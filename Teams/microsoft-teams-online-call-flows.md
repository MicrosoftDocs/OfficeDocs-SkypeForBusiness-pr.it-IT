---
title: Flussi di chiamata in Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Informazioni su Teams flussi Office 365 in varie topologie, oltre a flussi univoci del team usati per la comunicazione multimediale peer-to-peer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f152caaa90562a5223590ebcf97623646237e40
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727845"
---
# <a name="microsoft-teams-call-flows"></a>Flussi di chiamata in Microsoft Teams

> [!TIP]
> Guardare questa sessione per informazioni su Teams la rete e su come pianificare la connettività di rete ottimale: Teams [pianificazione della rete.](https://aka.ms/teams-networking)

## <a name="overview"></a>Panoramica

Questo articolo descrive come Teams Microsoft 365 o Office 365 delle chiamate in varie topologie. Descrive inoltre i flussi di Teams univoci usati per la comunicazione multimediale peer-to-peer. Il documento descrive questi flussi, il loro scopo e la loro origine e terminazione nella rete. Ai fini di questo articolo, si supponga di quanto segue:

- Flow X viene usato dal client locale per comunicare con il servizio Microsoft 365 o Office 365 nel cloud. Proviene dalla rete del cliente e termina come endpoint in Microsoft 365 o Office 365.

- Flow Y viene usato dal client locale per comunicare con un servizio su Internet da cui Microsoft 365 o Office 365 ha una dipendenza. Proviene dalla rete del cliente e termina come endpoint su Internet.

Questo articolo illustra le informazioni seguenti:

- **Sfondo**. Fornisce informazioni di base, ad esempio le reti che i flussi possono attraversare, i tipi di traffico, le indicazioni sulla connettività dalla rete del cliente agli endpoint del servizio Microsoft 365 o Office 365, l'interoperabilità con componenti di terze parti e i principi usati da Teams per selezionare i flussi multimediali.

- **I flussi delle chiamate in varie topologie**. Illustra l'uso dei flussi di chiamata in varie topologie. Per ogni topologia, la sezione enumera tutti i flussi supportati e illustra come questi flussi vengono usati in diversi casi di utilizzo. Per ogni caso di utilizzo, descrive la sequenza e la selezione dei flussi usando un diagramma di flusso.

- **Teams con l'ottimizzazione Express Route.** Descrive come vengono usati questi flussi quando Express Route viene distribuito per l'ottimizzazione, illustrato usando una topologia semplice.

## <a name="background"></a>Sfondo

### <a name="network-segments"></a>Segmenti di rete

**Rete clienti**. Questo è il segmento di rete che controlli e gestisci. Sono incluse tutte le connessioni dei clienti all'interno degli uffici dei clienti, sia cablate che wireless, connessioni tra edifici di uffici, connessioni a data center locali e connessioni a provider Internet, Express Route o qualsiasi altro peering privato.

In genere, una rete clienti ha diversi perimetri di rete con firewall e/o server proxy, che applicano i criteri di sicurezza dell'organizzazione e che consentono solo il traffico di rete configurato e configurato. Poiché si gestisce questa rete, si ha il controllo diretto sulle prestazioni della rete ed è consigliabile completare le valutazioni della rete per convalidare le prestazioni sia all'interno dei siti della rete che dalla rete alla rete Microsoft 365 o Office 365.

**Internet**. Questo è il segmento di rete che fa parte della rete generale che verrà usato dagli utenti che si connettono a Microsoft 365 o Office 365 dall'esterno della rete del cliente. Viene usato anche da parte del traffico dalla rete del cliente a Microsoft 365 o Office 365.

**Rete privata visitata o guest**. Si tratta del segmento di rete esterno alla rete dei clienti, ma non in Internet pubblico, che gli utenti e i loro guest possono visitare,ad esempio una rete privata domestica o una rete privata aziendale, che non distribuisce Teams, in cui possono risiedere gli utenti e i clienti che interagiscono con i servizi Teams.

> [!NOTE]
> La connettività Microsoft 365 o Office 365 è applicabile anche a queste reti.

**Microsoft 365 o Office 365**. Questo è il segmento di rete che supporta Microsoft 365 o Office 365 servizi. È distribuito in tutto il mondo con bordi vicini alla rete dei clienti nella maggior parte delle località. Le funzioni includono Transport Relay, Conferencing Server e Media Processor.

**Express Route (facoltativo)**. Questo è il segmento di rete che fa parte della rete generale che ti darà una connessione privata dedicata alla rete Microsoft 365 o Office 365 rete.

### <a name="types-of-traffic"></a>Tipi di traffico

**Elementi multimediali in tempo reale**. Dati incapsulati all'interno del protocollo RTP (Real-time Transport Protocol) che supportano carichi di lavoro audio, video e di condivisione dello schermo. In generale, il traffico multimediale è altamente sensibile alla latenza, quindi è consigliabile che il traffico prenda il percorso più diretto possibile e usi UDP e TCP come protocollo a livello di trasporto, che è il trasporto migliore per supporti interattivi in tempo reale da una prospettiva qualitativa. Si noti che, come ultima risorsa, i supporti multimediali possono usare TCP/IP ed essere anche oggetto di tunneling all'interno del protocollo HTTP, ma non è consigliabile a causa di implicazioni di qualità scarsa. Il flusso RTP è protetto tramite SRTP, in cui solo il payload è crittografato.

**Segnalazione**. Il collegamento di comunicazione tra il client e il server o altri client usati per controllare le attività, ad esempio quando viene avviata una chiamata, e recapitare messaggi istantanei. La maggior parte del traffico di segnalazione usa le interfacce REST basate su HTTPS, anche se in alcuni scenari, ad esempio la connessione tra Microsoft 365 o Office 365 e un session border controller, usa il protocollo SIP. È importante tenere presente che questo traffico è molto meno sensibile alla latenza, ma può causare interruzioni del servizio o timeout delle chiamate se la latenza tra gli endpoint supera alcuni secondi.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Connettività a Microsoft 365 o Office 365

Teams richiede [connettività a Internet.](/office365/enterprise/assessing-network-connectivity) Teams URL degli endpoint e intervalli di indirizzi IP sono elencati negli URL Office 365 e negli intervalli [di indirizzi IP.](/office365/enterprise/urls-and-ip-address-ranges) Tenere presente che è necessaria la connettività aperta alle porte TCP 80 e 443 e alle porte UDP da 3478 a 3481. Inoltre, Teams ha una dipendenza da Skype for Business Online, che deve essere connesso anche a Internet.

Teams la connettività dei flussi multimediali viene implementata usando le procedure ice (Interactive Connectivity Establishment) standard di IETF.

### <a name="interoperability-restrictions"></a>Restrizioni di interoperabilità

**Relè multimediali di terze parti**. Un Teams multimediale, ovvero in cui uno degli endpoint multimediali è Teams) può attraversare solo Teams o Skype for Business multimediali nativi. L'interoperabilità con un relay multimediale di terze parti non è supportata. Si noti che un SBC di terze parti sul confine con PSTN deve terminare lo stream RTP/RTCP, protetto con SRTP e non inoltrarlo all'hop successivo.

