---
title: Ottimizzazione dei media locali di routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Ottimizzazione di elementi multimediali locali per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 060b6f0fdf92969894cad98178073a4288eb2325
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158098"
---
# <a name="local-media-optimization-for-direct-routing"></a>Ottimizzazione di elementi multimediali locali per il routing diretto

La voce PSTN (Public Switched Telephone Network) è considerata un'applicazione business-critical con elevate aspettative per la qualità della voce. Il routing diretto consente di controllare i flussi di traffico multimediale per soddisfare una moltitudine di topologie di rete e di configurazioni di telefonia locali per varie aziende in tutto il mondo. 

L'ottimizzazione dei contenuti multimediali locali per il routing diretto consente di gestire la qualità vocale per:

-   Controllare la modalità di flusso del traffico multimediale tra i client Team e i controller di bordo della sessione cliente (SBCs).
-   Mantenere i contenuti multimediali locali all'interno dei limiti delle subnet della rete aziendale.
-   Consentendo flussi multimediali tra i client di teams e SBCs anche se i SBCs sono dietro i firewall aziendali con indirizzi IP privati e non sono visibili direttamente da Microsoft.

L'ottimizzazione media locale supporta due scenari:

- Centralizzazione di tutti i trunk locali tramite un SBC centralizzato collegato al trunk SIP (Main Session Initiation Protocol), che fornisce servizi di telefonia a tutte le filiali locali della società.

-   Creazione di una topologia di rete virtuale di SBCs, in cui le SBCs nelle filiali locali sono connesse a un SBC proxy centralizzato visibile e comunicante con il sistema telefonico Microsoft tramite l'indirizzo IP esterno. In una topologia di rete virtuale i SBCs downstream stanno comunicando tramite indirizzi IP interni e non sono direttamente visibili al sistema telefonico.

