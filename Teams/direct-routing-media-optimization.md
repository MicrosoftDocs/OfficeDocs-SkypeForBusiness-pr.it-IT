---
title: Ottimizzazione del supporto locale per il routing diretto
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
description: Ottimizzazione degli elementi multimediali locali per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886dd4d14d8393764f3c939991a8959ed4726aa3
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686462"
---
# <a name="local-media-optimization-for-direct-routing"></a>Ottimizzazione degli elementi multimediali locali per il routing diretto

La voce PSTN (Public Switched Telephone Network) è considerata un'applicazione di importanza fondamentale per l'azienda, con aspettative elevate in relazione alla qualità vocale. Il routing diretto consente di controllare i flussi di traffico multimediale per supportare numerose topologie di rete e configurazioni di telefonia locali per varie aziende in tutto il mondo. 

L'ottimizzazione degli elementi multimediali locali per il routing diretto consente di gestire la qualità vocale:

-   Controllare il modo in cui il traffico multimediale fluisce tra i client di Teams e i controller dei confini della sessione (SBC) del cliente.
-   Mantenere gli elementi multimediali locali entro i limiti delle subnet di rete aziendali.
-   Consentire flussi multimediali tra i client di Teams e gli SBC anche se i dispositivi SBC sono dietro firewall aziendali con IP privati e non sono visibili direttamente a Microsoft.

L'ottimizzazione degli elementi multimediali locali supporta due scenari:

- Centralizzazione di tutti i trunk locali tramite un SBC centralizzato connesso al trunk SIP (Session Initiation Protocol) principale, che fornisce servizi di telefonia a tutte le succursali locali della società.

-   Creazione di una topologia di rete virtuale di SBC, in cui gli SBC delle succursali locali sono connessi a un SBC proxy centralizzato visibile e con cui comunica il Sistema telefonico Microsoft tramite l'indirizzo IP esterno. In una topologia di rete virtuale, gli SBC a valle comunicano tramite IP interni e non sono direttamente visibili al Sistema telefonico.

Questo articolo descrive le funzionalità e gli scenari e le soluzioni dei clienti. Per informazioni dettagliate sulla configurazione, vedere [Configurare l'ottimizzazione del supporto locale.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Se si vuole mantenere gli elementi multimediali locali entro i limiti della Intranet, è consigliabile ottimizzare gli elementi multimediali locali. Se si dispone già del bypass multimediale e si usano solo gli indirizzi IP pubblici dei file SBC, non è obbligatorio passare all'ottimizzazione del supporto locale. È possibile continuare a usare il bypass multimediale. Per altre informazioni, vedere [Pianificare il bypass multimediale.](direct-routing-plan-media-bypass.md)


## <a name="supported-customer-scenarios"></a>Scenari dei clienti supportati

Per questa discussione, si supponga che Contoso gestisce più aziende in tutto il mondo come indicato di seguito. Le aree Europa e APAC vengono usate solo come esempi. Un'azienda potrebbe avere diverse aree geografiche con requisiti simili.
 
- **In Europa,** Contoso ha uffici in circa 30 paesi. Ogni ufficio ha un proprio PBX (Private Branch Exchange). 

  A Contoso è stata offerta la possibilità di centralizzare i trunk in un'unica posizione, Amsterdam, per tutti e 30 gli uffici europei. Contoso ha distribuito lo SBC in Amsterdam, ha fornito una larghezza di banda sufficiente per eseguire chiamate attraverso la posizione centralizzata, ha collegato un trunk SIP centrale alla posizione centralizzata e ha iniziato a servire tutte le località europee da Amsterdam. 

- **Nell'area geografica dell'APAC,** Contoso ha più uffici in paesi diversi. 

  In molti paesi, l'azienda ha ancora trunk di multiplexing (TDM) di divisione temporale nelle succursali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC, quindi non è possibile passare a SIP. Si supponga che nell'area APAC siano presenti più di cinquanta filiali Contoso con centinaia di gateway (SBC). In questo scenario non è possibile associare tutti i gateway all'interfaccia di routing diretto a causa dell'assenza di indirizzi IP pubblici e/o breakout Internet locali. Inoltre, alcuni paesi impongono requisiti normativi che non possono essere soddisfatti senza disporre di connettività di rete PSTN locale.

In base ai requisiti aziendali, Contoso ha implementato due soluzioni con Ottimizzazione elementi multimediali locali per il routing diretto:

- **In Europa,** tutti i trunk sono centralizzati e i flussi multimediali tra l'SBC centrale e gli utenti, in base alla posizione dell'utente. 

  - Se un utente è connesso alla subnet locale di una rete aziendale (ovvero, l'utente è interno), il flusso multimediale passa tra l'INDIRIZZO IP interno della SBC centrale e il client Teams dell'utente. 
  
  - Se un utente non è ai confini della rete aziendale, ad esempio se usa una connessione Internet wireless pubblica, l'utente viene considerato esterno. In questo caso, il flusso degli elementi multimediali tra l'INDIRIZZO IP esterno della pagina SBC centrale e il client di Teams.

- **Nell'area geografica APAC,** un proxy centralizzato SBC viene associato a Microsoft Direct Routing, che indirizza gli elementi multimediali tra l'interfaccia di routing diretto e gli SBC a valle nelle succursali locali. 

  I BCS a valle nelle succursali locali non sono direttamente visibili al routing diretto in APAC, ma vengono abbinati con il cmdlet Set-CSOnlinePSTNGateway per creare una topologia di rete virtuale all'interno del Sistema telefonico Microsoft. Gli elementi multimediali rimangono sempre locali quando possibile. Gli utenti esterni hanno elementi multimediali che scorrono tra il client di Teams e l'IP pubblico del proxy SBC.


## <a name="central-sbc-with-centralized-trunks"></a>SBC centrale con trunk centralizzati

Per creare una soluzione in cui i servizi PSTN vengono forniti a tutte le succursali locali tramite un singolo SBC centrale con un trunk SIP centralizzato connesso, l'amministratore del tenant di Contoso abbina un valore SBC (centralsbc.contoso.com) al servizio; A SBC è connesso un trunk SIP centralizzato. 

- Quando un utente fa parte della rete interna della società, SBC fornisce l'INDIRIZZO IP interno del database SBC per i supporti multimediali. 

- Quando un utente è esterno alla rete aziendale, SBC fornisce l'INDIRIZZO IP esterno (pubblico) di SBC.

Nota: tutti i valori inclusi in esempi, tabelle o diagrammi vengono presentati solo a scopo di illustrazione.

Tabella 1. Esempio di parametri di rete per gli SBC 

| Posizione | SBC FQDN | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Germania | Non distribuita | 192.168.6.0/24 | 172.16.76.74 | Non distribuita |  Non distribuita |
| Francia | Non distribuita | 192.168.7.0/24 | 172.16.76.75 | Non distribuita |  Non distribuita ||||


### <a name="internal-user"></a>Utente interno

Il diagramma seguente mostra il flusso di traffico quando un utente è connesso alla rete aziendale nella succursale o nel sito dell'utente. 

In locale, l'utente è assegnato alla succursale locale in Germania. L'utente effettua una chiamata telefonica con instradamento diretto tramite Teams.

- Il client Teams dell'utente comunica al Sistema telefonico direttamente tramite l'API REST, ma il supporto generato durante la chiamata passa all'indirizzo IP interno della SBC centrale. 

- SBC reindirizza il flusso al Sistema telefonico e alla rete PSTN connessa. 

- Il servizio SBC centrale è visibile al Sistema telefonico solo tramite l'indirizzo IP esterno. 

Diagramma 1. Flusso del traffico quando l'utente si trova nel sito "home" con un SBC centralizzato e con un trunk SIP centralizzato connesso

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-1.png "Flusso del traffico quando l'utente si trova in un sito "domestico" con SBC centralizzato con trunk SIP centralizzato connesso")


### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso di traffico quando un utente non è locale e non è connesso alla rete aziendale, ovvero se il dispositivo dell'utente è connesso a Internet tramite un dispositivo mobile o una rete #A0 pubblica. L'utente effettua una chiamata telefonica con instradamento diretto tramite Teams:

- Il client Teams dell'utente comunica al Sistema telefonico direttamente tramite l'API REST, ma, in questo caso, il supporto generato durante la chiamata passa all'indirizzo IP esterno della SBC centrale. 

- SBC reindirizza il flusso al Sistema telefonico e alla rete PSTN connessa. 

- Il servizio SBC centrale è visibile al Sistema telefonico solo tramite l'indirizzo IP esterno. 

In questo caso, il comportamento è simile sia che l'utente sia locale della succursale in Germania o di qualsiasi altra succursale. L'utente è considerato esterno perché è al di fuori dei limiti della rete aziendale.

Diagramma 2. Flusso del traffico quando l'utente è esterno con un SBC centralizzato e con un trunk SIP centralizzato connesso

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-2.png "Flusso del traffico quando l'utente è esterno nel caso di SBC centralizzato con trunk SIP centralizzato connesso")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy SBC con SBC a valle connessi