**Server proxy SIP di terze parti**. Una Teams di segnalazione SIP con un SBC e/o un gateway di terze parti può attraversare Teams o Skype for Business proxy SIP nativi. L'interoperabilità con un proxy SIP di terze parti non è supportata.

**B2BUA (o SBC)** di terze parti. Un Teams flusso multimediale da e verso la rete PSTN viene terminato da un SBC di terze parti. Tuttavia, l'interoperabilità con un SBC di terze parti all'interno della rete Teams (in cui una SBC di terze parti media due endpoint Teams o Skype for Business) non è supportata.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologie non consigliate con Microsoft Teams

**Rete VPN**. Non è consigliabile per il traffico multimediale (o il flusso 2'). Il client VPN deve usare il split tunneling e instradare Teams traffico multimediale come qualsiasi utente esterno non VPN, come specificato in Abilitazione dei supporti multimediali di Lync per ignorare [un tunnel VPN.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)

> [!NOTE]
> Anche se il titolo indica Lync, è applicabile anche Teams.

**Formatori di pacchetti**. Qualsiasi tipo di dispositivo di snipper di pacchetti, ispezione pacchetti o shaper di pacchetti non è consigliato per il traffico multimediale Teams e può degradare in modo significativo la qualità.

### <a name="principles"></a>Principi

Esistono quattro principi generali che consentono di comprendere i flussi delle chiamate per Microsoft Teams:

- Una Microsoft Teams è ospitata da Microsoft 365 o Office 365 nella stessa area geografica in cui si è unito il primo partecipante. Se in alcune topologie sono presenti eccezioni a questa regola, queste verranno descritte in questo documento e illustrate da un flusso di chiamate appropriato.

- Un Teams endpoint multimediale in Microsoft 365 o Office 365 viene usato in base alle esigenze di elaborazione dei supporti multimediali e non in base al tipo di chiamata. Ad esempio, una chiamata point-to-point può usare un endpoint multimediale nel cloud per elaborare elementi multimediali per la trascrizione o la registrazione, mentre una conferenza con due partecipanti potrebbe non usare alcun endpoint multimediale nel cloud. Tuttavia, la maggior parte delle conferenze userà un endpoint multimediale per la combinazione e il routing, allocato dove è ospitata la conferenza. Il traffico multimediale inviato da un client all'endpoint multimediale può essere instradato direttamente o usare un inoltro di trasporto in Microsoft 365 o Office 365, se necessario a causa delle restrizioni del firewall di rete del cliente.

- Il traffico multimediale per le chiamate peer-to-peer prende il percorso più diretto disponibile, presupponendo che la chiamata non impone un endpoint multimediale nel cloud (vedere il principio precedente). La route preferita è diretta al peer remoto (client), ma se tale route non è disponibile, uno o più relay di trasporto inoltrano il traffico. È consigliabile che il traffico multimediale non inverti server come i packet shaper, i server VPN e così via, in quanto questo influisce sulla qualità dei supporti.

- Il traffico di segnalazione passa sempre al server più vicino all'utente.

Per altre informazioni sui dettagli sul percorso multimediale scelto, vedere Informazioni sui flussi multimediali in Microsoft Teams [- BRK4016.](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>Flussi delle chiamate in varie topologie

### <a name="teams-topology"></a>Teams topologia

Questa topologia viene usata dai clienti che sfruttano i servizi di Teams dal cloud senza alcuna distribuzione locale, ad esempio Skype for Business Server o Sistema telefonico Routing diretto. Inoltre, l'interfaccia per Microsoft 365 o Office 365 viene eseguita tramite Internet senza Azure Express Route.

[![Microsoft Teams Flusso delle chiamate online Figura 01.](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1 - Teams topologia*

Tenere presente che:

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività ai perimetri aziendali. Nel caso di UDP per i supporti multimediali, i primi pacchetti potrebbero fluire nella direzione inversa, ma questi pacchetti potrebbero essere bloccati fino a quando non scorrono pacchetti nella direzione opposta.
- Teams viene distribuito affiancato a Skype for Business Online, quindi i client vengono visualizzati come "utente Teams/SFB".

Altre informazioni sulle topologie facoltative seguenti sono disponibili più avanti nell'articolo:

- Skype for Business la distribuzione locale è descritta in Teams **topologia ibrida.**
- Sistema telefonico Il routing diretto (per la connettività PSTN) è descritto in **Teams con la topologia Routing diretto**.
- Express Route è descritto in Teams **con l'ottimizzazione Express Route.**

**Flow descrizioni:**

- **Flow 2:** rappresenta un flusso avviato da un utente nella rete del cliente verso Internet come parte dell'esperienza Teams'utente. Esempi di questi flussi sono i supporti DNS e peer-to-peer.
- **Flow 2':** rappresenta un flusso avviato da un utente Teams cellulare remoto, con VPN alla rete del cliente.
- **Flow 3:** rappresenta un flusso avviato da un utente Teams mobile remoto per Microsoft 365 o Office 365/Teams endpoint.
- **Flow 4:** rappresenta un flusso avviato da un utente nella rete del cliente per Microsoft 365 o Office 365/Teams endpoint.
- **Flow 5:** rappresenta un flusso multimediale peer-to-peer tra un utente di Teams e un altro utente Teams o Skype for Business all'interno della rete del cliente.
- **Flow 6:** rappresenta un flusso multimediale peer-to-peer tra un utente di Teams mobile remoto e un altro utente Teams o Skype for Business mobile remoto tramite Internet.

#### <a name="use-case-one-to-one"></a>Caso d'uso: uno-a-uno

Le chiamate uno-a-uno usano un modello comune in cui il chiamante o ottiene un set di candidati costituiti da indirizzi IP/porte, inclusi i candidati locali, di inoltro e riflessivi (indirizzo IP pubblico del client come visto dall'inoltro). Il chiamante invia questi candidati alla parte chiamata; la parte chiamata ottiene anche un set simile di candidati e li invia al chiamante. I messaggi di controllo della connettività STUN vengono usati per trovare i percorsi multimediali del chiamante/chiamato parte e il percorso di lavoro migliore è selezionato. I supporti multimediali, ovvero i pacchetti RTP/RTCP protetti con SRTP, vengono quindi inviati usando la coppia di candidati selezionata. L'inoltro di trasporto viene distribuito come parte di Microsoft 365 e Office 365.

Se l'indirizzo IP locale/i candidati di porta o i candidati riflessivi hanno connettività, il percorso diretto tra i client (o con un NAT) verrà selezionato per i supporti multimediali. Se i client sono entrambi nella rete del cliente, è necessario selezionare il percorso diretto. Questa operazione richiede la connettività UDP diretta all'interno della rete del cliente. Se i client sono entrambi utenti del cloud nomadi, a seconda del NAT/firewall, i supporti multimediali possono usare la connettività diretta.

Se un cliente è interno alla rete del cliente e un cliente è esterno (ad esempio, un utente cloud mobile), è improbabile che la connettività diretta tra i candidati locali o riflessivi funzioni. In questo caso, un'opzione è quella di usare uno dei candidati dell'inoltro di trasporto da uno dei due client (ad esempio, il client interno ha ottenuto un candidato di inoltro dall'inoltro di trasporto in Microsoft 365 o Office 365; il client esterno deve essere in grado di inviare pacchetti STUN/RTP/RTCP all'inoltro di trasporto). Un'altra opzione è che il client interno invia al candidato di inoltro ottenuto dal client cloud mobile. Si noti che, anche se è altamente consigliata la connettività UDP per i supporti multimediali, è supportato TCP.

**Passaggi di alto livello:**

1. Teams L'utente risolve il nome di dominio URL (DNS) usando il flusso 2.
1. Teams L'utente A alloca una porta media Relay Teams transport relay usando il flusso 4.
1. Teams L'utente A invia "invito" con i candidati ICE usando il flusso 4 per Microsoft 365 o Office 365.
1. Microsoft 365 o Office 365 invia una notifica all Teams'utente B usando il flusso 4.
1. Teams L'utente B alloca una porta media Relay Teams transport relay usando il flusso 4.
1. Teams L'utente B invia una "risposta" con i candidati ICE usando il flusso 4, che viene inoltrato di nuovo Teams'utente A usando Flow 4.
1. Teams L'utente A e Teams utente B richiamano i test di connettività ICE e viene selezionato il percorso multimediale migliore disponibile (vedere i diagrammi seguenti per i vari casi di utilizzo).
1. Teams Gli utenti inviano dati di telemetria Microsoft 365 o Office 365 usando il flusso 4.

**All'interno della rete del cliente:**

[![Microsoft Teams Flusso delle chiamate online Figura 02.](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2 - All'interno della rete dei clienti*

Nel passaggio 7 è selezionato il flusso multimediale peer-to-peer 5.

L'elemento multimediale è bidirezionale. La direzione del flusso 5 indica che un lato avvia la comunicazione dal punto di vista della connettività, coerente con tutti i flussi in questo documento. In questo caso, non importa quale direzione viene usata perché entrambi gli endpoint si trova all'interno della rete del cliente.

**Rete del cliente a utente esterno (supporti inoltrati da Teams Transport Relay):**

[![Microsoft Teams Figura 03 Flussi di chiamate online.](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3 - Rete del cliente a un utente esterno (supporti inoltrati da Teams Transport Relay)*

Nel passaggio 7, il flusso 4, dalla rete del cliente a Microsoft 365 o Office 365, e il flusso 3, dall'utente remoto Teams mobile a Microsoft 365 o Office 365, sono selezionati. Questi flussi vengono inoltrati tramite Teams di trasporto all'interno Microsoft 365 o Office 365.

L'elemento multimediale è bidirezionale, dove la direzione indica quale lato avvia la comunicazione dal punto di vista della connettività. In questo caso, questi flussi vengono usati per la segnalazione e i supporti multimediali, usando protocolli e indirizzi di trasporto diversi.

**Rete del cliente a utente esterno (supporti diretti):**

[![Microsoft Teams Figura 04 Flussi delle chiamate online.](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4 - Rete dei clienti verso utenti esterni (supporti diretti)*

Nel passaggio 7 è selezionato il flusso 2, dalla rete del cliente a Internet (peer del cliente).

- Gli elementi multimediali diretti con utenti mobili remoti (non inoltrati tramite Microsoft 365 o Office 365) sono facoltativi. In altre parole, il cliente può bloccare questo percorso per applicare un percorso multimediale tramite l'inoltro di trasporto Microsoft 365 o Office 365.

- L'elemento multimediale è bidirezionale. La direzione del flusso 2 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

**Utente VPN a utente interno (supporto inoltrato da Teams Transport Relay)**

[![Microsoft Teams Figura 05 Flussi di chiamate online.](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5 - Utente VPN a utente interno (supporto inoltrato da Teams Transport Relay)*

La segnalazione tra la VPN e la rete del cliente usa il flusso 2'. La segnalazione tra la rete del cliente e Microsoft 365 o Office 365 utilizza il flusso 4. Tuttavia, i supporti multimediali ignorano la VPN e vengono instradati usando i flussi da 3 e 4 a Teams media relay in Microsoft 365 o Office 365.

**Da utente VPN a utente interno (supporto diretto)**

[![Microsoft Teams Flusso delle chiamate online Figura 06.](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6 - Da utente VPN a utente interno (supporto diretto)*

La segnalazione tra la VPN e la rete del cliente usa il flusso 2'. La segnalazione tra la rete del cliente e Microsoft 365 o Office 365 utilizza il flusso 4. Tuttavia, i supporti multimediali ignorano la VPN e vengono instradati usando il flusso 2 dalla rete del cliente a Internet.

L'elemento multimediale è bidirezionale. La direzione del flusso 2 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

**Da utente VPN a utente esterno (supporto diretto)**

[![Microsoft Teams flussi delle chiamate Figura 07.](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7 - Da utente VPN a utente esterno (supporto diretto)*

La segnalazione tra l'utente VPN alla rete del cliente usa il flusso 2' e il flusso da 4 a Microsoft 365 o Office 365. Tuttavia, i supporti multimediali ignorano la VPN e vengono instradati usando il flusso 6.

L'elemento multimediale è bidirezionale. La direzione del flusso 6 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Use Case: da Teams a PSTN tramite Microsoft 365 o Office 365 Trunk

Microsoft 365 e Office 365 hanno un Sistema telefonico che consente di effettuare e ricevere chiamate dalla rete PSTN (Public Switched Telephone Network). Se il trunk PSTN è connesso usando il piano Sistema telefonico chiamate, non ci sono requisiti di connettività speciali per questo caso d'uso. Se si vuole connettere il proprio trunk PSTN locale a Microsoft 365 o Office 365, è possibile usare Sistema telefonico Routing diretto.

[![Microsoft Teams Flusso delle chiamate online Figura 08.](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8 - Teams alla rete PSTN tramite Office 365 trunk*

#### <a name="use-case-teams-meeting"></a>Caso d'uso: Teams riunione

Il server di conferenza audio/video/condivisione dello schermo (VBSS) fa parte di Microsoft 365 e Office 365. Ha un indirizzo IP pubblico che deve essere raggiungibile dalla rete del cliente e deve essere raggiungibile da un client Cloud Nomadic. Ogni client/endpoint deve essere in grado di connettersi al server delle conferenze.

I client interni ottengono candidati locali, riflessivi e di inoltro nello stesso modo descritto per le chiamate uno-a-uno. I client invieranno questi candidati al server delle conferenze in un invito. Il server di conferenza non usa un inoltro perché ha un indirizzo IP accessibile pubblicamente, quindi risponde con il candidato dell'indirizzo IP locale. Il client e il server delle conferenze controllano la connettività nello stesso modo descritto per le chiamate uno-a-uno.

Tenere presente che:

- Teams non possono partecipare a Skype for Business riunioni e Skype for Business non possono partecipare a Teams riunioni.

- Un utente PSTN facoltativamente "Chiama IN" o è "Dialed OUT", a seconda del provisioning delle chiamate PSTN e/o dei servizi di conferenza dell'organizzatore della riunione.

- Un utente guest o un utente cliente può partecipare da una rete privata guest, che è protetta con FW/NAT con regole rigorose.

[![Microsoft Teams Flusso delle chiamate online Figura 09.](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9 - Teams riunione*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Use case: Federazione con Skype for Business locale

**Elementi multimediali inoltrati da Teams transport relay in Microsoft 365 o Office 365**

[![Microsoft Teams Flussi delle chiamate online Figura 10.](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10 - Elementi multimediali inoltrati da Teams di trasporto in Office 365*

Tenere presente che:

- La federazione è, per definizione, una comunicazione tra due tenant. In questo caso, il tenant A, che usa Teams, si federate con il tenant B, che usa Skype for Business locale. Se anche il tenant B usa Microsoft 365 o Office 365, il client Skype for Business avrebbe usato il flusso 3 per connettersi con Microsoft 365 o Office 365.

- La segnalazione e gli elementi multimediali dal client Skype for Business federato a un Skype for Business Server locale non sono nell'ambito di questo documento. Tuttavia, è illustrato qui per chiarezza.

- La segnalazione tra Teams e Skype for Business viene con bridge da un gateway.

- I supporti multimediali in questo caso vengono inoltrati Teams di trasporto alla rete del cliente e al client Skype for Business remoto usando il flusso 4.

**Media relayed by Skype for Business Media Relay in federated tenant**

[![Microsoft Teams Flussi delle chiamate online Figura 11.](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11 - Elementi multimediali inoltrati da Skype for Business Media Relay nel tenant federato*

Tenere presente che:

- Segnalazione ed elementi multimediali dal client Skype for Business federato a un Skype for Business Server locale non è in ambito di questo documento. Tuttavia, è illustrato qui per chiarezza.

- La segnalazione tra Teams e Skype for Business viene con bridge da un gateway.

- I supporti multimediali in questo caso vengono inoltrati Skype for Business media relay locale alla rete del cliente usando il flusso 2. Si noti che il traffico da Teams utente all'inoltro multimediale remoto nella rete del cliente federato verrà inizialmente bloccato da Media Relay finché il traffico nella direzione inversa non inizia a fluire. Tuttavia, il flusso bidirezionale aprirà la connettività in entrambe le direzioni.

**Direct (peer-to-peer)**

[![Microsoft Teams Flussi delle chiamate online Figura 12.](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12 - Direct (peer-to-peer)*

### <a name="teams-hybrid-topology"></a>Teams topologia ibrida

Questa topologia include Teams con una distribuzione Skype for Business locale.

[![Microsoft Teams Flusso delle chiamate online Figura 13.](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13 - Teams topologia ibrida*

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività ai perimetri aziendali. Nel caso di UDP per i supporti multimediali, i primi pacchetti potrebbero fluire nella direzione inversa, ma questi pacchetti potrebbero essere bloccati fino a quando non scorrono pacchetti nella direzione opposta.

- Teams viene distribuito affiancato a Skype for Business Online, quindi i client vengono visualizzati come "utente Teams/SFB".

Flusso aggiuntivo (sopra la Teams topologia):

- **Flow 5A:** rappresenta un flusso multimediale peer-to-peer tra un utente di Teams all'interno della rete del cliente e un inoltro multimediale locale di Skype for Business all'edge della rete del cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Use case: Teams per Skype for Business uno-a-uno

**Ibrida all'interno della rete del cliente**

[![Microsoft Teams Flusso delle chiamate online Figura 14.](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14 - Ibrida all'interno della rete dei clienti*

La segnalazione tra Teams e Skype for Business viene con bridge da un gateway. Tuttavia, i supporti multimediali vengono instradati direttamente peer-to-peer all'interno della rete del cliente usando il flusso 5.

**Rete dei clienti ibrida con utenti Skype for Business esterni, inoltrati da Microsoft 365 o Office 365**

[![Microsoft Teams Flusso delle chiamate online Figura 15.](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15 - Rete ibrida dei clienti con utenti Skype for Business esterni - inoltrati da Office 365*

Tenere presente che:

- La segnalazione e gli elementi multimediali dal client Skype for Business a un Skype for Business Server locale non sono nell'ambito di questo documento. Tuttavia, è illustrato qui per chiarezza.

- La segnalazione tra Teams e Skype for Business viene con bridge da un gateway.

- I supporti multimediali vengono inoltrati Teams l'inoltro di trasporto alla rete del cliente tramite il flusso 4.

**Rete dei clienti ibrida con utenti Skype for Business esterni , inoltrati da Edge locale**

[![Microsoft Teams Flusso delle chiamate online Figura 16.](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16 - Rete ibrida dei clienti con utenti Skype for Business esterni - inoltrati da Edge locale*

Tenere presente che:

- La segnalazione e gli elementi multimediali Skype for Business client a un Skype for Business Server locale non sono nell'ambito di questo documento. Tuttavia, è illustrato qui per chiarezza.

- La segnalazione viene con bridge da un gateway.

- I supporti multimediali vengono inoltrati da Skype for Business Media Relay all'interno di Skype for Business Edge locale a Teams utente all'interno della rete del cliente usando il flusso multimediale 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams con Sistema telefonico routing diretto

Questa topologia include le Teams con Sistema telefonico routing diretto.

Il routing diretto consente di usare un provider di servizi PSTN (Public Switched Telephone Network) di terze parti associando un dispositivo hardware SBC (Session Border Controller) di proprietà del cliente supportato a Microsoft 365 o Office 365 e quindi connettendo il trunk di telefonia a tale dispositivo.

Per supportare questo scenario, il cliente deve distribuire un SBC certificato per il routing diretto da uno dei partner certificati Microsoft. L'SBC deve essere configurato come consigliato dal fornitore e deve essere instradabile da Microsoft 365 o Office 365 per il traffico UDP diretto. I supporti multimediali possono fluire direttamente da Teams e/o dal client Skype for Business al gateway SBC (ignorando il gateway Teams) o attraversare il gateway Teams. La connettività con SBC, quando il trunk è configurato per ignorare il gateway Teams, si basa su ICE, dove SBC supporta ICE-Lite, mentre l'endpoint multimediale Teams/Skype for Business supporta ICE Full Form.

[![Microsoft Teams Flussi delle chiamate online Figura 17.](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17 - Teams con Sistema telefonico di routing diretto

Tenere presente che:

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività ai perimetri aziendali. Nel caso di UDP per i supporti multimediali, i primi pacchetti potrebbero fluire nella direzione inversa, ma questi pacchetti potrebbero essere bloccati fino a quando non scorrono pacchetti nella direzione opposta.

- Teams viene distribuito affiancato a Skype for Business Online, quindi i client vengono visualizzati come "utente Teams/SFB".

Flussi aggiuntivi (sopra la topologia Teams online):

- **Flow 4'** - Rappresenta un flusso da Microsoft 365 o Office 365 alla rete del cliente, usato per stabilire una connessione tra il server multimediale Teams nel cloud con il servizio SBC locale.
- **Flow 5B:** rappresenta un flusso multimediale tra l'utente Teams all'interno della rete del cliente con direct routing SBC in modalità bypass.
- **Flow 5C:** rappresenta un flusso multimediale tra il routing diretto SBC e un altro SBC di routing diretto in una modalità di bypass per le chiamate a tornanti PSTN.

**Utente interno con Routing diretto (supporti inoltrati da Teams Transport Relay)**

[![Microsoft Teams Flusso delle chiamate online Figura 18.](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18 - Utente interno con routing diretto (supporti inoltrati Teams Transport Relay)*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- La segnalazione e i supporti da SBC a Microsoft 365 o Office 365 e viceversa usano il flusso 4 e/o il flusso 4'.

- Segnalazione e supporto dal client all'interno della rete del cliente per Microsoft 365 o Office 365 usare il flusso 4.

**Utente remoto con routing diretto (i supporti vengono instradati tramite un server multimediale (MP))**

[![Microsoft Teams Flusso delle chiamate online Figura 19.](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19 - Utente remoto con routing diretto (i supporti vengono instradati tramite un server multimediale (MP))*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- La segnalazione e i supporti da SBC a Microsoft 365 o Office 365 e viceversa usano il flusso 4 e/o il flusso 4'.

- Segnalazione ed elementi multimediali dal client su Internet per Microsoft 365 o Office 365 usare il flusso 3.

**Routing diretto dell'utente interno (bypass multimediale)**

[![Microsoft Teams Flusso delle chiamate online Figura 20.](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20 - Routing diretto dell'utente interno (bypass multimediale)*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- La segnalazione da SBC a Microsoft 365 o Office 365 e viceversa usa il flusso 4 e/o il flusso 4'.

- Segnalazione da parte del cliente all'interno della rete del cliente Microsoft 365 o Office 365 il flusso 4.

- I supporti multimediali provenienti dal client all'interno della rete del cliente fino a SBC all'interno della rete del cliente usano il flusso 5B.

**Utente remoto con Routing diretto (bypass multimediale inoltrato da Teams di trasporto)**

[![Microsoft Teams Flussi delle chiamate online Figura 21.](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21 - Utente remoto con Routing diretto (bypass multimediale inoltrato Teams Transport Relay)*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365 Internet.

- La segnalazione da SBC a Microsoft 365 o Office 365 e viceversa usa il flusso 4 e/o il flusso 4'.

- La segnalazione da parte del client su Internet Microsoft 365 o Office 365 utilizza il flusso 3.

- I supporti multimediali dal client su Internet alla SBC all'interno della rete del cliente utilizzano i flussi 3 e 4, inoltrati da Teams Transport Relay.

**Routing diretto dell'utente remoto (bypass multimediale diretto)**

[![Microsoft Teams Flusso delle chiamate online Figura 22.](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22 - Routing diretto dell'utente remoto (bypass multimediale diretto)*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365 internet.

- La segnalazione da SBC a Microsoft 365 o Office 365 e viceversa usa il flusso 4 e/o il flusso 4'.

- La segnalazione da parte del client su Internet Microsoft 365 o Office 365 utilizza il flusso 3.

- I supporti multimediali dal client su Internet alla SBC all'interno della rete del cliente utilizzano il flusso 2.

**Routing diretto (bypass multimediale): chiamata per tornante PSTN (a causa di inoltro/trasferimento di chiamata)**

[![Microsoft Teams Flusso delle chiamate online Figura 23.](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23 - Routing diretto (bypass multimediale) - chiamata al tornante PSTN (a causa di inoltro/trasferimento di chiamata)*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- La segnalazione da SBC a Microsoft 365 o Office 365 e viceversa usa il flusso 4 e/o il flusso 4'.

- Il client è fuori dal ciclo di segnalazione e supporto dopo che la chiamata è stata bloccata da PSTN a PSTN.

- I supporti dall'istanza SBC A all'interno della rete del cliente all'istanza SBC B all'interno della rete del cliente (dove A e B possono essere la stessa istanza) usa il flusso 5C.

**Routing diretto (supporti tramite Microsoft 365 o Office 365) - chiamata per tornanti PSTN tra due tenant**

[![Microsoft Teams Flusso delle chiamate online Figura 24.](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figura 24 - Routing diretto (supporti tramite Microsoft 365 o Office 365) - Chiamata per tornanti PSTN tra due tenant*

Tenere presente che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- La segnalazione da SBC a Microsoft 365 o Office 365 e viceversa usa il flusso 4 e/o il flusso 4'.

- Il client è fuori dal ciclo di segnalazione e supporto dopo che la chiamata è stata bloccata da PSTN a PSTN.

- I supporti dell'istanza SBC A all'interno della rete del cliente X all'istanza B di SBC devono essere inoltrati tramite il server multimediale Microsoft 365 o Office 365 e non possono usare la modalità bypass.

## <a name="teams-with-express-route-optimization"></a>Teams con l'ottimizzazione Express Route

[![Microsoft Teams Flusso delle chiamate online Figura 25.](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25 - Teams con l'ottimizzazione Express Route*

Nel caso in cui Express Route sia giustificato e distribuito, i flussi di Teams potrebbero essere ri-instradati dal flusso 4 al flusso 1 e dal flusso 4' al flusso 1'. Tuttavia, l'applicazione Teams ha una dipendenza difficile da altri flussi di Microsoft 365 o Office 365 su Internet usando i flussi 4 e 4'; quindi questi flussi non devono essere bloccati.

Tenere presente Skype for Business il traffico edge ibrido viene instradato a Internet e non a Express Route per comunicare con utenti esterni e federatire con altri tenant.

Per evitare flussi asimmetrici, il ri-routing deve essere in entrambe le direzioni. In altre parole, un indirizzo all'interno della rete del cliente è instradabile tramite Internet o Express Route, in base all'ottimizzazione, ma non tramite entrambi.


**Rete del cliente a utente esterno (supporti inoltrati da Teams Transport Relay):**

[![Microsoft Teams Flusso delle chiamate online Figura 26.](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26 - Rete del cliente a utente esterno (supporti inoltrati da Teams Transport Relay)*

**Passaggi di alto livello:**

1. Teams L'utente all'interno della rete del cliente risolve il nome di dominio URL (DNS) usando flow2.
1. Teams L'utente all'interno della rete del cliente assegna una porta media Relay Teams Transport Relay usando il flusso 1.
1. Teams L'utente all'interno della rete del cliente invia "invito" con i candidati ICE usando il flusso 1 a Microsoft 365 o Office 365.
1. Microsoft 365 o Office 365 invia una notifica a utenti esterni Teams utente usando il flusso 3.
1. Teams utente esterno alloca una porta media Relay Teams transport relay usando il flusso 3.
1. Teams utente esterno invia "risposta" con i candidati ICE usando il flusso 3, che viene inoltrato di nuovo Teams'utente A usando Flow 1.
1. Teams L'utente A e Teams utente B richiamano i test di connettività ICE e selezionano i flussi 1 e 3, che vengono inoltrati Teams Transport Relay.
1. Teams Gli utenti inviano dati di telemetria Microsoft 365 o Office 365 usando i flussi 1 e 3.

> [!NOTE]
> Flow 4 deve essere abilitato per supportare le dipendenze Teams'applicazione da altri microservizi che impone il flusso 4.