Questo articolo descrive le funzionalità di funzionalità e gli scenari e le soluzioni dei clienti. Per informazioni dettagliate sulla configurazione, vedere [configurare l'ottimizzazione di elementi multimediali locali](direct-routing-media-optimization-configure.md). 

  > [!NOTE]
  > Se si vuole conservare l'elemento multimediale locale entro i limiti della propria Intranet, è consigliabile ottimizzare l'utilizzo dei contenuti multimediali locali. Se si ha già un bypass multimediale e si usano solo gli indirizzi IP pubblici del proprio SBCs, non è obbligatorio passare all'ottimizzazione media locale. Puoi continuare a usare il bypass multimediale. Per altre informazioni, vedere [pianificare il bypass multimediale](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Scenari di clienti supportati

Per questa discussione, supponiamo che contoso esegua più aziende in tutto il mondo come segue. Tieni presente che le aree Europa e APAC vengono usate solo come esempi. Una società può avere diverse aree geografiche con requisiti simili.
 
- **In Europa**Contoso ha uffici in circa 30 paesi. Ogni Office ha il proprio PBX (Private Branch Exchange). 

  A Contoso è stata offerta un'opzione per centralizzare i trunk in un'unica posizione, ad esempio Amsterdam, per tutti i 30 uffici europei. Contoso ha distribuito il SBC ad Amsterdam, se la larghezza di banda è sufficiente per eseguire chiamate attraverso la posizione centralizzata, collegato un trunk SIP centrale alla posizione centralizzata e ha iniziato a servire tutti i percorsi europei da Amsterdam. 

- **Nell'area APAC**, Contoso ha più uffici in paesi diversi. 

  In molti paesi, la società ha ancora tronchi TDM (Time-Division Multiplexing) nelle filiali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC, quindi il passaggio a SIP non è possibile. Supponiamo che ci siano più di 50 filiali di Contoso nell'area APAC con centinaia di gateway (SBCs). In questo scenario, non è possibile associare tutti i gateway all'interfaccia di routing diretta a causa della mancanza di indirizzi IP pubblici e/o sblocchi di Internet locali. Inoltre, alcuni paesi impongono requisiti normativi che non possono essere soddisfatti senza la connettività di rete PSTN locale.

In base ai requisiti aziendali, Contoso ha implementato due soluzioni con l'ottimizzazione media locale per il routing diretto:

- **In Europa**tutti i trunk sono centralizzati e i flussi multimediali tra l'SBC centrale e gli utenti, in base alla posizione dell'utente. 

  - Se un utente è connesso alla subnet locale di una rete aziendale (ovvero l'utente è interno), i flussi multimediali tra l'IP interno del SBC centrale e il client Teams dell'utente. 
  
  - Se un utente si trova al di fuori dei limiti della rete aziendale, ad esempio se l'utente usa una connessione Internet wireless pubblica, l'utente viene considerato esterno. In questo caso, il flusso di elementi multimediali viene posizionato tra l'IP esterno dell'SBC centrale e il client teams.

- **Nell'area APAC**un SBC proxy centralizzato è associato a Microsoft Direct routing, che indirizza il supporto tra l'interfaccia di routing diretto e il SBCS downstream nelle succursali locali. 

  Le SBCs downstream nelle succursali locali non sono direttamente visibili al routing diretto in APAC, ma sono abbinate usando il cmdlet Set-CSOnlinePSTNGateway per creare una topologia di rete virtuale all'interno del sistema telefonico Microsoft. Quando possibile, l'elemento multimediale rimane sempre locale. Gli utenti esterni hanno flussi multimediali tra il client teams e l'IP pubblico del proxy SBC.


## <a name="central-sbc-with-centralized-trunks"></a>SBC centrale con trunk centralizzato

Per creare una soluzione in cui i servizi PSTN vengono forniti a tutte le filiali locali tramite un singolo SBC centrale con un trunk SIP centralizzato connesso, l'amministratore del tenant di Contoso esegue la coppia di un SBC (centralsbc.contoso.com) per il servizio. il SBC ha un trunk SIP centralizzato connesso. 

- Quando un utente si trova nella rete interna della società, SBC fornisce l'indirizzo IP interno dell'SBC per l'elemento multimediale.

- Quando un utente si trova all'esterno della rete aziendale, SBC fornisce l'indirizzo IP esterno (pubblico) dell'SBC.

Nota: tutti i valori inclusi in esempi, tabelle o diagrammi sono presentati solo a scopo esemplificativo.

Tabella 1. Parametri di rete di esempio per SBCs 

| Posizione | FQDN DI SBC | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Germania | Non distribuito | 192.168.6.0/24 | 172.16.76.74 | Non distribuito |  Non distribuito |
| Francia | Non distribuito | 192.168.7.0/24 | 172.16.76.75 | Non distribuito |  Non distribuito ||||


### <a name="internal-user"></a>Utente interno

Il diagramma seguente mostra il flusso di traffico quando un utente è connesso alla rete aziendale nella sede della filiale o del sito dell'utente. 

Mentre si è in locale, l'utente viene assegnato alla filiale locale in Germania. L'utente effettua una telefonata di routing diretto tramite teams.

- Il client Teams dell'utente comunica direttamente al sistema telefonico tramite l'API REST, ma l'elemento multimediale generato durante il flusso della chiamata all'indirizzo IP interno del SBC centrale. 

- L'SBC reindirizza il sistema flusso al telefono e la rete PSTN connessa. 

- Il SBC centrale è visibile al sistema telefonico solo tramite l'indirizzo IP esterno. 

Diagramma 1. Flusso di traffico quando l'utente si trova nel sito "Home" con un SBC centralizzato e con un trunk SIP centralizzato connesso

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-1.png "Flusso di traffico quando l'utente si trova nel sito "Home" con SBC centralizzato con trunk SIP centralizzato connesso")


### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso di traffico quando un utente non è in locale e non è connesso alla rete aziendale, ovvero il dispositivo dell'utente è connesso a Internet tramite un dispositivo mobile o un Wi-Fi pubblico. L'utente effettua una chiamata telefonica di routing diretto tramite Team:

- Il client Teams dell'utente comunica direttamente al sistema telefonico tramite l'API REST, ma, in questo caso, il contenuto multimediale generato durante la chiamata passa all'indirizzo IP esterno dell'SBC centrale. 

- L'SBC reindirizza il sistema flusso al telefono e la rete PSTN connessa. 

- Il SBC centrale è visibile al sistema telefonico solo tramite l'indirizzo IP esterno. 

In questo caso, il comportamento è simile se l'utente è locale alla filiale in Germania o a qualsiasi altra filiale. L'utente è considerato esterno perché l'utente si trova al di fuori dei limiti della rete aziendale.

Diagramma 2. Flusso di traffico quando l'utente è esterno con un SBC centralizzato e con un trunk SIP centralizzato connesso

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-2.png "Flusso di traffico quando l'utente è esterno in caso di SBC centralizzato con trunk SIP centralizzato connesso")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy con il SBCs downstream connesso

Per creare una soluzione in cui i servizi PSTN sono forniti in tutte le filiali locali nell'area APAC in cui la centralizzazione dei tronchi TDM non è un'opzione, l'amministratore di Contoso esegue la coppia di un SBC (proxysbc.contoso.com), detto anche SBC proxy, al servizio di routing diretto. 

In seguito, l'amministratore di Contoso aggiunge alcuni SBCs downstream che indicano che possono essere raggiunti tramite il proxy SBC proxysbc.contoso.com. I SBCs downstream, tuttavia, non hanno IP pubblici, ma possono essere assegnati alle route vocali. La tabella seguente mostra i parametri e la configurazione di rete di esempio.

Quando un utente è nella filiale locale in cui si trova il SBC downstream, il traffico multimediale passa direttamente tra l'utente e l'SBC downstream locale. Se un utente si trova all'esterno di Office (in un Internet pubblico), il contenuto multimediale passa dall'utente all'IP pubblico del proxy SBC, che lo delega agli SBC a valle rilevanti.

Tabella 2. Informazioni sulla rete SBC di esempio

| Posizione | FQDN DI SBC | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC  | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nessuno |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nessuno |  192.168.2.5 |
| Singapore | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Utente interno 

Il diagramma seguente mostra il flusso di traffico di alto livello per lo scenario quando un utente si trova all'interno di Office nell'area APAC. L'utente, che è stato assegnato a una filiale locale in Vietnam ed è in locale, effettua una chiamata telefonica diretta tramite Team. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST, ma l'elemento multimediale generato durante il flusso della chiamata all'indirizzo IP interno di SBC locale.

- Il SBC locale reindirizza il flusso al proxy SBC di Singapore e alla rete PSTN locale connessa.

-  Il proxy SBC è visibile al sistema telefonico tramite l'indirizzo IP esterno e instrada il flusso dall'SBC a valle (in questo caso il SBC locale in Vietnam) al sistema telefonico. 

- L'SBC downstream nella filiale locale non è visibile al sistema telefonico direttamente, ma viene mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'Ottimizzazione multimediale locale.

Nota: il comportamento potrebbe essere diverso per gli utenti locali e gli utenti non locali, a seconda della modalità di ottimizzazione media locale configurata. 

Per altre informazioni sulle possibili modalità e sul comportamento pertinente, vedere Configurare l'ottimizzazione di elementi multimediali locali.

Diagramma 3. Flusso di traffico quando l'utente si trova nella rete "Home" con un SBC proxy e con il SBCs downstream connesso 

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-3.png "Flusso di traffico nel caso di SBC proxy con connessione downstream SBCs quando l'utente si trova nella rete "Home"")

### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso di traffico quando un utente si trova all'esterno dei limiti della rete aziendale. L'utente non è in locale (non rientra nei limiti della rete aziendale). L'utente effettua una telefonata di routing diretto tramite Teams a un numero di telefono in Vietnam. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST, ma il supporto generato durante la chiamata passa prima all'indirizzo IP esterno del proxy SBC di Singapore. 

