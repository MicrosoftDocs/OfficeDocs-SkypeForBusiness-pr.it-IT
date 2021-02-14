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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Informazioni su come Teams usa i flussi di Office 365 in varie topologie, nonché flussi univoci del team usati per la comunicazione multimediale peer-to-peer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13bd0479436963402124e7edea049bcc250d3515
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638665"
---
# <a name="microsoft-teams-call-flows"></a>Flussi di chiamata in Microsoft Teams

> [!TIP]
> Guarda questa sessione per imparare come Teams sfrutta la tua rete e come pianificare una connettività di rete ottimale: [Pianificazione della rete di Teams.](https://aka.ms/teams-networking)

## <a name="overview"></a>Panoramica

Questo articolo descrive in che modo Teams usa i flussi delle chiamate di Microsoft 365 o Office 365 in varie topologie. Descrive inoltre flussi univoci di Teams usati per la comunicazione multimediale peer-to-peer. Il documento descrive questi flussi, il loro scopo e la loro origine e risoluzione nella rete. Ai fini del presente articolo, si presuppone che:

- Flow X viene usato dal client locale per comunicare con il servizio Microsoft 365 o Office 365 nel cloud. Proviene dalla rete del cliente e termina come endpoint in Microsoft 365 o Office 365.

- Il flusso Y viene usato dal client locale per comunicare con un servizio su Internet da cui Microsoft 365 o Office 365 ha una dipendenza. Proviene dalla rete del cliente e termina come endpoint su Internet.

Questo articolo contiene le informazioni seguenti:

- **Sfondo.** Fornisce informazioni di base, ad esempio le reti che possono attraversare i flussi, i tipi di traffico, le indicazioni sulla connettività dalla rete del cliente agli endpoint del servizio Microsoft 365 o Office 365, l'interoperabilità con componenti di terze parti e i principi usati da Teams per selezionare i flussi multimediali.

- **Flussi delle chiamate in varie topologie.** Illustra l'uso dei flussi delle chiamate in varie topologie. Per ogni topologia, la sezione enumera tutti i flussi supportati e illustra come vengono usati in diversi casi di utilizzo. Per ogni caso di utilizzo, descrive la sequenza e la selezione dei flussi usando un diagramma di flusso.

- **Team con ottimizzazione Express Route.** Descrive come vengono usati questi flussi durante l'implementazione di Express Route per l'ottimizzazione, illustrati con una topologia semplice.

## <a name="background"></a>Sfondo

### <a name="network-segments"></a>Segmenti di rete

**Rete del cliente.** Si tratta del segmento di rete che si controlla e gestisce. Ciò include tutte le connessioni dei clienti all'interno degli uffici dei clienti, sia cablate che wireless, le connessioni tra gli edifici degli uffici, le connessioni a data center locali e le connessioni a provider Internet, Express Route o qualsiasi altro peering privato.

In genere, una rete del cliente ha diversi perimetrali di rete con firewall e/o server proxy, che applicano i criteri di sicurezza dell'organizzazione e che consentono solo il traffico di rete configurato e configurato. Poiché si gestisce questa rete, si ha un controllo diretto sulle prestazioni della rete ed è consigliabile completare le valutazioni della rete per convalidare le prestazioni sia all'interno dei siti della rete che dalla rete alla rete di Microsoft 365 o Office 365.

**Internet.** Si tratta del segmento di rete che fa parte della tua rete complessiva, che verrà utilizzato dagli utenti che si connettono a Microsoft 365 o Office 365 dall'esterno della rete del cliente. Viene usato anche da parte del traffico dalla rete del cliente a Microsoft 365 o Office 365.

**Rete privata visitata o guest.** Si tratta del segmento di rete al di fuori della rete del cliente, ma non nella rete Internet pubblica, che gli utenti e i loro guest possono visitare (ad esempio una rete privata domestica o una rete privata aziendale, che non distribuisce Teams, dove possono risiedere gli utenti e i loro clienti che interagiscono con i servizi di Teams).

> [!NOTE]
> La connettività a Microsoft 365 o Office 365 è applicabile anche a queste reti.

**Microsoft 365 o Office 365.** Si tratta del segmento di rete che supporta i servizi Microsoft 365 o Office 365. È distribuito in tutto il mondo con bordi in prossimità della rete del cliente nella maggior parte delle località. Le funzioni includono Inoltro di trasporto, server delle conferenze e processore multimediale.

**Express Route (facoltativo).** Si tratta del segmento di rete che fa parte della tua rete complessiva, che ti offrirà una connessione dedicata e privata alla rete Microsoft 365 o Office 365.

### <a name="types-of-traffic"></a>Tipi di traffico

**Elementi multimediali in tempo reale.** Dati incapsulati all'interno del protocollo RTP (Real-time Transport Protocol) che supportano carichi di lavoro audio, video e di condivisione dello schermo. In generale, il traffico degli elementi multimediali è altamente sensibile alla latenza, quindi è consigliabile che questo traffico prenda il percorso più diretto possibile e che usi UDP o TCP come protocollo layer di trasporto, che è il miglior trasporto per gli elementi multimediali interattivi in tempo reale da un punto di vista qualitativo. Come soluzione ultima, gli elementi multimediali possono usare TCP/IP ed essere anche essere tunneled all'interno del protocollo HTTP, ma non è consigliabile a causa di implicazioni di bassa qualità. Il flusso RTP è protetto con SRTP, in cui è crittografato solo il payload.

**Segnalazione**. Il collegamento di comunicazione tra il client e il server o altri client usati per controllare le attività (ad esempio, quando viene avviata una chiamata) e recapitare messaggi istantanei. La maggior parte del traffico di segnalazione utilizza le interfacce REST basate su HTTPS, ma in alcuni scenari (ad esempio la connessione tra Microsoft 365 o Office 365 e un controller dei confini della sessione) usa il protocollo SIP. È importante comprendere che questo traffico è molto meno sensibile alla latenza, ma può causare interruzioni del servizio o timeout delle chiamate se la latenza tra gli endpoint supera diversi secondi.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Connettività a Microsoft 365 o Office 365

Teams richiede [la connettività a Internet.](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity) Gli URL e gli intervalli di indirizzi IP degli endpoint di Teams sono elencati negli URL e [negli intervalli di indirizzi IP di Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) Tenere presente che è necessario aprire la connettività alle porte TCP 80 e 443 e alle porte UDP da 3478 a 3481. Inoltre, Teams ha una dipendenza da Skype for Business Online, che deve essere connesso anche a Internet.

La connettività dei flussi multimediali di Teams viene implementata utilizzando procedure STANDARD IETF Interactive Connectivity Connectivity Connectivity (ICE).

### <a name="interoperability-restrictions"></a>Limitazioni all'interoperabilità

**Media relay di terze parti.** Un flusso multimediale di Teams (ovvero, in cui uno degli endpoint multimediali è Teams) può attraversare solo Teams o i media relay nativi di Skype for Business. L'interoperabilità con un Media Relay di terze parti non è supportata. Si noti che un provider di servizi di archiviazione di terze parti sul confine con PSTN deve terminare il flusso RTP/RTCP, protetto con SRTP, e non inoltrarlo all'hop successivo.

**Server proxy SIP di terze parti.** Una finestra di dialogo SIP di Teams per il traffico di segnalazione con un SBC di terze parti e/o un gateway può attraversare i proxy SIP nativi di Teams o Skype for Business. L'interoperabilità con un proxy SIP di terze parti non è supportata.

**B2BUA (o SBC)** di terze parti. Un flusso multimediale di Teams da e verso la rete PSTN viene terminato da un SBC di terze parti. Tuttavia, l'interoperabilità con un SBC di terze parti all'interno della rete di Teams (in cui una SBC di terze parti media due endpoint di Teams o Skype for Business) non è supportata.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologie non consigliate con Microsoft Teams

**Rete VPN.** Non è consigliato per il traffico multimediale (o il flusso 2'). Il client VPN deve usare vpn divise e instradare il traffico multimediale come qualsiasi utente esterno non VPN, come specificato in Abilitazione dei supporti di [Lync per bypassare un tunnel VPN.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)

> [!NOTE]
> Anche se il titolo indica Lync, è applicabile anche a Teams.

**Packet shapers.** Non è consigliabile alcun tipo di dispositivi per la acquisizione di pacchetti, l'ispezione dei pacchetti o i dispositivi a forma di pacchetti e la qualità potrebbe peggiorare significativamente.

### <a name="principles"></a>Principi

Esistono quattro principi generali che ti aiutano a comprendere i flussi delle chiamate per Microsoft Teams:

- Microsoft 365 o Office 365 ospita una conferenza di Microsoft Teams nella stessa regione in cui si è unito il primo partecipante. Se esistono eccezioni a questa regola in alcune topologie, verranno descritte in questo documento e illustrate da un flusso delle chiamate appropriato.

- Un endpoint multimediale di Teams in Microsoft 365 o Office 365 viene utilizzato in base alle esigenze di elaborazione multimediale e non in base al tipo di chiamata. Ad esempio, una chiamata punto a punto può usare un endpoint multimediale nel cloud per elaborare elementi multimediali per la trascrizione o la registrazione, mentre una conferenza con due partecipanti potrebbe non usare alcun endpoint multimediale nel cloud. Tuttavia, la maggior parte delle conferenze userà un endpoint multimediale per la combinazione e l'instradamento, allocato dove è ospitata la conferenza. Il traffico multimediale inviato da un client all'endpoint multimediale può essere instradato direttamente o usare un Inoltro di trasporto in Microsoft 365 o Office 365, se necessario a causa delle restrizioni del firewall di rete dei clienti.

- Il traffico multimediale per le chiamate peer-to-peer prende il percorso più diretto disponibile, presupponendo che la chiamata non richiede un endpoint multimediale nel cloud (vedere il principio precedente). Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile, uno o più inoltro di trasporto inoltriranno il traffico. È consigliabile che il traffico multimediale non inverti server come forma pacchetti, server VPN e così via, in quanto ciò inciderà sulla qualità dei supporti multimediali.

- Il traffico di segnalazione viene sempre verso il server più vicino all'utente.

Per altre informazioni sui dettagli sul percorso multimediale scelto, vedere Informazioni sui flussi multimediali [in Microsoft Teams - BRK4016.](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>Flussi delle chiamate in varie topologie

### <a name="teams-topology"></a>Topologia di Teams

Questa topologia viene usata dai clienti che sfruttano i servizi Di Teams dal cloud senza alcuna distribuzione locale, come Skype for Business Server o Il routing diretto del sistema telefonico. Inoltre, l'interfaccia di Microsoft 365 o Office 365 viene eseguita su Internet senza Azure Express Route.

[![Flussi delle chiamate di Microsoft Teams Online - Figura 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1 - Topologia di Teams*

Si noti che:

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività sui perimetrali aziendali. Nel caso di UDP per il supporto, il flusso dei primi pacchetti potrebbe essere nella direzione inversa, ma questi pacchetti potrebbero essere bloccati finché non scorrono i pacchetti nella direzione opposta.
- Teams viene distribuito affiancato con Skype for Business Online, quindi i client vengono visualizzati come "Utente Teams/SfB".

Per altre informazioni sulle topologie facoltative seguenti, vedere più avanti in questo articolo:

- La distribuzione locale di Skype for Business è descritta nella topologia **ibrida di Teams.**
- Il routing diretto del sistema telefonico (per la connettività PSTN) è descritto in **Teams con topologia di routing diretto.**
- Express Route è descritto in **Teams con l'ottimizzazione Express Route.**

**Descrizioni del flusso:**

- **Flusso 2** – Rappresenta un flusso avviato da un utente sulla rete del cliente verso Internet nell'ambito dell'esperienza teams dell'utente. Esempi di questi flussi sono i record DNS e gli elementi multimediali peer-to-peer.
- **Flow 2'** – Rappresenta un flusso avviato da un utente di Teams per dispositivi mobili remoto, con VPN alla rete del cliente.
- **Flusso 3** : rappresenta un flusso avviato da un utente di Teams per dispositivi mobili remoto verso gli endpoint di Microsoft 365 o Office 365/Teams.
- **Flusso 4** : rappresenta un flusso avviato da un utente nella rete del cliente verso gli endpoint di Microsoft 365 o Office 365/Teams.
- **Flusso 5** – Rappresenta un flusso multimediale peer-to-peer tra un utente di Teams e un altro utente di Teams o Skype for Business all'interno della rete del cliente.
- **Flusso 6** – Rappresenta un flusso multimediale peer-to-peer tra un utente di Teams per dispositivi mobili remoto e un altro utente remoto di Teams per dispositivi mobili o Skype for Business tramite Internet.

#### <a name="use-case-one-to-one"></a>Caso d'uso: uno-a-uno

Le chiamate uno-a-uno usano un modello comune in cui il chiamante ottiene un set di candidati costituiti da indirizzi IP/porte, inclusi i candidati locali, di inoltro e riflessivi (l'indirizzo IP pubblico del client, come visto dal inoltro). Il chiamante invia questi candidati al chiamato; Il chiamante ottiene anche un insieme di candidati simili e li invia al chiamante. I messaggi di controllo della connettività STUN vengono usati per trovare i percorsi dei supporti di risposta/parti supportati e viene selezionato il percorso di lavoro migliore. I supporti (ovvero i pacchetti RTP/RTCP protetti con SRTP) vengono quindi inviati usando la coppia candidata selezionata. L'inoltro di trasporto viene distribuito come parte di Microsoft 365 e Office 365.

Se i candidati per l'indirizzo IP locale o i candidati riflessivi hanno una connettività, verrà selezionato il percorso diretto tra i client (o con un NAT) per gli elementi multimediali. Se i client sono entrambi nella rete del cliente, è consigliabile selezionare il percorso diretto. A questo scopo è necessaria la connettività UDP diretta all'interno della rete del cliente. Se i client sono entrambi utenti cloud, a seconda del NAT/firewall, gli elementi multimediali possono usare la connettività diretta.

Se un cliente è interno alla rete del cliente e uno è esterno (ad esempio, un utente cloud mobile), è improbabile che la connettività diretta tra i candidati locali o riflessivi funzioni correttamente. In questo caso, è possibile usare uno dei candidati per l'inoltro di trasporto da uno dei due client (ad esempio, il client interno ha ottenuto un inoltro candidato dall'inoltro di trasporto in Microsoft 365 o Office 365; il client esterno deve essere in grado di inviare pacchetti STUN/RTP/RTCP all'inoltro di trasporto). Un'altra opzione è il client interno che invia al candidato per l'inoltro ottenuto dal client cloud mobile. Si noti che, anche se è altamente consigliata la connettività UDP per i supporti multimediali, è supportato TCP.

**Passaggi di alto livello:**

1. L'utente A di Teams risolve il nome di dominio URL (DNS) con il flusso 2.
1. L'utente di Teams A assegna una porta Media Relay su Transport Relay di Teams utilizzando il flusso 4.
1. L'utente A del team invia un "invito" con i candidati ICE utilizzando il flusso 4 a Microsoft 365 o Office 365.
1. Microsoft 365 o Office 365 invia una notifica all'utente di Teams B usando il flusso 4.
1. L'utente di Teams B assegna una porta Media Relay su Transport Relay di Teams utilizzando il flusso 4.
1. L'utente B del team invia una risposta con i candidati ICE utilizzando il flusso 4, che viene inoltrato di nuovo all'utente di Teams A utilizzando il flusso 4.
1. L'utente A e il team Utente B richiamano i test di connettività ICE ed è selezionato il miglior percorso multimediale disponibile (vedere i diagrammi di seguito per vari casi di utilizzo).
1. Gli utenti di Teams inviano telemetria a Microsoft 365 o Office 365 usando il flusso 4.

**All'interno della rete del cliente:**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2 - Interno alla rete del cliente*

Nel passaggio 7 è selezionato il flusso multimediale peer-to-peer 5.

L'elemento multimediale è bidirezionale. La direzione del flusso 5 indica che un lato avvia la comunicazione dal punto di vista della connettività, in modo coerente con tutti i flussi nel documento. In questo caso, non importa quale direzione viene usata perché entrambi gli endpoint sono all'interno della rete del cliente.

**Rete del cliente a utente esterno (contenuti multimediali inoltrati da Transport Relay di Teams):**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3 - Rete del cliente a utente esterno (elementi multimediali inoltrati da Teams Transport Relay)*

Nel passaggio 7, flusso 4, dalla rete del cliente a Microsoft 365 o Office 365, e flusso 3, dall'utente remoto di Teams per dispositivi mobili a Microsoft 365 o Office 365, sono selezionati. Questi flussi vengono inoltrati da Teams Transport Relay all'interno di Microsoft 365 o Office 365.

Gli elementi multimediali sono bidirezionali, dove la direzione indica quale lato avvia la comunicazione dal punto di vista della connettività. In questo caso, questi flussi vengono utilizzati per il traffico di segnalazione e gli elementi multimediali, utilizzando diversi protocolli e indirizzi di trasporto.

**Rete del cliente a utente esterno (elementi multimediali diretti):**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4 - Rete del cliente a utente esterno (elementi multimediali diretti)*

Nel passaggio 7, il flusso 2, dalla rete del cliente a Internet (peer del client), è selezionato.

- Gli elementi multimediali diretti con utenti mobili remoti (non inoltrati tramite Microsoft 365 o Office 365) sono facoltativi. In altre parole, il cliente può bloccare questo percorso per applicare un percorso multimediale tramite Transport Relay in Microsoft 365 o Office 365.

- L'elemento multimediale è bidirezionale. La direzione del flusso 2 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

**Utente VPN a utente interno (contenuti multimediali inoltrati da Teams Transport Relay)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5 - Utente VPN a utente interno (contenuti multimediali inoltrati da Teams Transport Relay)*

Il traffico di segnalazione tra la VPN alla rete del cliente utilizza il flusso 2'. Il traffico di segnalazione tra la rete del cliente e Microsoft 365 o Office 365 utilizza il flusso 4. Tuttavia, gli elementi multimediali evitano la VPN e vengono instradati usando i flussi 3 e 4 attraverso l'Media Relay di Teams in Microsoft 365 o Office 365.

**Da utente VPN a utente interno (file multimediali diretti)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6 - Da utente VPN a utente interno (file multimediali diretti)*

Il traffico di segnalazione tra la VPN alla rete del cliente utilizza il flusso 2'. Il traffico di segnalazione tra la rete del cliente e Microsoft 365 o Office 365 utilizza il flusso 4. Tuttavia, gli elementi multimediali ignorano la VPN e vengono instradati utilizzando il flusso 2 dalla rete del cliente a Internet.

L'elemento multimediale è bidirezionale. La direzione del flusso 2 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

**Da un utente VPN a un utente esterno (file multimediali diretti)**

[![Flussi delle chiamate di Microsoft Teams - Figura 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7 - Da utente VPN a utente esterno (file multimediali diretti)*

Il traffico di segnalazione tra l'utente VPN e la rete del cliente utilizza il flusso 2' e il flusso 4 verso Microsoft 365 o Office 365. Tuttavia, gli elementi multimediali ignorano la VPN e vengono instradati usando il flusso 6.

L'elemento multimediale è bidirezionale. La direzione del flusso 6 per l'utente mobile remoto indica che un lato avvia la comunicazione dal punto di vista della connettività.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Use Case: Da Teams a PSTN tramite Trunk di Microsoft 365 o Office 365

Microsoft 365 e Office 365 dispongono di un sistema telefonico che consente di effettuare e ricevere chiamate dalla rete PSTN (Public Switched Telephone Network). Se il trunk PSTN è connesso tramite il Piano per le chiamate del sistema telefonico, non ci sono requisiti di connettività speciali per questo caso d'uso. Se si vuole connettere il trunk PSTN locale a Microsoft 365 o Office 365, è possibile usare il routing diretto del sistema telefonico.

[![Flussi delle chiamate di Microsoft Teams Online - Figura 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8 - Da Teams a PSTN tramite trunk di Office 365*

#### <a name="use-case-teams-meeting"></a>Use Case: Riunione di Teams

Il server delle conferenze audio/video/schermo (VBSS) fa parte di Microsoft 365 e Office 365. Ha un indirizzo IP pubblico che deve essere raggiungibile dalla rete del cliente e deve essere raggiungibile da un client cloud aziendale. Ogni client/endpoint deve essere in grado di connettersi al server delle conferenze.

I clienti interni ottengono candidati locali, riflessivi e inoltrati nello stesso modo in cui sono descritti per le chiamate uno-a-uno. I client invieranno questi candidati al server delle conferenze in un invito. Il server delle conferenze non usa un inoltro perché ha un indirizzo IP accessibile pubblicamente, quindi risponde con il candidato per l'indirizzo IP locale. Il client e il server delle conferenze controllano la connettività come descritto per le chiamate uno-a-uno.

Si noti che:

- I client Teams non possono partecipare alle riunioni Skype for Business e i client Skype for Business non possono partecipare alle riunioni di Teams.

- Un utente PSTN ha la funzione facoltativamente "Chiamata in corso" o "Chiamata in uscita", a seconda del provisioning delle chiamate e/o delle conferenze PSTN dell'organizzatore della riunione.

- Un utente guest o un utente cliente può partecipare da una rete privata guest, che è protetta con FW/NAT con regole restrittive.

[![Flussi delle chiamate di Microsoft Teams Online - Figura 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9 - Riunione di Teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso d'uso: Federazione con Skype for Business locale

**Elementi multimediali trasmessi da Teams Transport Relay in Microsoft 365 o Office 365**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10 - Elementi multimediali inoltrati da Transport Relay di Teams in Office 365*

Si noti che:

- La federazione è, per definizione, una comunicazione tra due tenant. In questo caso, il tenant A, che usa Teams, è federato con il tenant B, che usa Skype for Business locale. Se il tenant B usa anche Microsoft 365 o Office 365, il client Skype for Business avrebbe usato il flusso 3 per connettersi a Microsoft 365 o Office 365.

- Segnalazione ed elementi multimediali dal client Skype for Business federato a Skype for Business Server locale non ambito del presente documento. Tuttavia, è illustrato qui per chiarezza.

- Il servizio di segnalazione tra Teams e Skype for Business viene bridgeato da un gateway.

- Gli elementi multimediali in questo caso vengono inoltrati da Teams Transport Relay alla rete del cliente e al client skype for Business remoto usando il flusso 4.

**Elementi multimediali inoltrati da Media Relay di Skype for Business nel tenant federato**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11 - Elementi multimediali inoltrati da Skype for Business Media Relay nel tenant federato*

Si noti che:

- Segnalazione ed elementi multimediali dal client Skype for Business federato a un server Skype for Business locale non ambito del presente documento. Tuttavia, è illustrato qui per chiarezza.

- Il servizio di segnalazione tra Teams e Skype for Business viene bridgeato da un gateway.

- In questo caso, gli elementi multimediali vengono inoltrati da Media Relay locale di Skype for Business alla rete del cliente utilizzando il flusso 2. Tenere presente che il traffico dall'utente di Teams al Media Relay remoto nella rete del cliente federato verrà inizialmente bloccato da Media Relay finché non inizia il flusso del traffico nella direzione inversa. Tuttavia, il flusso bidirezionale aprirà la connettività in entrambe le direzioni.

**Diretta (peer-to-peer)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12 - Diretta (peer-to-peer)*

### <a name="teams-hybrid-topology"></a>Topologia ibrida di Teams

Questa topologia include Teams con una distribuzione locale di Skype for Business.

[![Flussi delle chiamate di Microsoft Teams Online - Figura 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13 - Topologia ibrida di Teams*

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività sui perimetrali aziendali. Nel caso di UDP per il supporto, il flusso dei primi pacchetti potrebbe essere nella direzione inversa, ma questi pacchetti potrebbero essere bloccati finché non scorrono i pacchetti nella direzione opposta.

- Teams viene distribuito affiancato con Skype for Business Online, quindi i client vengono visualizzati come "Utente Teams/SfB".

Flusso aggiuntivo (sopra la topologia di Teams):

- **Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso d'uso: da Teams a Skype for Business uno a uno

**Ibrida all'interno della rete del cliente**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14 - Scenario ibrido all'interno della rete del cliente*

Il servizio di segnalazione tra Teams e Skype for Business viene bridgeato da un gateway. Tuttavia, gli elementi multimediali vengono instradati direttamente peer-to-peer all'interno della rete del cliente usando il flusso 5.

**Rete dei clienti ibrida con utente skype for Business esterno , inoltrato da Microsoft 365 o Office 365**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15 - Rete clienti ibrida con utente Skype for Business esterno - inoltrato da Office 365*

Si noti che:

- Segnalazione ed elementi multimediali dal client Skype for Business a un server Skype for Business locale non ambito del presente documento. Tuttavia, è illustrato qui per chiarezza.

- Il servizio di segnalazione tra Teams e Skype for Business viene bridgeato da un gateway.

- Gli elementi multimediali vengono inoltrati tramite l'Inoltro di trasporto di Teams alla rete del cliente attraverso il flusso 4.

**Rete del cliente ibrida con utente Skype for Business esterno – inoltrato dall'Edge locale**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16 - Rete del cliente ibrida con utente Skype for Business esterno - inoltrato dall'Edge locale*

Si noti che:

- Segnalazione ed elementi multimediali dal client Skype for Business a un server Skype for Business locale non ambito del presente documento. Tuttavia, è illustrato qui per chiarezza.

- Il servizio di segnalazione viene bridgeato da un gateway.

- Gli elementi multimediali vengono inoltrati da Skype for Business Media Relay all'interno dell'Edge locale di Skype for Business agli utenti di Teams all'interno della rete del cliente utilizzando il flusso multimediale 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Team con topologia di routing diretto del sistema telefonico

Questa topologia include Teams con routing diretto del sistema telefonico.

Il routing diretto consente di usare un provider di servizi PSTN (Public Switched Telephone Network) di terze parti associando un dispositivo hardware SBC (Session Border Controller) di proprietà del cliente supportato a Microsoft 365 o Office 365 e quindi connettendo il trunk di telefonia a tale dispositivo.

Per supportare questo scenario, il cliente deve distribuire un SBC certificato per l'instradamento diretto da uno dei partner certificati Microsoft. Il servizio SBC deve essere configurato come consigliato dal fornitore e deve essere instradabile da Microsoft 365 o Office 365 per il traffico UDP diretto. Il flusso degli elementi multimediali può essere diretto da Teams e/o dal client Skype for Business al gateway SBC (bypassando il gateway di Teams) o attraverso il gateway di Teams. La connettività con SBC, quando il trunk è configurato per bypassare il gateway di Teams, si basa su ICE, dove SBC supporta ICE-Lite, mentre l'endpoint media di Teams/Skype for Business supporta ICE Full Form.

[![Flussi delle chiamate di Microsoft Teams Online - Figura 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17 - Team con topologia di routing diretto del sistema telefonico

Si noti che:

- La direzione delle frecce nel diagramma precedente riflette la direzione di avvio della comunicazione che influisce sulla connettività sui perimetrali aziendali. Nel caso di UDP per il supporto, il flusso dei primi pacchetti potrebbe essere nella direzione inversa, ma questi pacchetti potrebbero essere bloccati finché non scorrono i pacchetti nella direzione opposta.

- Teams viene distribuito affiancato con Skype for Business Online, quindi i client vengono visualizzati come "Utente Teams/SfB".

Altri flussi (sopra la topologia online di Teams):

- **Flusso 4'** - Rappresenta un flusso da Microsoft 365 o Office 365 alla rete del cliente, usato per stabilire una connessione tra il server multimediale di Teams nel cloud e SBC in locale.
- **Flusso 5B:** rappresenta un flusso multimediale tra l'utente di Teams all'interno della rete del cliente con il routing diretto SBC in modalità bypass.
- **Flusso 5C:** rappresenta un flusso multimediale tra il routing diretto SBC e un altro SBC di routing diretto in modalità bypass chiamata hairpin PSTN.

**Utente interno con instradamento diretto (elementi multimediali inoltrati da Teams Transport Relay)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18 - Utente interno con routing diretto (elementi multimediali inoltrati da Transport Relay di Teams)*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- Segnalazione ed elementi multimediali dall'SBC a Microsoft 365 o Office 365 e viceversa usano il flusso 4 e/o flusso 4'.

- Segnalazione ed elementi multimediali dal client all'interno della rete del cliente a Microsoft 365 o Office 365 usano il flusso 4.

**Utente remoto con routing diretto (gli elementi multimediali vengono instradati attraverso un server multimediale (MP))**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19 - Utente remoto con routing diretto (gli elementi multimediali vengono instradati attraverso un server multimediale (MP))*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- Segnalazione ed elementi multimediali dall'SBC a Microsoft 365 o Office 365 e viceversa usano il flusso 4 e/o flusso 4'.

- Segnalazione ed elementi multimediali dal client su Internet a Microsoft 365 o Office 365 usano il flusso 3.

**Routing diretto dell'utente interno (bypass multimediale)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20 - Routing diretto dell'utente interno (bypass multimediale)*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- Il traffico di segnalazione da SBC a Microsoft 365 o Office 365 e viceversa utilizza il flusso 4 e/o il flusso 4'.

- Il traffico di segnalazione dal client all'interno della rete del cliente a Microsoft 365 o Office 365 utilizza il flusso 4.

- Gli elementi multimediali dal client all'interno della rete del cliente fino a SBC all'interno della rete del cliente usano il flusso 5B.

**Utente remoto con instradamento diretto (bypass multimediale inoltrato da Transport Relay di Teams)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21 - Utente remoto con routing diretto (bypass multimediale inoltrato da Teams Transport Relay)*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365 e Internet.

- Il traffico di segnalazione dall'SBC a Microsoft 365 o Office 365 e viceversa utilizza il flusso 4 e/o il flusso 4'.

- Il traffico di segnalazione dal client su Internet a Microsoft 365 o Office 365 utilizza il flusso 3.

- Gli elementi multimediali dal client su Internet al servizio SBC all'interno della rete del cliente utilizzano i flussi 3 e 4, inoltrati da Teams Transport Relay.

**Routing diretto utente remoto (bypass multimediale diretto)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22 - Routing diretto dell'utente remoto (bypass multimediale diretto)*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365 e da Internet.

- Il traffico di segnalazione dall'SBC a Microsoft 365 o Office 365 e viceversa utilizza il flusso 4 e/o il flusso 4'.

- Il traffico di segnalazione dal client su Internet a Microsoft 365 o Office 365 utilizza il flusso 3.

- Gli elementi multimediali dal client su Internet al servizio SBC all'interno della rete del cliente utilizzano il flusso 2.

**Routing diretto (bypass multimediale) - Chiamata di hairpin PSTN (a causa dell'inoltro/trasferimento chiamata)**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23 - Routing diretto (bypass multimediale) - Chiamata di hairpin PSTN (per inoltro/trasferimento chiamata)*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- Il traffico di segnalazione dall'SBC a Microsoft 365 o Office 365 e viceversa utilizza il flusso 4 e/o il flusso 4'.

- Il client è fuori dal ciclo di segnalazione e dei supporti multimediali dopo che la chiamata è stata aggiunta da PSTN a PSTN.

- Gli elementi multimediali dall'istanza SBC A all'interno della rete del cliente all'istanza SBC B all'interno della rete del cliente, dove A e B possono essere la stessa istanza, utilizzano il flusso 5C.

**Routing diretto (supporti tramite Microsoft 365 o Office 365) – Chiamata di hairpin PSTN tra due tenant**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figura 24 - Routing diretto (supporti tramite Microsoft 365 o Office 365) - Chiamata di hairpin PSTN tra due tenant*

Si noti che:

- L'SBC deve avere un indirizzo IP pubblico instradabile da Microsoft 365 o Office 365.

- Il traffico di segnalazione dall'SBC a Microsoft 365 o Office 365 e viceversa utilizza il flusso 4 e/o il flusso 4'.

- Il client è fuori dal ciclo di segnalazione e dei supporti multimediali dopo che la chiamata è stata aggiunta da PSTN a PSTN.

- Gli elementi multimediali provenienti dall'istanza SBC A della rete del cliente X all'istanza SBC B devono essere inoltrati tramite il server multimediale Microsoft 365 o Office 365 e non possono usare la modalità bypass.

## <a name="teams-with-express-route-optimization"></a>Team con ottimizzazione Express Route

[![Flussi delle chiamate di Microsoft Teams Online - Figura 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25 - Team con ottimizzazione Express Route*

Nel caso in cui Express Route sia giustificato e distribuito, i flussi di Teams potrebbero essere ri instradati dal flusso 4 al flusso 1 e dal flusso 4' al flusso 1'. Tuttavia, l'applicazione Teams ha una dipendenza difficile da altri flussi di Microsoft 365 o Office 365 su Internet con flussi 4 e 4'; di conseguenza, questi flussi non devono essere bloccati.

Il traffico Edge ibrido di Skype for Business viene instradato a Internet e non a Express Route per comunicare con utenti esterni e federati con altri tenant.

Per evitare flussi asimmetrici, il ri routing deve essere in entrambe le direzioni. In altre parole, un indirizzo all'interno della rete del cliente può essere instradato attraverso Internet o Express Route, in base all'ottimizzazione, ma non attraverso entrambi.


**Rete del cliente a utente esterno (contenuti multimediali inoltrati da Transport Relay di Teams):**

[![Flussi delle chiamate di Microsoft Teams Online - Figura 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26 - Rete del cliente a utente esterno (elementi multimediali inoltrati da Teams Transport Relay)*

**Passaggi di alto livello:**

1. L'utente di Teams all'interno della rete del cliente risolve il nome di dominio (DNS) dell'URL con flow2.
1. L'utente di Teams nella rete del cliente assegna una porta Media Relay su Transport Relay di Teams utilizzando il flusso 1.
1. L'utente teams all'interno della rete del cliente invia un "invito" con i candidati ICE utilizzando il flusso 1 a Microsoft 365 o Office 365.
1. Microsoft 365 o Office 365 invia una notifica agli utenti esterni di Teams usando il flusso 3.
1. L'utente esterno di Teams assegna una porta Media Relay su Transport Relay di Teams usando il flusso 3.
1. Gli utenti esterni di Teams inviano una risposta con i candidati ICE utilizzando il flusso 3, che viene inoltrato all'utente di Teams A utilizzando il flusso 1.
1. L'utente A e il team Utente B richiamano i test di connettività ICE e selezionano i flussi 1 e 3, inoltrati da Teams Transport Relay.
1. Gli utenti di Teams inviano telemetria a Microsoft 365 o Office 365 usando i flussi 1 e 3.

> [!NOTE]
> Il flusso 4 deve essere abilitato per supportare le dipendenze dell'applicazione Teams su altri micro-servizi che impone il flusso 4.