Per creare una soluzione in cui i servizi PSTN vengono forniti in tutte le succursali locali nell'area APAC in cui la centralizzazione dei trunk TDM non è disponibile, l'amministratore Contoso abbina un database SBC (proxysbc.contoso.com), chiamato anche SBC proxy, al servizio di routing diretto. 

In un secondo momento, l'amministratore di Contoso aggiunge alcuni SBC a valle per indicare che possono essere raggiunti tramite la connessione SBC proxy proxysbc.contoso.com. Gli SBC a valle non hanno IP pubblici, ma possono essere assegnati a percorsi vocali. La tabella seguente mostra un esempio di configurazione e parametri di rete.

Quando un utente si trova nella succursale locale in cui si trova il valore SBC a valle, il traffico multimediale passa direttamente tra l'utente e l'SBC a valle locale. Se un utente è esterno all'ufficio (su una Internet pubblica), gli elementi multimediali passano dall'utente all'IP pubblico del proxy SBC, che lo proxy agli SBC a valle pertinenti.

Tabella 2. Esempio di informazioni sulla rete SBC

| Posizione | SBC FQDN | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC  | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nessuno |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nessuno |  192.168.2.5 |
| Singapore | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Utente interno 

Il diagramma seguente mostra il flusso di traffico di alto livello per lo scenario quando un utente si trova all'interno dell'ufficio nell'area APAC. L'utente, assegnato a una filiale locale in Vietnam e locale, effettua una chiamata telefonica con instradamento diretto tramite Teams. 

- Il client Teams dell'utente comunica con il sistema telefonico direttamente tramite l'API REST, ma i supporti generati durante la chiamata passano all'indirizzo IP interno del servizio SBC locale.

- Il servizio SBC locale reindirizza il flusso al proxy SBC di Singapore e alla rete PSTN locale connessa.

-  Il proxy SBC è visibile al Sistema telefonico solo attraverso l'indirizzo IP esterno e instrada il flusso dal valore SBC a valle (in questo caso la SBC locale in Vietnam) al Sistema telefonico. 

- L'SBC a valle nella succursale locale non è visibile direttamente al Sistema telefonico, ma è mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'ottimizzazione dei supporti locali.

Nota: il comportamento potrebbe essere diverso per gli utenti locali e non locali, a seconda della modalità di ottimizzazione file multimediale locale configurata. 

Per altre informazioni sulle modalità possibili e sul comportamento pertinente, vedere Configurare l'ottimizzazione degli elementi multimediali locali.

Diagramma 3. Flusso del traffico quando l'utente si trova nella rete "domestica" con un proxy SBC e con gli SBC a valle connessi 

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-3.png "Flusso del traffico in caso di SBC proxy con SBC downstream connessi quando l'utente è nella rete "domestica"")

### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso del traffico quando un utente è al di fuori dei limiti di rete aziendali. L'utente non è locale e non è entro i confini della rete aziendale. L'utente effettua una chiamata telefonica di instradamento diretto tramite Teams a un numero di telefono in Vietnam. 

- Il client Teams dell'utente comunica con il Sistema telefonico direttamente tramite l'API REST, ma i supporti generati durante la chiamata vengono prima di tutto indirizzati all'indirizzo IP esterno del proxy SBC a Singapore. 

- In base ai criteri [](direct-routing-media-optimization-configure.md) di configurazione e voce (vedere Configurare l'ottimizzazione degli elementi multimediali locali per i dettagli), il proxy SBC reindirizza il flusso al database SBC a valle in Vietnam. 

- La rete SBC a valle in Vietnam reindirizza il flusso alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al Sistema telefonico solo tramite l'indirizzo IP esterno.

-  L'SBC a valle nella succursale locale non è visibile direttamente al Sistema telefonico, ma è mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'ottimizzazione dei supporti locali. In questo esempio l'utente è considerato esterno perché non rientra nei limiti della rete aziendale. 

Diagramma 4. Flusso del traffico quando l'utente è esterno con un SBC proxy e con SBC a valle connessi

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-4.png "Flusso del traffico in caso di SBC proxy con SBC downstream connessi quando l'utente è esterno")

## <a name="local-media-optimization-modes"></a>Modalità di ottimizzazione degli elementi multimediali locali

L'ottimizzazione degli elementi multimediali locali supporta due modalità:

- **Modalità 1: ignorare sempre**. In questo caso, se l'utente è interno, il flusso degli elementi multimediali attraverso l'indirizzo IP interno della SBC a valle locale, indipendentemente dalla posizione effettiva dell'utente interno; ad esempio all'interno della stessa succursale in cui si trova il ramo SBC a valle o in altre filiali.  

- **Modalità 2: solo per gli utenti locali.** In questa modalità, il flusso degli elementi multimediali verrà indirizzato direttamente all'indirizzo IP interno di SBC di downstream locale solo quando viene generato dall'utente interno che si trova nella stessa succursale di SBC a valle. 

Per distinguere tra le modalità di ottimizzazione del supporto locale, l'amministratore del tenant deve impostare il parametro -BypassMode su "Always" o "OnlyForLocalUsers" per ogni SBC usando il cmdlet Set-CSonlinePSTNGateway. Per altre informazioni, vedere [Configurare l'ottimizzazione degli elementi multimediali locali.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Quando gli utenti sono interni, è necessaria la connettività dei supporti multimediali tra l'utente e SBC tramite l'indirizzo IP **interno.** In questo caso non ci sono fallback ai inoltro del trasporto pubblico per i contenuti multimediali, perché SBC fornirerà un IP interno per la connettività dei supporti multimediali. 

### <a name="mode-1-always-bypass"></a>Modalità 1: ignorare sempre

Se la connessione tra succursali è buona, la modalità consigliata è Sempre esclusa.
 
Ad esempio, si supponga che una società abbia un trunk SIP centralizzato in Amsterdam, al servizio di 30 paesi con una buona connettività tra i 30 siti e gli utenti locali. È presente anche una filiale in Germania in cui è distribuito un SBC locale.

Il servizio SBC in Germania può essere configurato in modalità "Ignora sempre". Gli utenti, indipendentemente dalla loro posizione, si connetteranno all'SBC direttamente attraverso l'indirizzo IP interno del database SBC (ad esempio dalla Francia alla Germania; vedere il diagramma seguente per riferimento).

Di seguito sono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione del servizio SBC definito nel criterio di routing vocale online.

- Scenario 2. L'utente e il gateway si tratta di siti diversi.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione del servizio SBC definito nel criterio di routing vocale online

Lo SBC di Amsterdam è configurato per essere un proxy SBC per un SBC a valle locale in Germania. L'utente si trova in Germania nella stessa subnet della rete aziendale del servizio SBC locale. Sia gli SBC (proxy che a valle) sono configurati per la modalità Bypass sempre. I criteri di routing vocale online specificano che nel caso di chiamate in Germania (con codice di area +49) devono essere instradati all'SBC locale in Germania. Tutte le altre chiamate, e nel caso in cui l'SBC in Germania non riesce, le chiamate in Germania devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 3. Configurazione di esempio per lo scenario 1

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri per l'instradamento vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Germania | +49 1 437 2800 | Priorità 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Priorità 2: .* - proxysbc.contoso.com| DEsbc.contoso.com - Ignora sempre <br>proxysbc.contoso.com - Ignora sempre | Team User <-> DEsbc.contoso.com |

Il diagramma seguente mostra il flusso di traffico di alto livello per l'utente interno in Germania che effettua una chiamata telefonica di routing diretto attraverso Teams al numero in Germania. 

- Il client Teams dell'utente comunica con il Sistema telefonico direttamente tramite l'API REST. 

- Il supporto generato durante la chiamata passa all'indirizzo IP interno del servizio SBC locale. 

- Il servizio SBC locale reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al Sistema telefonico solo attraverso l'indirizzo IP esterno e instrada il flusso dal valore SBC a valle (in questo caso, l'SBC locale in Germania) al Sistema telefonico. 

- L'SBC a valle nella succursale locale non è visibile direttamente al Sistema telefonico, ma è mappato all'interno della topologia di rete virtuale definita dall'amministratore di Contoso durante la configurazione dell'ottimizzazione dei supporti locali.


Diagramma 5.  Flusso del traffico con la modalità "Bypass sempre" e l'utente si trova nel sito "home"

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-5.png "Flusso del traffico con la modalità "Bypass sempre" e l'utente si trova nel sito "home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2: L'utente e i gateway si tratta di siti diversi

Lo SBC di Amsterdam è configurato per essere un proxy SBC per un SBC a valle locale in Germania. Sia gli SBC (proxy che a valle) sono configurati per la modalità Bypass sempre. L'utente interno in Francia, situato nella succursale locale, effettua una chiamata di routing diretto in Germania. I criteri di routing vocale online specificano che le chiamate verso la Germania (con codice di area +49) devono essere instradati all'SBC locale in Germania. Tutte le altre chiamate, e, nel caso in cui l'SBC in Germania non riesce, tutte le chiamate in Germania devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 4. Configurazione di esempio per lo scenario 2

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri per l'instradamento vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Francia | +49 1 437 2800 | Priorità 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Priorità 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com - Ignora sempre proxysbc.contoso.com - Ignora sempre | Utenti di Teams <- > DEsbc.contoso.com  |

Il diagramma seguente mostra il flusso di traffico di alto livello quando l'utente tedesco interno che si trova in Francia effettua una chiamata telefonica di routing diretto attraverso Teams al numero in Germania. 

- Il client Teams dell'utente comunica con il Sistema telefonico direttamente tramite l'API REST.

- Il supporto generato durante la chiamata passa direttamente all'SBC nell'indirizzo IP interno della Germania. 

- SBC in Germania reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa. 

Diagramma 6.  Flusso del traffico con la modalità "Bypass sempre" e l'utente non si trova nel sito "home", ma nella rete interna

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-6.png "Flusso del traffico con la modalità "Bypass sempre" e l'utente non si trova nel sito "home", ma nella rete interna")

### <a name="mode-2-only-for-local-users"></a>Modalità 2: solo per gli utenti locali

Se ci sono connessioni non erre tra le succursali locali ma buone connessioni tra ogni filiale locale e ufficio locale, la modalità consigliata è "Solo per gli utenti locali".

Ad esempio, nell'area APAC, si supponga che Contoso abbia più uffici in paesi diversi. Per molti paesi, il passaggio a SIP non è possibile perché la società ha ancora trunk TDM in molte filiali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC. Inoltre, ci sono più di cinquanta filiali Contoso nell'area APAC con centinaia di gateway (SBC). 

Per creare una soluzione in cui i servizi PSTN vengono forniti in tutte le succursali locali nell'area APAC in cui la centralizzazione dei trunk TDM non è disponibile, l'amministratore Contoso abbina un SBC locale a Singapore come SBC proxy al servizio di routing diretto. La connessione diretta tra le succursali locali non è buona, ma esiste una buona connessione tra ogni filiale locale e l'SBC locale di Singapore. Per il servizio SBC locale, l'amministratore sceglie la modalità "Bypass sempre" e per gli SBC locali a valle l'amministratore sceglie la modalità "Solo per gli utenti locali".

Di seguito sono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione del servizio SBC definito nel criterio di routing vocale online

- Scenario 2. L'utente e il gateway si tratta di siti diversi

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione del servizio SBC definito nel criterio di routing vocale online

Si supponga che la SBC di Singapore sia configurata come proxy SBC per le SBC a valle locali in Vietnam e Indonesia. L'utente si trova in Vietnam nella stessa posizione del database SBC locale. I criteri di routing vocale online specificano che le chiamate in Vietnam (con codice di area +84) devono essere instradati all'SBC locale in Vietnam. Tutte le altre chiamate e, se il servizio SBC in Vietnam ha esito negativo, le chiamate in Vietnam devono essere indirizzate al proxy SBC di Singapore. La tabella seguente riepiloga la configurazione di esempio. 

Tabella 5. Configurazione di esempio per la modalità "Solo per utenti locali" Scenario 1

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri per l'instradamento vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Priorità 2: .* - proxysbc.contoso.com | VNsbc.contoso.com- Solo per gli utenti locali <br> proxysbc.contoso.com - Ignora sempre | Team User <-> VNsbc.contoso.com |