- In base ai criteri di configurazione e vocale (vedere [configurare l'ottimizzazione dei contenuti multimediali locali](direct-routing-media-optimization-configure.md) per i dettagli), l'SBC Proxy reindirizza il flusso allo SBC downstream in Vietnam. 

- Lo SBC downstream in Vietnam reindirizza il flusso alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al sistema telefonico solo tramite l'indirizzo IP esterno.

-  L'SBC downstream nella filiale locale non è visibile direttamente al sistema telefonico, ma viene mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'Ottimizzazione multimediale locale. Nell'esempio l'utente è considerato esterno perché l'utente si trova all'esterno dei limiti della rete aziendale. 

Diagramma 4. Flusso di traffico quando l'utente è esterno con un SBC proxy e con il SBCs downstream connesso

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-4.png "Flusso di traffico nel caso di SBC proxy con SBCs downstream connesso quando l'utente è esterno")

## <a name="local-media-optimization-modes"></a>Modalità di ottimizzazione dei media locali

L'ottimizzazione media locale supporta due modalità:

- **Modalità 1: bypass sempre**. In questo caso, se l'utente è interno, il contenuto multimediale verrà eseguito attraverso l'indirizzo IP interno del SBC locale, indipendentemente dalla posizione effettiva dell'utente interno. ad esempio, all'interno della stessa filiale in cui si trova il SBC downstream o in un'altra filiale.

- **Modalità 2: solo per gli utenti locali**. In questa modalità, gli elementi multimediali scorrono direttamente all'indirizzo IP interno del SBC locale solo se generati dall'utente interno che si trova nella stessa filiale dello SBC downstream. 

Per distinguere tra le modalità di ottimizzazione degli elementi multimediali locali, l'amministratore del tenant deve impostare il parametro-BypassMode su' always ' o ' OnlyForLocalUsers ' per ogni SBC usando il cmdlet Set-CSonlinePSTNGateway. Per altre informazioni, vedere [configurare l'ottimizzazione di elementi multimediali locali](direct-routing-media-optimization-configure.md).  

### <a name="mode-1-always-bypass"></a>Modalità 1: bypass sempre

Se si ha una buona connessione tra le filiali, la modalità consigliata è sempre bypass.

Supponiamo ad esempio che una società disponga di un trunk SIP centralizzato di Amsterdam, che serve 30 paesi e offre una buona connettività tra tutti e 30 i siti e gli utenti locali. Esiste anche una filiale in Germania in cui è distribuito un SBC locale.

Il SBC in Germania può essere configurato in modalità "Ignora sempre". Gli utenti, indipendentemente dalla loro posizione, si connetteranno a SBC direttamente tramite l'indirizzo IP interno del SBC, ad esempio dalla Francia alla Germania; Vedi il diagramma seguente per riferimento.

Di seguito vengono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione dell'SBC definito nel criterio di routing vocale online.

- Scenario 2. L'utente e i gateway si trovano in siti diversi.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione di SBC definita nel criterio di routing vocale online

Il SBC di Amsterdam è configurato per essere un SBC proxy per un SBC locale a valle in Germania. L'utente si trova in Germania nella stessa subnet della rete aziendale dello SBC locale. Sia SBCs (proxy che downstream) sono configurati per la modalità di bypass sempre. I criteri di routing vocale online specificano che in caso di chiamate in Germania (con prefisso + 49) devono essere indirizzati al SBC locale in Germania. Tutte le altre chiamate e, se il SBC in Germania non riesce, le chiamate in Germania devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 3. Configurazione di esempio per lo scenario 1

| Posizione fisica dell'utente | L'utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Germania | + 49 1 437 2800 | Priorità 1: ^\+49 (\d{8}) $-DEsbc.contoso.com<br>Priorità 2:. *-proxysbc.contoso.com| DEsbc.contoso.com-ignora sempre <br>proxysbc.contoso.com-ignora sempre | < utente teams-> DEsbc.contoso.com |

