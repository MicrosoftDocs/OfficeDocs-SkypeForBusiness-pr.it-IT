---
title: Pianificare la guida alla gestione dei servizi per Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/16/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rowille
description: Offrire un'esperienza utente di team di alta qualità gestendo servizi, reti ed endpoint per l'integrità e definendo i ruoli di campione operativo e qualità.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbee758f45e743fa17848af14e960ede5830dcd0
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184198"
---
# <a name="plan-for-service-management-and-quality"></a>Pianificare la gestione e la qualità dei servizi

Questo documento riguarda la fase di prevedibilità per Microsoft teams.
 
## <a name="introduction"></a>Introduzione

Questo contenuto fornirà una panoramica dei requisiti necessari per offrire e gestire una distribuzione di Microsoft teams di alta qualità. È possibile garantire una distribuzione efficace pianificando la gestione e la qualità dei servizi durante la fase di progettazione, prima della prima distribuzione di Pilot o Production.

Le linee guida sono organizzate nelle sezioni seguenti:

-   La prima è una panoramica dell'esperienza utente e dei componenti chiave che sostengono la qualità. In questo articolo vengono evidenziate le aree in cui concentrarsi prima dell'onboarding in Microsoft teams.

-   In secondo luogo, vengono fornite indicazioni per pianificare un modello di supporto per la gestione di Microsoft teams prima della prima distribuzione pilota o di produzione dell'utente. Questa sezione descrive le attività che devono essere eseguite regolarmente per mantenere una distribuzione di team di alta qualità. In questa sezione vengono inoltre illustrate altre informazioni che è possibile usare per iniziare a comprendere e operationalizing queste attività.

-   In terzo luogo, le linee guida specifiche aiutano a pianificare la rete e gli endpoint dell'organizzazione per supportare Microsoft teams.

-   Infine, i passaggi successivi vengono riepilogati con riferimenti a contenuto correlato.

## <a name="key-components-that-affect-user-experience"></a>Componenti chiave che influiscono sull'esperienza utente

I componenti chiave che influiscono sull'esperienza utente verranno esaminati in questa sezione. Prima di visualizzare i componenti principali, è fondamentale comprendere l'esperienza utente e la sua importanza per realizzare gli obiettivi aziendali dell'organizzazione. Esaminiamo prima di tutto come definiamo l'esperienza utente.

### <a name="user-experience-defined"></a>Esperienza utente definita

Gli obiettivi aziendali possono essere realizzati quando si distribuisce Microsoft teams e si incorporano le comunicazioni nei processi aziendali per migliorare il flusso di lavoro. Adozione e utilizzo delle unità di qualità: se l'organizzazione offre un servizio di alta qualità che delizia gli utenti, gli utenti e i team possono acquisire fiducia e trovare nuovi e innovativi modi di usare il servizio che guida i vantaggi aziendali.

Al centro dell'esperienza dell'utente con teams: le emozioni e gli atteggiamenti della persona verso il servizio. Quali sono i contributi per l'esperienza utente? Spazia da utenti che sanno usare teams e incorporarli nel flusso di lavoro giornaliero per provare una qualità di chiamata eccezionale ed essere in grado di connettersi in modo affidabile, indipendentemente da dove si trovano. L'esperienza utente è molto ampia in natura; Questo documento si basa solo sugli elementi che possono essere controllati dall'organizzazione.

Ci sono requisiti specifici per la distribuzione che sono di fondamentale importanza per offrire un'esperienza utente fantastica, soprattutto quando si usano le caratteristiche di cloud Voice in teams. È fondamentale trattare Microsoft teams come cittadino di prima classe con altri investimenti per la comunicazione e la collaborazione, in modo da dare priorità al traffico in tempo reale di conseguenza. La sezione seguente offre una panoramica dei componenti chiave che influiscono sull'esperienza utente. In altre sezioni verranno fornite indicazioni su come iniziare a pianificare la distribuzione e la gestione dei componenti chiave che includono la qualità.

### <a name="key-components-of-quality"></a>Componenti chiave della qualità

Un'organizzazione o un partner di supporto dovrebbe iniziare a pianificare tre componenti chiave durante la fase di progettazione di una distribuzione di Team: gestione dei servizi, rete e endpoint. La combinazione di tutte e tre le aree è fondamentale per la qualità dell'esperienza utente.

![Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti.] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti.")

#### <a name="service-management"></a>Gestione dei servizi

La gestione dei servizi può essere divisa in due categorie di responsabilità distinte:

-   **Responsabilità Microsoft**. Microsoft è responsabile per i componenti dell'infrastruttura che il servizio Office 365 include. Microsoft è responsabile per i clienti di garantire che tutti gli utenti che si connettono ai team siano dotati di un'esperienza affidabile e di alta qualità.

-   **Responsabilità del cliente**. L'utente e l'organizzazione sono responsabili della gestione di vari aspetti del servizio Office 365, della rete locale e degli endpoint degli utenti. Ad esempio, quando si aggiungono nuovi indirizzi IP a Office 365, è necessario aggiornare i firewall appropriati per consentire la comunicazione ai nuovi endpoint per evitare interruzioni degli utenti.

Per informazioni dettagliate sulla pianificazione della gestione dei servizi, vedere [pianificare la gestione dei servizi](#plan-for-service-management).

#### <a name="network"></a>Rete 

Nella maggior parte delle organizzazioni le reti sono state progettate inizialmente per consentire l'accesso ai dati e alle applicazioni che risiedevano nei loro datacenter. Le applicazioni basate su cloud come Office 365 richiedono modifiche a queste reti per supportare il nuovo accesso e i flussi di dati necessari per i team. Prima di poter abilitare gli utenti per i team dell'organizzazione, è necessario valutare e ottimizzare la rete corrente. Questo aspetto è fondamentale quando si sfruttano le funzionalità di cloud Voice.

Nelle reti tradizionali gli utenti dovranno attraversare le reti perimetrali di un'organizzazione per accedere ai team. Molte organizzazioni avranno dispositivi basati sulla sicurezza come server proxy, firewall e VPN che possono bloccare, impedire o specificare un percorso non ottimizzato per il traffico di rete.

Inoltre, le reti interne principali devono essere ottimizzate e dimensionate a destra per fornire capacità e qualità sufficienti per supportare i carichi di lavoro dei team, inclusi i supporti in tempo reale. È possibile usare la pianificazione della larghezza di banda, il risanamento e l'ottimizzazione per garantire che la rete fornisca un percorso di alta qualità ed efficiente per Office 365.

Per istruzioni dettagliate sulla pianificazione della rete, vedere [pianificare la qualità della rete](#plan-for-network-quality).

#### <a name="endpoints"></a>Endpoint

Microsoft teams supporta un'ampia gamma di endpoint. Dai PC ai tablet ai telefoni, è possibile accedere a Team ovunque da qualsiasi dispositivo.

Per offrire agli utenti un'esperienza ottimale, è necessario considerare questi importanti aspetti durante la fase di prevedibilità: gli endpoint soddisfano i requisiti hardware e software dei team? Sono stati configurati e ottimizzati gli endpoint per il supporto delle reti Wi-Fi? Quali dispositivi si usano per effettuare e ricevere chiamate vocali? I dispositivi sono ottimizzati per i team?

Per istruzioni dettagliate sulla pianificazione degli endpoint, vedere [pianificare la qualità dell'](#plan-for-endpoint-quality)endpoint.

## <a name="plan-for-service-management"></a>Pianificare la gestione dei servizi

La gestione dei servizi è un argomento ampio che include le operazioni quotidiane del servizio Microsoft teams dopo che è stato distribuito e abilitato per gli utenti. Il servizio teams include Microsoft Office 365 e i componenti dell'infrastruttura distribuiti localmente (ad esempio, Networking).

La nozione di gestione dei servizi non è probabilmente un nuovo concetto per la maggior parte delle organizzazioni. Probabilmente hai già implementato processi e attività associati ai servizi esistenti. Ciò detto, è probabile che sia possibile aumentare le informazioni disponibili quando si prevede di gestire i servizi Microsoft teams in futuro.

La gestione dei servizi comprende tutte le attività e i processi coinvolti nella gestione di Microsoft teams end to end. Come descritto in precedenza, alcuni componenti della gestione dei servizi, ovvero i componenti dell'infrastruttura che il servizio di Office 365 stesso comporta, sono responsabili di Microsoft, mentre il cliente è responsabile per gli utenti di gestire i vari aspetti dei team, rete e endpoint da essi forniti. Questa sezione del documento consentirà di concentrarsi sulla responsabilità del cliente da una prospettiva di gestione dei servizi.

![Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sulla gestione dei servizi.] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sulla gestione dei servizi.")

### <a name="introduction-to-the-operations-guide"></a>Introduzione alla Guida alle operazioni 

**Cosa**, **chi**e **come** sono tre domande importanti che devono essere risolte quando si tratta di gestione dei servizi.

È possibile usare la [Guida alle operazioni](1-drive-value-operate-my-service.md) per rispondere a tutte e tre le domande. La guida fornisce un elenco di attività da eseguire su base giornaliera, settimanale, mensile e necessaria. Queste attività e attività sono critiche per il mantenimento di una distribuzione di team di alta qualità. Determinare chi sarà responsabile dell'esecuzione di attività specifiche nella gestione dei servizi è un aspetto cruciale della pianificazione che è necessario eseguire all'inizio della fase di progettazione per garantire una distribuzione corretta. Dopo aver trovato le attività e le attività, è necessario che siano comprese e seguite dai gruppi o dagli individui assegnati. La Guida alle operazioni fornisce informazioni e indicazioni su come eseguire ognuna delle attività e/o i riferimenti al contenuto esterno.

### <a name="operational-role-mapping"></a>Mapping dei ruoli operativi

La pianificazione della gestione dei servizi è un cardine cruciale, perché la fase delle operazioni inizia quando sono abilitati i primi utenti pilota. Il team di progetto deve rivedere e concordare le attività e le attività necessarie, identificare il team responsabile per ogni attività operativa e quindi ottenere un impegno e un discarico da ogni rispettivo team.

Dopo il completamento della disconnessione, il team responsabile deve quindi avviare operationalizing questi ruoli e responsabilità. Questo potrebbe includere formazione e disponibilità, aggiornare il modello di personale o garantire che i partner esterni siano pronti per la distribuzione.

La mappatura dei ruoli operativi all'inizio della fase di predisposizione consente a tutti i team di avviare le attività operative durante il progetto pilota e di aumentare le operazioni e verificare che tutto sia pronto dopo l'avvio della distribuzione.

La Guida alle operazioni fornisce un elenco di attività comuni mappate a ruoli tipici che devono essere validi nella maggior parte degli scenari. È necessario personalizzare queste responsabilità per lavorare per l'organizzazione.

### <a name="the-quality-champion-role"></a>Ruolo di campione di qualità

Un gruppo o un individuo deve essere responsabile per la qualità in tutte le organizzazioni. Questo è il ruolo più importante nella gestione dei servizi. Il campione di qualità è un ruolo del cliente assegnato a una persona o un gruppo appassionato dell'esperienza degli utenti. Questo ruolo richiede le competenze necessarie per identificare le tendenze nell'ambiente e la sponsorizzazione per collaborare con altri team per gestire i correttivi. Il candidato migliore per il campione di qualità è in genere il proprietario del servizio clienti, che, a seconda delle dimensioni e della complessità dell'organizzazione, potrebbe essere una persona o un gruppo appassionato dell'esperienza utente.

Il campione della qualità sfrutta gli strumenti esistenti e i processi documentati, ad esempio il dashboard qualità chiamata (Call Quality Dashboard) e la guida alla revisione dell'esperienza di qualità, per monitorare l'esperienza utente, identificare le tendenze della qualità e correggere le esigenze di guida. Il campione di qualità collabora con i rispettivi team per gestire azioni correttive, segnalando a un comitato direttivo i propri progressi e i problemi aperti.

Le attività e le attività associate al ruolo sono state documentate nella Guida alle operazioni. Questo ruolo deve essere assegnato in anticipo nella fase di predisposizione. Un passaggio chiave in operationalizing il ruolo di campione di qualità sta acquisendo le conoscenze necessarie per il ruolo e garantendo che siano disponibili i prerequisiti per l'esecuzione delle attività. Un'attività chiave per questo ruolo consiste nell'eseguire una normale revisione dell'esperienza di qualità.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduzione alla guida alla revisione dell'esperienza di qualità

La guida alla revisione dell'esperienza di qualità include una serie di attività che valutano e includono indicazioni per il risanamento in aree chiave che hanno il massimo impatto per migliorare l'esperienza utente, come illustrato nella figura seguente.

![Diagramma che illustra le aree principali esaminate durante una revisione dell'esperienza di qualità.] (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Diagramma che illustra le aree principali esaminate durante una revisione dell'esperienza di qualità.")

Valutando e rimediando continuamente le aree descritte in questo documento, è possibile ridurre le proprie potenzialità per influire negativamente sull'esperienza utente. La maggior parte dei problemi di esperienza utente incontrati in una distribuzione può essere raggruppata nelle categorie seguenti:

-   Firewall o configurazione proxy incompleta

-   Scarsa copertura Wi-Fi

-   Larghezza di banda insufficiente

-   VPN

-   Uso di dispositivi audio non ottimizzati o incorporati

-   Subnet problematiche o dispositivi di rete

Le indicazioni fornite nella Guida alla revisione dell'esperienza di qualità si basano sull'uso di Call Quality Dashboard (Call Quality Dashboard) online come strumento principale per segnalare e analizzare ogni area descritta, con un particolare accento sull'audio per massimizzare l'adozione e l'impatto. Le eventuali ottimizzazioni apportate alla rete per migliorare l'esperienza audio si traducono anche direttamente nei miglioramenti della condivisione di video e desktop.

Ti consigliamo vivamente di nominare il campione di qualità in anticipo. Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con il contenuto della Guida alla revisione dell'esperienza di qualità.

La guida alla revisione dell'esperienza di qualità può essere trovata [qui](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Pianificare la qualità della rete 

La pianificazione della qualità della rete sarà lo stato principale per la sezione seguente.

![Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sulla rete.] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sulla rete.")

Come accennato in precedenza, la pianificazione della qualità della rete prima dell'onboarding in Microsoft teams è fondamentale. Per altre indicazioni sulla conformità della rete, vedere [preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md).

Nella maggior parte delle organizzazioni le reti possono contenere sia reti gestite che non gestite.

Le reti gestite sono componenti dell'infrastruttura di rete a cui un'organizzazione ha diretto il controllo. Di conseguenza, le reti gestite influenzano direttamente la qualità che può essere fornita ai carichi di lavoro in tempo reale.

Viceversa, le reti non gestite sono segmenti della rete che un cliente ha un controllo limitato o nessun controllo.

Le connessioni Internet tra l'organizzazione e Office 365 sono reti in cui un cliente ha un controllo limitato. Le reti sono gestite da un ISP, ma le organizzazioni devono essere in grado di influenzare la qualità della rete aggiornando la larghezza di banda, sostenendo le ottimizzazioni delle route oppure, se tutto il resto non riesce, passando ISP.

Le reti domestiche o le reti in alberghi o coffee shop sono esempi di reti in cui un cliente non ha alcun controllo.

Nelle sezioni seguenti verranno illustrati i requisiti di qualità delle reti gestite.

### <a name="key-network-planning-areas"></a>Aree principali per la pianificazione della rete

Le sezioni seguenti riguardano le aree importanti per la distribuzione di una rete di alta qualità.

> [!NOTE]
> Molte reti si evolvono nel tempo a causa di aggiornamenti, espansioni o altri requisiti aziendali. Verificare di avere a disposizione processi operativi per mantenere queste aree nell'ambito della pianificazione della gestione dei servizi.

#### <a name="bandwidth"></a>Banda

La pianificazione della larghezza di banda è un aspetto critico dell'attività di preparazione della rete. Verificare che la larghezza di banda sufficiente per i carichi di lavoro di Microsoft teams sia indispensabile. Per avere la possibilità di ridimensionare una rete esistente, è necessario comprendere il provisioning corrente, l'utilizzo attuale e, in definitiva, la larghezza di banda disponibile rimanente.

Per misurare l'utilizzo corrente, è necessario monitorare la rete. Questa misura può quindi essere usata come punto di partenza per la pianificazione della larghezza di banda. Inoltre, la rete deve essere continuamente monitorata durante la distribuzione e dopo la distribuzione per assicurarsi che la rete sia sufficientemente provisioning.

> [!NOTE]
> Quando si monitora l'utilizzo della rete, è importante evitare di usare le medie durante il giorno. Queste medie possono includere ore non core che alterano il risultato. Le medie possono nascondere i periodi di punta e mascherare un problema sottostante.

#### <a name="quality-of-service-qos"></a>Qualità del servizio (QoS)

La QoS deve essere implementata in tutti i segmenti della rete gestita, anche le reti che sono state adeguatamente provisionate per la larghezza di banda. In quest'ultimo caso, QoS funge da mitigazione dei rischi in caso di caricamento di rete imprevisto. Quando viene implementato QoS, il traffico vocale verrà assegnato in modo che questi eventi imprevisti non influenzino la qualità.

Un'implementazione QoS deve includere aree della rete, dall'endpoint fino ai punti di uscita e dai punti di uscita di nuovo all'endpoint. In questo modo viene garantito che il traffico vocale venga assegnato in priorità in entrambe le direzioni. La QoS deve essere implementata sia sulle reti cablate che su quelle Wi-Fi.

Per implementare QoS nella rete, le linee guida seguenti possono aiutare la [qualità del servizio in Microsoft teams](qos-in-teams.md)

#### <a name="proxy-servers"></a>Server proxy

Molte organizzazioni visualizzano il traffico destinato a Internet come rischio per la sicurezza e mitigano questo rischio monitorando e valutando il traffico nei punti di uscita della rete. I server proxy sono una classe di dispositivi che possono essere distribuiti per soddisfare questo requisito.

Un server proxy può introdurre problemi durante l'esecuzione di un controllo dei pacchetti o una modifica al payload. In questo esempio puoi chiamare errori di configurazione, chiamate interrotte e scarsa qualità delle chiamate. Se l'elemento multimediale in tempo reale è costretto a attraversare un server proxy, lo stack multimediale in teams sarà costretto a non riuscire a eseguire il failover di TCP, che può ulteriormente ridurre la qualità. UDP è sempre preferibile rispetto a TCP.

Inoltre, un server proxy potrebbe non essere progettato per gestire il carico aggiuntivo di Office 365 e, in particolare, i carichi di lavoro di Microsoft teams, incluso il supporto in tempo reale.

A causa dei potenziali problemi che possono essere introdotti da un server proxy e di questi ulteriori aspetti relativi alla capacità, Microsoft consiglia di ignorare il server proxy e di stabilire una connessione diretta a Office 365.

La configurazione necessaria per aggirare il server proxy varia tra i fornitori, ma l'approccio più comune consiste in genere nell'aggiornamento del file di configurazione automatica del proxy (PAC). Il file PAC è un file di configurazione che descrive il traffico che passa attraverso il proxy e il traffico che lo ignora.

Alcuni fornitori di server proxy includono un processo automatizzato per garantire la configurazione aggiornata. Se il fornitore non offre questo processo automatico, è possibile scaricare un file PAC aggiornato <https://aka.ms/o365proxies>.

[Server proxy per Teams o Skype for business online](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>Firewall

Per avere accesso a Microsoft teams, è necessario assicurarsi che le porte e i protocolli giusti siano aperti a tutti gli indirizzi IP di Office 365 e gli URL. È anche fondamentale per una distribuzione di alta qualità. Basta effettuare una chiamata o partecipare a una conferenza telefonica non è sufficiente per verificare che il firewall sia configurato correttamente.

Se sul firewall viene aperto solo TCP, la sessione verrà stabilita, ma il trasporto preferenziale (UDP) non viene negoziato. Sia TCP che UDP devono essere aperti sul firewall per garantire la migliore esperienza utente.

A causa della sua natura imponente, TCP non è preferibile per il supporto in tempo reale e viene fornito solo come un trasporto di rete di failback per Microsoft teams. Con TCP, se si verificano ritardi o perdite di pacchetti, questi pacchetti devono essere ritrasmessi finché non vengono riconosciuti. Questo può comportare pacchetti multimediali che non sono più rilevanti in competizione con il recapito tempestivo dei pacchetti multimediali correnti. Il client Teams dell'utente tenta di estendere l'audio e può produrre artefatti udibili a seconda delle condizioni della rete. Con l'overhead aggiuntivo di TCP, un'esperienza generalmente accettabile può passare a un'esperienza utente insufficiente. Per questo motivo, è necessario l'UDP del trasporto di rete apolidi.

La guida completa per l'apertura del firewall per Microsoft teams è disponibile nell'articolo [URL e intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips) .

Dopo l'apertura del firewall, è possibile usare lo [strumento](https://www.microsoft.com/download/details.aspx?id=53885) di valutazione della rete Microsoft per convalidare la connettività per le funzionalità di cloud Voice.

> [!IMPORTANT]
> Gli indirizzi IP e gli URL di Microsoft Office 365 cambieranno nel tempo. Come parte della pianificazione della gestione dei servizi, è importante garantire un processo operativo e un gruppo è responsabile per monitorare gli [URL e gli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips) e rendere gli aggiornamenti di conseguenza.

#### <a name="local-internet-egress"></a>Uscita Internet locale

Molte reti sono state progettate per l'uso di una topologia hub e spoke. In questa topologia, il traffico Internet in genere attraversa la rete WAN fino a un centro dati centrale prima che venga emerge (egresses) a Internet. Spesso questa operazione viene eseguita per centralizzare i dispositivi di sicurezza della rete con l'obiettivo di ridurre i costi complessivi.

Il traffico di back-haul attraverso la rete WAN aumenta la latenza e ha un impatto negativo sulla qualità e sull'esperienza utente. Poiché Microsoft teams viene eseguito nella grande rete globale di Microsoft, c'è spesso una posizione di peering di rete vicina all'utente. Un utente probabilmente otterrà prestazioni migliori egressing fuori da un punto Internet locale vicino alla propria posizione e alla rete ottimizzata per la voce il più presto possibile. Per alcuni carichi di lavoro, le richieste DNS vengono usate per inviare il traffico al server front-end più vicino. In questi casi, è importante che quando si usa un punto di uscita locale sia associato alla risoluzione DNS locale.

Per ottimizzare il percorso di rete della rete globale Microsoft, è possibile migliorare le prestazioni e infine garantire l'esperienza migliore per gli utenti. Per altri dettagli, vedere il post di Blog per [ottenere la connettività e le prestazioni migliori in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Le VPN garantiscono un servizio prezioso a molte organizzazioni. Sfortunatamente, in genere non sono progettati o configurati per supportare elementi multimediali in tempo reale. Alcune VPN potrebbero anche non supportare UDP. Le VPN introducono anche un ulteriore livello di crittografia sulla parte superiore del traffico multimediale già crittografato. Inoltre, la connettività al servizio Microsoft teams potrebbe non essere efficiente a causa di un traffico di pinne di capelli attraverso un dispositivo VPN. Inoltre, non sono necessariamente progettati da una prospettiva di capacità per soddisfare i carichi previsti necessari per i team.

La raccomandazione consiste nel creare un percorso alternativo che ignori la VPN per il traffico di teams. Questa operazione è comunemente nota come VPN a tunnel separato. Suddividi tunneling significa che il traffico per Office 365 non attraverserà la VPN, ma passerà direttamente a Office 365. Questa modifica avrà un impatto positivo sulla qualità, ma offre anche il vantaggio secondario di ridurre il carico dai dispositivi VPN e dalla rete dell'organizzazione.

Per implementare un tunnel suddiviso, consultare il proprio fornitore di VPN per i dettagli della configurazione.

#### <a name="wi-fi"></a>Wi-Fi

Come la VPN, le reti Wi-Fi non sono necessariamente progettate o configurate per supportare i supporti in tempo reale. Pianificare e/o ottimizzare una rete Wi-Fi per supportare team è una considerazione importante per una distribuzione di qualità.

Esistono diversi fattori che entrano in gioco per ottimizzare una rete Wi-Fi.

-   Implementazione di QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale sia di conseguenza prioritario per le reti Wi-Fi.

-   Pianificare e ottimizzare le bande W-Fi e il posizionamento dei punti di accesso. L'intervallo di 2,4 GHz può avere un'esperienza adeguata a seconda della posizione del punto di accesso, ma i punti di accesso sono spesso colpiti da altri dispositivi consumer che operano in tale intervallo. La gamma a 5 GHz è più adatta a elementi multimediali in tempo reale a causa della loro gamma densa, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo e essere configurati in base a tali bande.

-   Se vengono distribuite reti Wi-Fi dual band, è consigliabile implementare lo sterzo della banda. Lo sterzo della banda è una tecnica implementata da fornitori Wi-Fi per influenzare i client dual-band per usare l'intervallo di 5Ghz.

-   Sovrapposizione dei canali: quando i punti di accesso dello stesso canale sono troppo vicini, possono causare una sovrapposizione di segnali e una concorrenza involontaria, con conseguente esperienza negativa per l'utente. Verificare che i punti di accesso adiacenti si trovino nei canali che non siano sovrapposti.

Ogni fornitore wireless ha le proprie raccomandazioni per la distribuzione della soluzione wireless. È consigliabile consultare il fornitore per indicazioni specifiche.

### <a name="network-readiness-assessment"></a>Valutazione della conformità della rete

Una parte delle attività di conformità della rete include una valutazione della rete. Dopo aver completato la pianificazione e la configurazione, la valutazione può darvi una previsione della qualità della rete prima di intavolare gli utenti in Microsoft teams. I risultati della valutazione aiuteranno anche a identificare e dare priorità agli sforzi correttivi prima di abilitare gli utenti per i team.

La valutazione della rete deve essere eseguita sia sulle reti cablate che su quelle Wi-Fi per tutti gli edifici abilitati per le funzionalità di cloud Voice in teams.

La valutazione della rete può essere eseguita usando un partner Microsoft, strumenti di terze parti o lo [strumento di valutazione della rete Microsoft](https://www.microsoft.com/download/details.aspx?id=53885). 

## <a name="plan-for-endpoint-quality"></a>Pianificare la qualità di endpoint

Come si può vedere dal diagramma seguente, gli endpoint sono un blocco predefinito importante per offrire un'esperienza di alta qualità per gli utenti.

![Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sugli endpoint.] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagramma che illustra i tre componenti della qualità e la gestione dei servizi in sovrapposizione di tutti e tre i componenti. Con lo stato attivo sugli endpoint.")

Gli endpoint di Microsoft teams possono essere eseguiti in molti dispositivi, tra cui PC, Mac, tablet e dispositivi mobili. Parte dell'esperienza non include solo il dispositivo, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono/altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. L'uso di un auricolare ottimizzato può arricchire l'esperienza utente complessiva.

Le linee guida seguenti per la pianificazione degli endpoint consentiranno di verificare che l'organizzazione abbia un'esperienza di onboarding efficace con i team.

### <a name="endpoint-capability"></a>Funzionalità endpoint

La prima parte della pianificazione consiste nel garantire che tutti i PC e altri dispositivi dell'organizzazione possano eseguire Microsoft teams. Questo implica non solo esaminare i requisiti hardware, ma anche capire cos'altro sta facendo il PC in background. Molte organizzazioni eseguono altri software, inclusi i sistemi di rilevamento delle intrusioni e il software antimalware, che possono influire sulle prestazioni di base di un dispositivo.

Microsoft teams è disponibile per i client Web, desktop (Windows e Mac) e per dispositivi mobili (Android, iOS e Windows Mobile). Per informazioni sui requisiti software per ogni piattaforma, vedere [ottenere client per Microsoft teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente. I firewall lato client possono influire sulla qualità delle chiamate oltre a impedire la creazione di una chiamata. Configurare le esclusioni appropriate nel firewall client in base alle informazioni contenute negli [URL e negli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips). Il fornitore di terze parti avrà indicazioni specifiche su come creare le esclusioni.

> [!NOTE]
> Microsoft teams aggiornerà automaticamente Windows Firewall con una configurazione appropriata del firewall.

### <a name="wi-fi-recommendations-for-endpoints"></a>Raccomandazioni Wi-Fi per gli endpoint

La pianificazione e la distribuzione di una rete Wi-Fi ottimizzata per supportare i carichi di lavoro in tempo reale in Microsoft teams richiedono una pianificazione significativa. Nelle sezioni seguenti sono disponibili indicazioni generali che consentono di evitare alcuni problemi comuni quando si pianificano gli endpoint.

#### <a name="wi-fi-drivers"></a>Driver Wi-Fi

Alcuni driver Wi-Fi potrebbero essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso, causando una scarsa qualità delle chiamate. Non si tratta di una cosa comune, ma è importante assicurarsi che i driver Wi-Fi nel PC siano stati aggiornati e testati prima della distribuzione.

#### <a name="wi-fi-bands"></a>Bande Wi-Fi

Ci sono principalmente due tipi di bande usate oggi in apparecchiature Wi-Fi, 2,4 GHz e 5,0 GHz. Se l'organizzazione fornisce entrambe le bande, è consigliabile configurare le impostazioni del driver per preferire la banda di 5,0 GHz. Questa banda è molto più densa in termini di velocità effettiva ed è meno influenzata dall'interferenza riscontrata nella banda di 2,4 GHz. Questa raccomandazione presuppone che sia stata ottimizzata correttamente la banda di rete di 5,0 GHz.

#### <a name="wi-fi-radio-type"></a>Tipo di radio Wi-Fi

Pianificare i dispositivi che supportano i più recenti tipi di radio Wi-Fi. È possibile ottenere ottime prestazioni Wi-Fi se si sfruttano 802.11 AC o versioni successive sui dispositivi che si provisionano.

#### <a name="wireless-avoidance"></a>Evitamento wireless

Alcune organizzazioni preferiscono evitare completamente la rete Wi-Fi. A volte queste indicazioni vengono fornite tramite una raccomandazione agli utenti di connettersi direttamente a una rete cablata. In alcuni casi, l'ordine di binding della rete potrebbe avere la connessione wireless preferita e continuare a usare questa connessione anche se il PC è connesso alla connessione cablata. Per evitare questo comportamento imprevisto, configurare l'ordine di binding per evitare questo scenario.

#### <a name="80211-power-save-protocol"></a>protocollo di risparmio energetico di 802,11

Se l'organizzazione usa punti di accesso wireless o router che non supportano il protocollo di risparmio energia di 802,11, è possibile che si verifichino chiamate cadute o una qualità scadente delle chiamate in Microsoft teams in uso su dispositivi Windows. Se non è possibile aggiornare il punto di accesso o i router wireless, è consigliabile aggiornare le impostazioni di Windows Power Plan nei dispositivi in esecuzione a batteria. Ulteriori indicazioni dettagliate e di configurazione sono disponibili nell' [articolo di supporto](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)seguente.

### <a name="devices-for-teams"></a>Dispositivi per Teams

Microsoft teams può essere usato per le riunioni o come sistema telefonico. Quando si usano queste funzionalità, il dispositivo di interfaccia usato per i team svolge un ruolo importante nell'esperienza utente.

L'uso di un altoparlante e un microfono incorporati nel PC può sembrare accettabile per l'utente che ha questa configurazione. Ma in genere questi dispositivi non sono ottimizzati per l'annullamento del rumore e qualsiasi tipo di rumore ambientale può avere un impatto a valle sugli altri utenti della chiamata. Sfruttando i dispositivi ottimizzati per questi scenari, sarà utile garantire un'esperienza di alta qualità.

Ogni dispositivo deve soddisfare le esigenze degli utenti. È necessario adattare dispositivi come auricolari per i diversi tipi di utenti e casi di utilizzo nell'organizzazione. Un esercizio di mapping da persona a dispositivo deve essere completato come parte del processo di pianificazione.

Dopo aver selezionato i dispositivi, includerli nel piano di test pilota per la convalida finale. È necessario sfruttare i sondaggi durante il progetto pilota per raccogliere feedback per verificare che la strategia del dispositivo sia ottimale.

In questo momento, ti consigliamo di usare i dispositivi audio certificati tramite il programma di certificazione Skype for business. Per trovare i dispositivi certificati in questo programma, vedere i [dispositivi USB certificati per il catalogo di soluzioni Skype for business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

## <a name="client-updates"></a>Aggiornamenti client

Uno dei vantaggi principali di Microsoft teams è che il client viene mantenuto aggiornato automaticamente. I client del PC e del Mac vengono aggiornati usando un processo in background che verifica la ricerca di nuove compilazioni e Scarica il nuovo client quando l'app è inattiva. La dimensione del download del client è approssimativamente di 100 MB.

Un'organizzazione non ha alcun controllo o accesso a un'impostazione di criterio per gestire il processo di aggiornamento. Per ridurre il rischio di un problema che potrebbe essere rilevato in una build più recente, l'ultima versione valida nota viene mantenuta nell'endpoint. Se c'è un problema con una nuova build, il servizio Microsoft teams può ripristinare automaticamente l'endpoint alla versione precedente.

## <a name="next-steps-and-references"></a>Passaggi e riferimenti successivi

Questa tabella include un riepilogo delle attività di pianificazione con collegamenti a contenuto correlato.

| Zona | Dettagli | Riferimenti |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pianificare la gestione dei servizi | Eseguire un esercizio di mapping dei ruoli operativo <br/> Conclusione dei team responsabili <br/> Preparazione del ruolo | [Guida alle operazioni](1-drive-value-operate-my-service.md) |
| | Nominare i campioni di qualità <br/> Preparazione del campione di qualità| [Guida alla revisione dell'esperienza di qualità](https://aka.ms/qerguide) |
| | Installare i modelli di revisione dell'esperienza di qualità <br/> Caricare un file di costruzione | [Modelli di QERLite](https://aka.ms/qertemplates) <br/> [Caricare informazioni sulle costruzioni](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)|
| Pianificare la qualità della rete | Eseguire la pianificazione della rete |  |
| | Implementare QoS | [Qualità del servizio in Microsoft Teams](qos-in-teams.md) |
| | Bypassare i server proxy | [Guida proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implementare una VPN a tunnel separato |  |
| | Ottimizzare le reti Wi-Fi per elementi multimediali in tempo reale  | Consultare i fornitori di terze parti |
| | Implementare l'uscita Internet locale | [Uscita Internet locale](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementare la connettività di rete <br/> Convalidare la connettività di rete | [URL e indirizzi IP di Office 365](https://aka.ms/o365ips) |
| | Eseguire la valutazione della rete |[Strumento di valutazione della rete](https://www.microsoft.com/download/details.aspx?id=53885)   |
| Pianificare la qualità di endpoint | Aggiornare i firewall endpoint | [URL e indirizzi IP di Office 365](https://aka.ms/o365ips) |
| | Convalidare i requisiti software | [Ottenere client per Microsoft Teams](get-clients.md) |
| | Implementare le raccomandazioni Wi-Fi dell'endpoint | Consultare i fornitori di terze parti |
| | Eseguire il mapping di tipo persona a dispositivi <br/> Eseguire il provisioning di dispositivi e pilotarli | [Catalogo dispositivi](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |
