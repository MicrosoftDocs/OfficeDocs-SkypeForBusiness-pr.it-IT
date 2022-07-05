---
title: Ottimizzazione multimediale locale per il routing diretto
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
description: Ottimizzazione multimediale locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c33b8225f3bcde32428348e85166ff4d4463738
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616092"
---
# <a name="plan-for-local-media-optimization-for-direct-routing"></a>Pianificare Ottimizzazione multimediale locale per il routing diretto

La voce PSTN (Public Switched Telephone Network) è considerata un'applicazione business-critical con aspettative elevate per la qualità della voce. Direct Routing consente di controllare i flussi di traffico multimediale per ospitare una moltitudine di topologie di rete e configurazioni di telefonia locale per varie aziende in tutto il mondo.

Ottimizzazione multimediale locale per routing diretto consente di gestire la qualità della voce:

- Controllo del flusso del traffico multimediale tra i client di Teams e i controller dei confini della sessione (SBC) del cliente.
- Mantenere i supporti locali entro i limiti delle subnet di rete aziendale.
- Consentire flussi multimediali tra i client di Teams e gli SBC anche se gli SBC sono dietro firewall aziendali con IP privati e non sono visibili direttamente a Microsoft.

Ottimizzazione multimediale locale supporta due scenari:

- Centralizzazione di tutti i trunk locali attraverso una SBC centralizzata connessa al trunk SIP (Session Initiation Protocol) principale, fornendo servizi di telefonia a tutte le filiali locali dell'azienda.

- Creazione di una topologia di rete virtuale degli SBC, in cui gli SBC nelle succursali locali sono connessi a un SBC proxy centralizzato visibile a Microsoft Phone System e con cui comunicarlo tramite il relativo indirizzo IP esterno. In una topologia di rete virtuale, gli SBC a valle comunicano tramite IP interni e non sono direttamente visibili nel sistema telefonico.

Questo articolo descrive le funzionalità e gli scenari e le soluzioni dei clienti. Per informazioni dettagliate sulla configurazione, vedi [Configurare Ottimizzazione multimediale locale](direct-routing-media-optimization-configure.md).

  > [!NOTE]
  > Se vuoi mantenere i contenuti multimediali locali entro i limiti della tua Intranet, è consigliabile Ottimizzazione media locale. Se hai già media bypass e usi solo gli indirizzi IP pubblici dei tuoi SBC, non è obbligatorio passare a Ottimizzazione multimediale locale. Puoi continuare a usare bypass multimediale. Per altre informazioni, vedi [Pianificare il bypass multimediale](direct-routing-plan-media-bypass.md).

Per informazioni sui fornitori di SBC che supportano Ottimizzazione multimediale locale, vedere [Session Border Controllers Certified for Direct Routing](direct-routing-border-controllers.md).

## <a name="supported-customer-scenarios"></a>Scenari dei clienti supportati

Per questa discussione, si supponga che Contoso gestisce più aziende in tutto il mondo come indicato di seguito. Si noti che le aree geografiche Europa e APAC sono utilizzate solo come esempi. Un'azienda potrebbe avere diverse aree geografiche con requisiti simili.

- **In Europa**, Contoso ha uffici in circa 30 paesi. Ogni ufficio ha un proprio PBX (Private Branch Exchange).

  A Contoso è stata offerta la possibilità di centralizzare i tronchi in un'unica posizione, Amsterdam, per tutti i 30 uffici europei. Contoso ha distribuito la SBC ad Amsterdam, ha fornito larghezza di banda sufficiente per eseguire chiamate attraverso la posizione centralizzata, connesso un trunk SIP centrale alla posizione centralizzata e ha iniziato a servire tutte le località europee da Amsterdam.

- **Nell'area APAC** Contoso ha più uffici in diversi paesi.

  In molti paesi, l'azienda dispone ancora di trunk di multiplexing di divisione temporale (TDM) nelle filiali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC, quindi non è possibile passare a SIP. Si supponga che nell'area APAC siano presenti più di 50 filiali Contoso con centinaia di gateway (SBC). In questo scenario, non è possibile associare tutti i gateway all'interfaccia di routing diretto a causa della mancanza di indirizzi IP pubblici e/o di breakout Internet locali. Inoltre, alcuni paesi impongono requisiti normativi che non possono essere soddisfatti senza la connettività di rete PSTN locale.

In base ai requisiti aziendali, Contoso ha implementato due soluzioni con Ottimizzazione multimediale locale per il routing diretto:

- **In Europa**, tutti i trunks sono centralizzati e flussi multimediali tra la SBC centrale e gli utenti, in base alla posizione dell'utente.

  - Se un utente è connesso alla subnet locale di una rete aziendale (ovvero l'utente è interno), i flussi multimediali tra l'INDIRIZZO IP interno della scheda SBC centrale e il client Teams dell'utente.

  - Se un utente non rientra nei limiti della rete aziendale, ad esempio se usa una connessione Internet wireless pubblica, l'utente è considerato esterno. In questo caso, i flussi multimediali tra l'INDIRIZZO IP esterno della scheda SBC centrale e il client teams.

- **Nell'area APAC**, un SBC proxy centralizzato viene associato a Microsoft Direct Routing, che indirizza i supporti tra l'interfaccia Direct Routing e gli SBC a valle nelle filiali locali.

  Gli SBC a valle nelle filiali locali non sono direttamente visibili in Direct Routing in APAC, ma sono associati utilizzando il cmdlet Set-CSOnlinePSTNGateway per creare una topologia di rete virtuale all'interno di Microsoft Phone System. I supporti rimangono sempre locali quando possibile. Gli utenti esterni hanno supporti che attraversano il client Teams e l'indirizzo IP pubblico del proxy SBC.

## <a name="central-sbc-with-centralized-trunks"></a>SBC centrale con trunk centralizzati

Per creare una soluzione in cui i servizi PSTN vengono forniti a tutte le filiali locali tramite un'unica funzionalità SBC centrale con un trunk SIP centralizzato connesso, l'amministratore del tenant Contoso associa un'unità SBC (centralsbc.contoso.com) al servizio. a SBC è collegato un trunk SIP centralizzato.

- Quando un utente si trova nella rete interna della società, L'SBC fornisce l'INDIRIZZO IP interno di SBC per i contenuti multimediali.

- Quando un utente si trova all'esterno della rete aziendale, l'SBC fornisce l'INDIRIZZO IP esterno (pubblico) di SBC.

> [!NOTE]
> Tutti i valori inclusi in esempi, tabelle o diagrammi vengono presentati solo a scopo di illustrazione.

Tabella 1. Parametri di rete di esempio per gli SBC

| Posizione | SBC FQDN | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Germania | Non distribuito | 192.168.6.0/24 | 172.16.76.74 | Non distribuito |  Non distribuito |
| Francia | Non distribuito | 192.168.7.0/24 | 172.16.76.75 | Non distribuito |  Non distribuito |

### <a name="internal-user"></a>Utente interno

Il diagramma seguente mostra il flusso del traffico quando un utente è connesso alla rete aziendale nella filiale o nel sito principale dell'utente.

In locale, l'utente viene assegnato alla filiale locale in Germania. L'utente effettua una chiamata telefonica instradamento diretto tramite Teams.

- Il client Teams dell'utente comunica al sistema telefonico direttamente tramite l'API REST, ma il supporto generato durante la chiamata passa all'indirizzo IP interno della SBC centrale.

- SBC reindirizza il flusso a Sistema telefonico e alla rete PSTN connessa.

- La scheda SBC centrale è visibile solo al sistema telefonico tramite l'indirizzo IP esterno.

Diagramma 1. Flusso del traffico quando l'utente si trova nel sito "home" con una scheda SBC centralizzata e un trunk SIP centralizzato connesso

![Diagramma che mostra il flusso del traffico Ottimizzazione multimediale locale.](media/direct-routing-media-op-1.png "Flusso del traffico quando l'utente si trova nel sito &quot;home&quot; con SBC centralizzato con trunk SIP centralizzato connesso")


### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso del traffico quando un utente non è locale e non è connesso alla rete aziendale, ovvero il dispositivo dell'utente è connesso a Internet tramite un dispositivo mobile o una rete Wi-Fi pubblica. L'utente effettua una chiamata telefonica instradamento diretto tramite Teams:

- Il client Teams dell'utente comunica al sistema telefonico direttamente tramite l'API REST, ma, in questo caso, il supporto generato durante la chiamata scorre verso l'indirizzo IP esterno della SBC centrale.

- SBC reindirizza il flusso a Sistema telefonico e alla rete PSTN connessa.

- La scheda SBC centrale è visibile solo al sistema telefonico tramite l'indirizzo IP esterno.

In questo caso, il comportamento è simile se l'utente è locale per la succursale in Germania o per qualsiasi altra filiale. L'utente viene considerato esterno perché l'utente è al di fuori dei limiti della rete aziendale.

Diagramma 2. Flusso del traffico quando l'utente è esterno con una scheda SBC centralizzata e con un trunk SIP centralizzato connesso

![Il diagramma mostra il flusso del traffico Ottimizzazione multimediale locale.](media/direct-routing-media-op-2.png "Flusso del traffico quando l'utente è esterno in caso di SBC centralizzato con trunk SIP centralizzato connesso")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy con SBC a valle connessi

Per creare una soluzione in cui i servizi PSTN vengono forniti in tutte le succursali locali nell'area APAC in cui la centralizzazione dei trunk TDM non è un'opzione, l'amministratore Contoso associa un SBC (proxysbc.contoso.com), denominato anche SBC proxy, al servizio di routing diretto.

In seguito, l'amministratore di Contoso aggiunge alcuni SBC a valle che indicano che è possibile raggiungersi tramite il proxysbc.contoso.com SBC proxy. Gli SBC a valle non hanno IP pubblici, tuttavia, possono essere assegnati alle route vocali. La tabella seguente mostra i parametri di rete e la configurazione di esempio.

Quando un utente si trova nella filiale locale in cui si trova l'SBC a valle, il traffico multimediale scorre direttamente tra l'utente e l'SBC a valle locale. Se un utente è al di fuori dell'ufficio (su una rete Internet pubblica), il flusso multimediale dall'utente all'INDIRIZZO IP pubblico del proxy SBC, che lo rende proxy agli SBC a valle pertinenti.

Tabella 2. Esempio di informazioni sulla rete SBC

| Posizione | SBC FQDN | Subnet interna | NAT esterno (IP attendibile) | Indirizzo IP esterno SBC  | Indirizzo IP interno SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Nessuno |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Nessuno |  192.168.2.5 |
| Singapore | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Utente interno

Il diagramma seguente mostra il flusso di traffico generale per lo scenario in cui un utente si trova all'interno dell'ufficio nell'area APAC.
L'utente, che è assegnato a una filiale locale in Vietnam ed è in locale, effettua una chiamata telefonica direct routing tramite Teams.

- Il client Teams dell'utente comunica con Sistema telefonico direttamente tramite l'API REST, ma i supporti generati durante la chiamata passano all'indirizzo IP interno di SBC locale.

- L'SBC locale reindirizza il flusso al proxy SBC a Singapore e alla rete PSTN locale connessa.

-  Il proxy SBC è visibile al sistema telefonico solo attraverso l'indirizzo IP esterno e instrada il flusso dalla SBC a valle (in questo caso la SBC locale in Vietnam) al sistema telefonico.

- La scheda SBC a valle nella filiale locale non è visibile direttamente al sistema telefonico, ma viene mappata all'interno della topologia di rete virtuale definita dall'amministratore Contoso durante la configurazione di Ottimizzazione multimediale locale.

> [!NOTE]
> Il comportamento potrebbe essere diverso per gli utenti locali e non locali a seconda della modalità di ottimizzazione multimediale locale configurata.

Per ulteriori informazioni sulle possibili modalità e sul comportamento pertinente, vedi Configurare Ottimizzazione multimediale locale.

Diagramma 3. Flusso di traffico quando l'utente si trova nella rete "domestica" con un SBC proxy e con SBC a valle connessi

![Diagramma che mostra di nuovo il flusso di traffico Ottimizzazione multimediale locale.](media/direct-routing-media-op-3.png "Traffic flow in case of proxy SBC with connected downstream SBCs when user is in the \"home\" network")

### <a name="external-user"></a>Utente esterno

Il diagramma seguente mostra il flusso del traffico quando un utente è al di fuori dei confini della rete aziendale. L'utente non è locale (non rientra nei limiti della rete aziendale). L'utente effettua una chiamata telefonica instradamento diretto tramite Teams a un numero di telefono in Vietnam.

- Il client Teams dell'utente comunica con sistema telefonico direttamente tramite l'API REST, ma il supporto generato durante la chiamata scorre prima verso l'indirizzo IP esterno del proxy SBC a Singapore.

- In base ai criteri di configurazione e voce (vedere [Configurare Ottimizzazione multimediale locale](direct-routing-media-optimization-configure.md) per i dettagli), il proxy SBC reindirizza il flusso alla SBC a valle in Vietnam.

- La SBC a valle in Vietnam reindirizza il flusso alla rete PSTN locale connessa.

- L'SBC proxy è visibile solo al sistema telefonico tramite l'indirizzo IP esterno.

-  La scheda SBC a valle nella filiale locale non è visibile direttamente a Sistema telefonico, ma è mappata all'interno della topologia di rete virtuale definita dall'amministratore contoso durante la configurazione di Ottimizzazione multimediale locale. Nell'esempio l'utente viene considerato esterno perché non rientra nei limiti della rete aziendale.

Diagramma 4. Flusso del traffico quando l'utente è esterno con un SBC proxy e con SBC a valle connessi

![Il diagramma mostra di nuovo il flusso di traffico Ottimizzazione multimediale locale.](media/direct-routing-media-op-4.png "Flusso del traffico nel caso di SBC proxy con SBC a valle connessi quando l'utente è esterno")

## <a name="local-media-optimization-modes"></a>Modalità ottimizzazione multimediale locale

Ottimizzazione multimediale locale supporta due modalità:

- **Modalità 1: ignora sempre**. In questo caso, se l'utente è interno, il supporto scorre attraverso l'indirizzo IP interno di SBC locale a valle indipendentemente dalla posizione effettiva dell'utente interno; ad esempio, all'interno della stessa filiale in cui si trova l'SBC a valle o in un'altra filiale.

- **Modalità 2: solo per gli utenti locali**. In questa modalità, i supporti fluiranno direttamente verso l'indirizzo IP interno di SBC locale a valle solo se generati dall'utente interno situato nella stessa filiale della SBC a valle.

Per distinguere tra le modalità di Ottimizzazione multimediale locale, l'amministratore del tenant deve impostare il parametro -BypassMode su "Always" o "OnlyForLocalUsers" per ogni SBC usando il cmdlet Set-CSonlinePSTNGateway. Per ulteriori informazioni, vedi [Configurare Ottimizzazione multimediale locale](direct-routing-media-optimization-configure.md).

> [!NOTE]
> Quando gli utenti sono interni, è **necessaria** la connettività dei supporti tra l'utente e SBC tramite l'indirizzo IP interno. Non esiste alcun fallback ai relè di trasporto pubblico per i media in questo caso in quanto la SBC fornirà un IP interno per la connettività media.

### <a name="mode-1-always-bypass"></a>Modalità 1: ignorare sempre

Se la connessione tra le filiali è buona, la modalità consigliata è Ignora sempre.

Ad esempio, si supponga che una società abbia un trunk SIP centralizzato ad Amsterdam, che serve 30 paesi e ha una buona connettività tra tutti i 30 siti e gli utenti locali. C'è anche un ramo in Germania in cui viene distribuita una SBC locale.

La scheda SBC in Germania può essere configurata in modalità "Ignora sempre". Gli utenti, indipendentemente dalla loro posizione, si connetteranno a SBC direttamente tramite l'indirizzo IP interno dell'SBC (ad esempio dalla Francia alla Germania; per riferimento, vedere il diagramma seguente).

Di seguito sono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione dell'SBC definito nei criteri di routing vocale online.

- Scenario 2. L'utente e i gateway si trovano in siti diversi.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione dell'SBC definito nei criteri di routing vocale online

L'SBC di Amsterdam è configurato come proxy SBC per una SBC locale a valle in Germania. L'utente si trova in Germania nella stessa subnet della rete aziendale della SBC locale. Sia gli SBC (proxy che a valle) sono configurati per la modalità Sempre bypass. I criteri di routing vocale online specificano che nel caso di chiamate in Germania (con prefisso +49) devono essere indirizzati alla SBC locale in Germania. Tutte le altre chiamate - e nel caso in cui la SBC in Germania fallisca, chiamate in Germania - devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione dell'esempio.

Tabella 3. Configurazione di esempio per lo scenario 1

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale |
|:------------|:-------|:-------|:-------|:-------|
| Germania | +49 1 437 2800 | Priorità 1: ^\+49(\d{8})$ -DEsbc.contoso.com<br>Priorità 2: .* - proxysbc.contoso.com| DEsbc.contoso.com - Ignora sempre <br>proxysbc.contoso.com - Ignora sempre | <-> DEsbc.contoso.com utenti di Teams |

Il diagramma seguente mostra il flusso di traffico ad alto livello per l'utente interno in Germania che effettua una chiamata telefonica direct routing attraverso Teams al numero in Germania.

- Il client Teams dell'utente comunica con Sistema telefonico direttamente tramite l'API REST.

- Il supporto generato durante il flusso della chiamata verso l'indirizzo IP interno della SBC locale.

- La SBC locale reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa.

- Il proxy SBC è visibile al sistema telefonico solo attraverso l'indirizzo IP esterno e indirizza il flusso dalla SBC a valle (in questo caso, la SBC locale in Germania) al sistema telefonico.

- La scheda SBC a valle nella filiale locale non è visibile direttamente al sistema telefonico, ma viene mappata all'interno della topologia di rete virtuale definita dall'amministratore Contoso durante la configurazione di Ottimizzazione multimediale locale.


Diagramma 5.  Flusso del traffico con modalità "Bypass sempre" e l'utente si trova nel sito "home"

! [Diagramma che mostra il flusso del traffico Ottimizzazione multimediale locale.] (media/direct-routing-media-op-5.png "Flusso di traffico con modalità "Bypass sempre" e l'utente si trova nel sito "home")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2: l'utente e i gateway si trovano in siti diversi

L'SBC di Amsterdam è configurato come proxy SBC per una SBC locale a valle in Germania. Sia gli SBC (proxy che a valle) sono configurati per la modalità Sempre bypass. L'utente interno in Francia, situato nella filiale locale, sta effettuando una chiamata di instradamento diretto in Germania. I criteri di routing vocale online specificano che le chiamate in Germania (con prefisso +49) devono essere indirizzate alla SBC locale in Germania. Tutte le altre chiamate - e, nel caso in cui la SBC in Germania fallisca, tutte le chiamate in Germania - devono essere indirizzate al proxy SBC di Amsterdam. La tabella seguente riepiloga la configurazione dell'esempio.

Tabella 4. Configurazione di esempio per lo scenario 2

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale |
|:------------|:-------|:-------|:-------|:-------|
| Francia | +49 1 437 2800 | Priorità 1: ^\+49(\d{8})$ -DEsbc.contoso.com <br>Priorità 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com - Bypassare sempre proxysbc.contoso.com - Bypassare sempre | < utenti di Teams- > DEsbc.contoso.com  |

Il diagramma seguente mostra il flusso di traffico ad alto livello quando l'utente tedesco interno in Francia effettua una chiamata telefonica di instradamento diretto attraverso Teams al numero in Germania.

- Il client Teams dell'utente comunica con Sistema telefonico direttamente tramite l'API REST.

- I supporti generati durante la chiamata fluiscono direttamente alla SBC nell'indirizzo IP interno tedesco.

- SBC in Germania reindirizza il flusso al proxy SBC di Amsterdam e alla rete PSTN locale connessa.

Diagramma 6.  Flusso del traffico con modalità "Bypass sempre" e l'utente non è nel sito "home" ma nella rete interna

! [Un diagramma mostra il flusso del traffico Ottimizzazione multimediale locale.] (media/direct-routing-media-op-6.png "Flusso di traffico con modalità "Bypass sempre" e l'utente non è nel sito "home", ma nella rete interna")

### <a name="mode-2-only-for-local-users"></a>Modalità 2: Solo per gli utenti locali

Se ci sono collegamenti non validi tra le filiali locali ma buone connessioni tra ogni filiale locale e l'ufficio locale, la modalità consigliata è "Solo per gli utenti locali".

Ad esempio, nell'area APAC, si supponga che Contoso abbia più uffici in paesi diversi. Per molti paesi, il passaggio a SIP non è possibile perché l'azienda dispone ancora di trunk TDM in molte filiali locali. La centralizzazione dei trunk TDM non è un'opzione nell'area APAC. Inoltre, nell'area APAC sono presenti più di 50 filiali Contoso con centinaia di gateway (SBC).

Per creare una soluzione in cui i servizi PSTN vengono forniti in tutte le filiali locali nell'area APAC in cui la centralizzazione dei trunk TDM non è un'opzione, l'amministratore di Contoso associa una SBC locale a Singapore come proxy SBC al servizio di routing diretto. La connessione diretta tra le filiali locali non è buona, ma c'è un buon collegamento tra ogni filiale locale e la SBC regionale a Singapore. Per l'SBC regionale, l'amministratore sceglie la modalità "Always Bypass" e per le SBC locali a valle l'amministratore sceglie la modalità "Solo per gli utenti locali".

Di seguito sono descritti due scenari:

- Scenario 1. L'utente si trova nella stessa posizione dell'SBC definito nei criteri di routing vocale online

- Scenario 2. L'utente e i gateway si trovano in siti diversi

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Scenario 1. L'utente si trova nella stessa posizione della scheda SBC definita nei criteri di routing vocale online

Si supponga che la SBC a Singapore sia configurata come SBC proxy per gli SBC locali a valle in Vietnam e Indonesia. L'utente si trova in Vietnam nella stessa posizione della SBC locale. I criteri di routing vocale online specificano che le chiamate in Vietnam (con prefisso +84) devono essere indirizzate alla SBC locale in Vietnam. Tutte le altre chiamate - e, se la SBC in Vietnam fallisce, chiamate in Vietnam - dovrebbero essere indirizzate al proxy SBC a Singapore. La tabella seguente riepiloga la configurazione dell'esempio.

Tabella 5. Configurazione di esempio per lo scenario 1 della modalità "Solo per utenti locali"

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorità 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br>Priorità 2: .* - proxysbc.contoso.com | VNsbc.contoso.com - Solo per utenti locali <br> proxysbc.contoso.com - Ignora sempre | < utenti di Teams- > VNsbc.contoso.com |

Nel diagramma seguente, un utente assegnato alla filiale locale in Vietnam, mentre è in locale, effettua una chiamata telefonica direct routing tramite Teams.

- Il client Teams dell'utente comunica con Sistema telefonico direttamente tramite l'API REST.

- Elementi multimediali generati durante il flusso della chiamata verso l'indirizzo IP interno della SBC locale.

- L'SBC locale reindirizza il flusso al proxy SBC a Singapore e alla rete PSTN locale connessa.

- Il proxy SBC è visibile al sistema telefonico solo attraverso l'indirizzo IP esterno e instrada il flusso dalla SBC a valle (in questo caso, la SBC locale in Vietnam) a Sistema telefonico.

- L'SBC a valle nella filiale locale non è visibile direttamente a Sistema telefonico, ma è mappato all'interno della topologia della rete virtuale.

Diagramma 7. Flusso del traffico con modalità "Solo per utenti locali" e l'utente è nel sito "home"

! [Un altro diagramma che mostra il flusso del traffico Ottimizzazione multimediale locale.] (media/direct-routing-media-op-7.png "Flusso di traffico con modalità "Solo per utenti locali" e l'utente è nel sito "home")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scenario 2. L'utente e i gateway si trovano in siti diversi

Si supponga che la SBC a Singapore sia configurata come SBC proxy per gli SBC locali a valle in Vietnam e Indonesia. L'utente interno in Indonesia, situato nella filiale locale, sta effettuando una chiamata di routing diretto in Vietnam. I criteri di routing voce online specificano che le chiamate in Vietnam (con prefisso +84) devono essere indirizzate alla SBC locale in Vietnam. Tutte le altre chiamate - e, nel caso in cui la SBC in Vietnam fallisca, chiamate in Vietnam - dovrebbero essere indirizzate al proxy SBC a Singapore. Il proxy SBC a Singapore è impostato su 'Sempre Bypass' modalità, e la SBC locale in Vietnam è impostata su 'Solo per gli utenti locali' modalità. La tabella seguente riepiloga la configurazione dell'esempio.

Tabella 6. Configurazione utente

| Posizione fisica dell'utente | Un utente effettua una chiamata a un numero | Criteri di routing vocale online | Modalità configurata per SBC | Flusso multimediale |
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | +84 4 3926 3000 | Priorità 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com |VNsbc.contoso.com - Solo per utenti locali <br> proxysbc.contoso.com - Ignora sempre | < utenti di Teams- > proxysbc.contoso.com < - > VNsbc.contoso.com |


Nel diagramma seguente, l'utente interno, mentre si trova nella filiale indonesiana, effettua una chiamata telefonica di instradamento diretto attraverso Teams a un numero in Vietnam.

- Il client Teams dell'utente comunica con Sistema telefonico direttamente tramite l'API REST.

- Elementi multimediali generati durante il flusso della chiamata verso l'indirizzo IP interno di SBC del proxy.

- Il proxy SBC a Singapore reindirizza il flusso all'indirizzo IP interno della SBC a valle in Vietnam e a Sistema telefonico.

- La SBC a valle in Vietnam instrada il flusso alla rete PSTN locale connessa.

- L'SBC proxy è visibile solo al sistema telefonico tramite l'indirizzo IP esterno.

- Gli SBC a valle nelle filiali locali non sono visibili direttamente nel sistema telefonico, ma sono mappati all'interno della topologia della rete virtuale.

Diagramma 8.  Flusso del traffico con modalità "Solo per utenti locali" e l'utente non è nel sito "home" ma nella rete interna

! [Un altro diagramma mostra il flusso del traffico Ottimizzazione multimediale locale.] (media/direct-routing-media-op-8.png "Flusso di traffico con modalità "Solo per utenti locali", l'utente non è nel sito "home" ma nella rete interna")

## <a name="known-issues"></a>Problemi noti

Di seguito è riportato un elenco dei problemi noti attualmente presenti in Ottimizzazione multimediale locale. Microsoft sta lavorando per risolvere questi problemi.

| Problema | Soluzione |
| :--- | :--- |
| Il client Teams non viene identificato come **interno** quando l'IP pubblico del client Teams corrisponde all'elenco IP attendibile del cliente. | Ottimizzazione multimediale locale richiede che la subnet client di Teams corrisponda a una [subnet di rete](/powershell/module/skype/new-cstenantnetworksubnet) configurata dal tenant|
| Le riassegnazioni delle chiamate provocano l'caduta delle chiamate quando il client teams viene identificato come interno.| Disabilitare Ottimizzazione multimediale locale in Direct Routing SBC.|
| Le riassegnazioni delle chiamate da 1 a 1 chiamata tra i clienti interni a una chiamata a più parti con cliente esterno/risorsa provocano chiamate interrotte | Lavora in corso per una correzione. In alternativa, disabilitare Ottimizzazione multimediale locale in Direct Routing SBC.|
| L'utente di Teams mette la chiamata in attesa. La musica viene riprodotta da PSTN e Ottimizzazione multimediale locale funziona. L'utente di Teams riprende la chiamata. La chiamata a PSTN riprende ma Ottimizzazione multimediale locale non funziona e la chiamata continua tramite SBC centrale (proxy) | Quando un utente effettua una chiamata per avviare una musica in attesa (MoH), viene inoltrata da 1:1 a una chiamata multiparty da parte del controller di chiamata per richiamare Media Controller e Media Processor (che funge da mixer AVMCU) attraverso il quale MoH raggiunge un utente che è stato messo in attesa. L'escalation a una chiamata 1:1 dopo il curriculum della chiamata non avviene mai come da progettazione. Disabilitare Ottimizzazione multimediale locale in Direct Routing SBC.|
|Mentre viene stabilita una chiamata per alcuni secondi, l'utente potrebbe sentire il silenzio.| A causa della complessità dell'architettura di Ottimizzazione multimediale locale, questo può verificarsi in alcuni casi.Due to the complexity of Local Media Optimization architecture, this might occur in some cases.|
|Le app vocali (ad esempio Operatore automatico, Coda di chiamata) non funzionano.| LMO non supporta le app vocali, perché risiedono nel cloud e richiedono la connettività esterna. Per il momento non è disponibile alcuna soluzione alternativa.|