Il diagramma seguente mostra il flusso di traffico di alto livello per l'utente interno in Germania che effettua una chiamata telefonica diretta tramite Team al numero in Germania. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST. 

- L'elemento multimediale generato durante il flusso della chiamata all'indirizzo IP interno del SBC locale. 

- Il SBC locale reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al sistema telefonico tramite l'indirizzo IP esterno e instrada il flusso dall'SBC downstream (in questo caso, lo SBC locale in Germania) al sistema telefonico. 

- L'SBC downstream nella filiale locale non è visibile al sistema telefonico direttamente, ma viene mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'Ottimizzazione multimediale locale.


Diagramma 5.  Flusso di traffico con la modalità "Ignora sempre" e l'utente si trova nel sito "Home"

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-5.png "Il flusso di traffico con la modalità "Ignora sempre" e l'utente si trova nel sito "Home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2: l'utente e i gateway si trovano in siti diversi

Il SBC di Amsterdam è configurato per essere un SBC proxy per un SBC locale a valle in Germania. Sia SBCs (proxy che downstream) sono configurati per la modalità di bypass sempre. L'utente interno in Francia, che si trova nella filiale locale, sta effettuando una chiamata di routing diretto in Germania. I criteri di routing vocale online specificano che le chiamate in Germania (con prefisso + 49) devono essere indirizzate al SBC locale in Germania. Tutte le altre chiamate e, se il SBC in Germania non riesce, tutte le chiamate in Germania devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 4. Configurazione di esempio per lo scenario 2

| Posizione fisica dell'utente | L'utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Francia | + 49 1 437 2800 | Priorità 1: ^\+49 (\d{8}) $-DEsbc.contoso.com <br>Priorità 2:. *-proxysbc.contoso.com |  DEsbc.contoso.com-ignora sempre proxysbc.contoso.com-ignora sempre | < utente teams-> DEsbc.contoso.com  |

Il diagramma seguente mostra il flusso di traffico di alto livello quando l'utente interno tedesco che si trova in Francia effettua una chiamata diretta di routing tramite teams al numero in Germania. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST.

- Il contenuto multimediale generato durante la chiamata passa direttamente all'SBC nell'indirizzo IP interno della Germania. 

- Il SBC in Germania reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa. 

Diagramma 6.  Flusso di traffico con la modalità "Ignora sempre" e l'utente non si trova nel sito "Home", ma nella rete interna

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-6.png "Il flusso di traffico con la modalità "Ignora sempre" e l'utente non si trova nel sito "Home", ma nella rete interna")

### <a name="mode-2-only-for-local-users"></a>Modalità 2: solo per gli utenti locali

Se sono presenti connessioni errate tra le filiali locali, ma le connessioni tra le varie filiali locali e l'ufficio regionale, la modalità consigliata è "solo per gli utenti locali".

Ad esempio, nell'area APAC, supponiamo che Contoso disponga di più uffici in paesi diversi. Per molti paesi, il passaggio a SIP non è possibile perché la società ha ancora trunk TDM in molte succursali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC. Sono inoltre presenti più di 50 succursali di Contoso nell'area APAC con centinaia di gateway (SBCs). 

Per creare una soluzione in cui i servizi PSTN sono forniti in tutte le filiali locali nell'area APAC in cui la centralizzazione dei tronchi TDM non è un'opzione, l'amministratore di Contoso unisce un SBC regionale a Singapore come SBC proxy al servizio di routing diretto. La connessione diretta tra le filiali locali non è buona, ma esiste una buona connessione tra ogni filiale locale e il SBC regionale di Singapore. Per l'SBC regionale, l'amministratore sceglie la modalità "sempre bypass" e per la SBCs locale a valle l'amministratore sceglie la modalità "solo per gli utenti locali".

Di seguito vengono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione di SBC definita nel criterio di routing vocale online

- Scenario 2. L'utente e i gateway si trovano in siti diversi

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione dell'SBC definito in criteri di routing vocale online

Supponiamo che SBC in Singapore sia configurato come SBC proxy per il SBCs locale a valle in Vietnam e Indonesia. L'utente si trova in Vietnam nella stessa posizione del SBC locale. I criteri di routing vocale online specificano che le chiamate in Vietnam (con prefisso area + 84) devono essere indirizzate al SBC locale in Vietnam. Tutte le altre chiamate e, se il SBC in Vietnam non riesce, le chiamate in Vietnam devono essere indirizzate al proxy SBC di Singapore. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 5. Configurazione di esempio per la modalità "solo per gli utenti locali" scenario 1

| Posizione fisica dell'utente | L'utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 | Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com <br>Priorità 2:. *-proxysbc.contoso.com | VNsbc.contoso.com-solo per gli utenti locali <br> proxysbc.contoso.com-ignora sempre | < utente teams-> VNsbc.contoso.com |

Nel diagramma seguente un utente assegnato alla filiale locale in Vietnam, mentre è in locale, effettua una chiamata telefonica diretta tramite Team. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST. 

- Gli elementi multimediali generati durante il flusso delle chiamate all'indirizzo IP interno del SBC locale. 

- Il SBC locale reindirizza il flusso al proxy SBC di Singapore e alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al sistema telefonico tramite l'indirizzo IP esterno e instrada il flusso dall'SBC downstream (in questo caso, lo SBC locale in Vietnam) al sistema telefonico. 

- L'SBC downstream nella filiale locale non è visibile al sistema telefonico direttamente, ma viene mappato all'interno della topologia di rete virtuale.

Diagramma 7. Flusso del traffico con la modalità "solo per gli utenti locali" e l'utente si trova nel sito "Home"

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-7.png "Flusso del traffico con la modalità "solo per gli utenti locali" e l'utente si trova nel sito "Home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2. L'utente e i gateway si trovano in siti diversi

Supponiamo che SBC in Singapore sia configurato come SBC proxy per il SBCs locale a valle in Vietnam e Indonesia. L'utente interno in Indonesia, che si trova nella filiale locale, sta effettuando una chiamata di routing diretto in Vietnam. I criteri di routing vocale online specificano che le chiamate al Vietnam (con prefisso area + 84) devono essere instradate allo SBC locale in Vietnam. Tutte le altre chiamate e, se il SBC in Vietnam non riesce, le chiamate in Vietnam devono essere indirizzate al proxy SBC di Singapore. Il proxy SBC di Singapore è impostato sulla modalità "sempre Byass" e il SBC locale in Vietnam è impostato su "solo per gli utenti locali". La tabella seguente riepiloga la configurazione di esempio. 

Tabella 6. Configurazione utente

| Posizione fisica dell'utente | L'utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | + 84 4 3926 3000 | Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com <br> Priorità 2:. *-proxysbc.contoso.com |VNsbc.contoso.com-solo per gli utenti locali <br> proxysbc.contoso.com-ignora sempre | < utente teams-> proxysbc.contoso.com <-> VNsbc.contoso.com |


Nel diagramma seguente l'utente interno, mentre si trova in locale nella filiale indonesiana, effettua una chiamata telefonica diretta tramite Team a un numero in Vietnam. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST.

- Gli elementi multimediali generati durante il flusso delle chiamate all'indirizzo IP interno del proxy SBC sono i primi. 

- Il proxy SBC di Singapore reindirizza il flusso all'indirizzo IP interno dell'SBC downstream in Vietnam e al sistema telefonico. 

- Lo SBC downstream in Vietnam instrada il flusso alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al sistema telefonico solo tramite l'indirizzo IP esterno.

- Le SBCs downstream nelle succursali locali non sono visibili al sistema telefonico direttamente, ma sono mappate all'interno della topologia di rete virtuale.

Diagramma 8.  Flusso del traffico con la modalità "solo per gli utenti locali" e l'utente non si trova nel sito "Home", ma nella rete interna

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-8.png "Flusso di traffico con la modalità "solo per utenti locali", l'utente non si trova nel sito "Home", ma nella rete interna")