Nel diagramma seguente, un utente assegnato alla filiale locale in Vietnam, mentre è locale, effettua una chiamata telefonica di instradamento diretto tramite Teams. 

- Il client Teams dell'utente comunica con il Sistema telefonico direttamente tramite l'API REST. 

- I supporti generati durante la chiamata passano all'indirizzo IP interno del servizio SBC locale. 

- Il servizio SBC locale reindirizza il flusso al proxy SBC di Singapore e alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al Sistema telefonico solo attraverso l'indirizzo IP esterno e instrada il flusso dal valore SBC a valle (in questo caso, l'SBC locale in Vietnam) al Sistema telefonico. 

- Il servizio SBC a valle nella succursale locale non è visibile direttamente nel Sistema telefonico, ma è mappato all'interno della topologia della rete virtuale.

Diagramma 7. Flusso del traffico con modalità "Solo per utenti locali" e l'utente si trova nel sito "home"

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-7.png "Flusso del traffico con modalità "Solo per utenti locali" e l'utente si trova nel sito "home"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2. L'utente e il gateway si tratta di siti diversi

Si supponga che la SBC di Singapore sia configurata come proxy SBC per le SBC a valle locali in Vietnam e Indonesia. L'utente interno in Indonesia, situato nella filiale locale, sta effettuando una chiamata di routing diretto in Vietnam. I criteri di routing vocale online specificano che le chiamate al Vietnam (con codice di area +84) devono essere instradati all'SBC locale in Vietnam. Tutte le altre chiamate, e, nel caso in cui la SBC in Vietnam non riesce, le chiamate al Vietnam devono essere indirizzate al proxy SBC a Singapore. Il proxy SBC di Singapore è impostato sulla modalità "Bypass sempre" e il valore SBC locale in Vietnam è impostato sulla modalità "Solo per gli utenti locali". La tabella seguente riepiloga la configurazione di esempio. 

Tabella 6. Configurazione utente

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri per l'instradamento vocale online | Modalità configurata per SBC | Flusso multimediale | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | +84 4 3926 3000 | Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com |VNsbc.contoso.com- Solo per gli utenti locali <br> proxysbc.contoso.com - Ignora sempre | Team User <-> proxysbc.contoso.com <-> VNsbc.contoso.com |


Nel diagramma seguente, l'utente interno, in sede nella filiale indonesiana, effettua una chiamata telefonica con instradamento diretto attraverso Teams a un numero in Vietnam. 

- Il client Teams dell'utente comunica con il Sistema telefonico direttamente tramite l'API REST.

- Gli elementi multimediali generati durante il flusso delle chiamate vengono prima indirizzati all'indirizzo IP interno del proxy SBC. 

- Il proxy SBC di Singapore reindirizza il flusso all'indirizzo IP interno della SBC a valle in Vietnam e al Sistema telefonico. 

- La rete SBC a valle in Vietnam indirizza il flusso alla rete PSTN locale connessa. 

- Il proxy SBC è visibile al Sistema telefonico solo tramite l'indirizzo IP esterno.

- Gli SBC a valle nelle succursali locali non sono visibili direttamente nel Sistema telefonico, ma sono mappati all'interno della topologia della rete virtuale.

Diagramma 8.  Flusso del traffico con modalità "Solo per gli utenti locali" e l'utente non si trova nel sito "home", ma nella rete interna

![Diagramma che mostra l'ottimizzazione del flusso di traffico locale](media/direct-routing-media-op-8.png "Flusso del traffico con la modalità "Solo per gli utenti locali", l'utente non si trova nel sito "home", ma nella rete interna")

## <a name="known-issues"></a>Problemi noti

Di seguito è riportato un elenco dei problemi noti attualmente presenti nell'ottimizzazione degli elementi multimediali locali. Microsoft sta lavorando alla risoluzione di questi problemi.

| Problema | Soluzione alternativa |
| :--- | :--- |
| Il client Teams non viene identificato come **interno quando** l'IP pubblico del client Teams corrisponde all'elenco di indirizzi IP attendibili del cliente. | L'ottimizzazione dei supporti locali richiede che la subnet del client Teams corrisponda a una subnet di [rete configurata dal tenant](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Le escalation delle chiamate causano chiamate eliminate quando il client di Teams viene identificato come interno.| Disabilitare l'ottimizzazione del supporto locale in Direct Routing SBC.|


