---
title: Ridimensionare la distribuzione video in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo descriverà la scalabilità delle reti per la distribuzione di contenuti video e di distribuzione di contenuti aziendali (eCDN) per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767943"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>Ridimensionare la distribuzione video e monitorare il traffico di rete usando eCDN con Microsoft Teams

La riproduzione di video da Microsoft Teams e gli eventi live "App o dispositivi esterni" (precedentemente noti come produzioni "External Encoder") utilizzano lo streaming a bitrate adattivo (ABR) fornito come flusso unicast. Questo significa che ogni visualizzatore riceve il proprio flusso video da Internet. Per gli eventi live o i video inviati a grandi parti dell'organizzazione, potrebbe esserci una quantità significativa di larghezza di banda di rete e Internet usata dagli spettatori.

Le organizzazioni potrebbero voler comprendere e ridurre il traffico di rete per eventi live e video popolari. In tal caso, Teams può essere abilitato all'integrazione con partner Microsoft attendibili che offrono soluzioni eCDN (Enterprise Content Delivery Network) che includono tecnologie di distribuzione a gestione automatica, monitoraggio in tempo reale e analisi approfondita della rete. Queste piattaforme eCDN consentono alle organizzazioni di monitorare, ridimensionare e ottimizzare la distribuzione di flussi video (e a volte altri tipi di contenuto) nella rete aziendale.

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>Acquisire e configurare la soluzione eCDN all'esterno di Teams

Ottenere assistenza di esperti per il monitoraggio e il ridimensionamento della distribuzione video collaborando con partner Microsoft eCDN attendibili.

Prima di poter abilitare una soluzione eCDN da usare con Teams, è necessario acquistare e configurare tale soluzione eCDN all'esterno e separata da Teams. Per garantire che la soluzione soddisfi le tue esigenze, alcuni partner forniscono prove gratuite delle loro tecnologie di distribuzione dei contenuti e di analisi di rete.

Diverse soluzioni eCDN sono pre-integrate e possono essere abilitate per l'uso con Teams. Vedere le informazioni dei provider di seguito.

### <a name="hive-streaming"></a>Hive Streaming

La **piattaforma di esperienze video streaming Hive** è composta da tre prodotti principali:

- **Hive Video Optimization** si basa su un algoritmo di configurazione zero e solo software brevettato. L'ottimizzazione ottimizza automaticamente la qualità e la portata dei video live e su richiesta (VOD) per l'intera organizzazione.
- **Hive Video Analytics aiuta i** clienti a comprendere le tendenze negli eventi live e le prestazioni video su richiesta per migliorare il coinvolgimento degli spettatori nel tempo. Con il miglioramento del coinvolgimento, anche l'adozione di video in tutta l'azienda.
- **Hive Video Operations** offre potenti funzionalità che puntano a proteggere proattivamente il successo dei video in streaming prima e durante gli eventi video in diretta. Gli strumenti operativi consentono ai team di video streaming e UC di individuare e correggere i problemi prima che si verifichino.

Tutte lavorano per creare esperienze video complete, dalla pianificazione all'esecuzione e all'analisi. Ottimizzare l'esperienza di comunicazione video in streaming è fondamentale per il coinvolgimento e l'allineamento dei dipendenti nella missione aziendale. Per altre informazioni, consulta [questo collegamento](https://www.hivestreaming.com/partners/microsoft).

### <a name="kollective"></a>Kollective

**Kollective Technology** è una piattaforma di distribuzione dei contenuti basata sul cloud che utilizza il peering intelligente per offrire video aziendali in tempo reale e su richiesta, fornendo una qualità video al 100% e un coinvolgimento del 100% a solo l'1% della larghezza di banda. L'integrazione di Kolletive con Teams Live Events consente ai dipendenti distribuiti a livello globale di utilizzare facilmente il video, migliorare la comunicazione dei dipendenti, aumentare il coinvolgimento generale e aumentare le opportunità di formazione e conservazione.

**Kollective IQ** è una piattaforma di analisi sofisticata e intuitiva per Microsoft Stream. Grazie a report, visualizzazioni e dashboard personalizzabili, è facile quantificare e digerire sia l'esperienza utente che il coinvolgimento in reti aziendali globali complesse. I responsabili delle comunicazioni e gli amministratori di rete possono guardare gli eventi in tempo reale e l'attività di rete, in modo che i colli di bottiglia possano essere risolti rapidamente, assicurando massime prestazioni di rete.

Per altre informazioni su queste opzioni, consulta [questo collegamento](https://kollective.com/microsoft-live-events/).

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** risolve il problema di congestione della rete che si verifica durante eventi virtuali aziendali di grandi dimensioni, ad esempio riunioni a mani libere. Microsoft eCDN forma una rete mesh attraverso la LAN che riduce il carico del 95% ed elimina i problemi di rete. Microsoft eCDN è il primo eCDN a usare WebRTC come base, il che significa che non è necessaria alcuna installazione hardware o software. I clienti Fortune 500 possono mitigare i problemi di rete e considerare attendibile Peer5 per i loro eventi aziendali più grandi.

- La configurazione di rete zero-setup per Microsoft eCDN garantisce che i lavoratori remoti e/o il traffico video pesante non sovraccaricheranno la rete né obbligano l'utente a investire in costose infrastrutture. Include il rilevamento automatico del sito, il rilevamento automatico della VPN e l'attraversamento automatico di NAT/firewall. Per altre informazioni, vedere [questo collegamento](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant).
- Test silenziosi con Microsoft eCDN consente agli amministratori IT di simulare eventi live di grandi dimensioni sulla propria rete aziendale, consentendo test approfonditi e non fastidiosi e la risoluzione dei problemi prima di un evento reale. Per altre informazioni, vedere [questo collegamento](/ecdn/how-to/perform-silent-test).
- Le analisi leader del settore di Microsoft eCDN forniscono analisi granulari e consentono agli amministratori di individuare rapidamente la causa principale di qualsiasi problema di streaming. Il toolkit include metriche di recapito e esperienza utente, drill-down avanzati, analisi per utente e un'API back-end. Per altre informazioni, vedere [questo collegamento](/ecdn/technical-documentation/analytics).

### <a name="ramp"></a>Ramp

**Ramp eCDN** riduce il consumo della larghezza di banda di rete del 90% o più durante lo streaming di eventi live e video su richiesta (VOD). Usa Ramp per combinare qualsiasi combinazione di tecnologie eCDN: multicast, memorizzazione nella cache e rete peer-to-peer. Grazie alla gestione centralizzata, al monitoraggio e all'analisi approfondita, è possibile ottenere visibilità e controllo sulle prestazioni di rete per creare un'esperienza di visualizzazione di altissima qualità.

- **Ramp Multicast+** è il modo più efficiente per trasmettere video in diretta. Usando il protocollo multicast, si utilizza solo la larghezza di banda necessaria per un solo visualizzatore, indipendentemente dal fatto che si abbiano 100, 10.000 o 100.000 visualizzatori. Per altre informazioni, vedere [questo collegamento](https://www.rampecdn.com/altitudecdn/multicast/).
- **Ramp OmniCache™** è un software di memorizzazione nella cache specifico per video che usa le cache locali per fornire video in tempo reale e VOD ai destinatari nelle vicinanze, riducendo drasticamente il numero di flussi video che viaggiano attraverso le connessioni Internet e i collegamenti WAN. Per altre informazioni, vedere [questo collegamento](https://www.rampecdn.com/altitudecdn/video-cache/).
- **Ramp Peer-to-Peer (P2P)** consente di ottimizzare la larghezza di banda anche in luoghi con infrastruttura limitata. P2P crea una rete peer di dispositivi client che guardano lo stesso contenuto per ridistribuire i flussi video da un dispositivo di visualizzazione a un altro. Per altre informazioni, vedere [questo collegamento](https://www.rampecdn.com/altitudecdn/p2p/).

### <a name="riverbed"></a>Riverbed

**Riverbed**, lo standard di settore nell'ottimizzazione della rete, ha esteso le sue soluzioni di accelerazione a Teams. I clienti di Microsoft 365 possono accelerare con sicurezza il traffico di Microsoft 365, incluso Teams, insieme a un'ampia gamma di altri servizi SaaS aziendali leader per aumentare la produttività della forza lavoro ovunque ci si trovi. L'accelerazione di Teams può essere abilitata attraverso una configurazione senza sforzo che viene fornita con tutta la garanzia del supporto di livello mondiale di Riverbed e degli investimenti continuativi. Per altre informazioni, vedere [questo collegamento](https://www.riverbed.com/office365).

> [!NOTE]
> La soluzione eCDN scelta è soggetta alle condizioni del servizio e all'informativa sulla privacy del provider eCDN partner selezionato, che regoleranno l'uso della soluzione del provider eCDN. L'uso della soluzione del provider di eCDN non sarà soggetto alle condizioni dei contratti multilicenza o dei servizi online Microsoft. Se non accetti le condizioni del provider di terze parti, non abilitare la soluzione eCDN in Microsoft Teams.

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>Configurare gli eventi del tipo di codificatore di Stream per la soluzione eCDN

Dopo aver acquistato e configurato la soluzione eCDN, è possibile abilitarla per l'uso con Microsoft Stream, inclusi gli eventi live del codificatore di Stream creati tramite Microsoft Teams o Yammer.

1. Aprire l'interfaccia di amministrazione di Teams come amministratore globale di Microsoft 365 o amministratore di Teams e passare alla pagina [delle impostazioni degli eventi live](https://admin.teams.microsoft.com/broadcasts/settings) .
1. Impostare il **provider di distribuzione video** **su Attivato**.
1. Scegliere un **provider eCDN/SDN** dall'elenco a discesa **Provider di distribuzione video** .
1. Compilare gli altri campi come indicato dal provider di soluzioni (non tutti i campi vengono usati da tutti i provider di soluzioni).
1. Selezionare **Salva**.
1. Per verificare se la configurazione è corretta, seleziona **Verifica configurazione**.
    - Cercare qualsiasi video nell'organizzazione con cui eseguire la convalida.
    - Se il provider eCDN è configurato correttamente, verrà visualizzato un messaggio **Di successo** nello strumento di verifica configurazione.
    - Se non si è configurati correttamente, verrà visualizzato un messaggio **di errore** . Copiare il messaggio dell'evento da condividere con il provider per la risoluzione dei problemi.

Dopo aver configurato Teams per una soluzione eCDN, qualsiasi video o evento live riprodotto in Teams sfrutterà automaticamente tale soluzione.

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>Configurare gli eventi di tipo produzione di Teams tramite Teams e Yammer per la soluzione eCDN

Se si prevede di creare eventi live di Teams tramite Teams o Yammer, è necessario [configurare il provider eCDN in modo che sia integrato anche con Microsoft Teams](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) .

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>Accedere ai report di analisi video per la soluzione eCDN

Come indicato in precedenza, alcune soluzioni eCDN forniscono anche report di analisi che forniscono informazioni più approfondite sulle sessioni di riproduzione, gli spettatori e la qualità del servizio. Se il provider ti ha fornito un modello di URL di report analitico da configurare quando configuri il provider nell'interfaccia di amministrazione di Teams, i proprietari di video o eventi possono accedere facilmente al report di analisi per uno specifico video o evento.

I proprietari dei video vedranno una scheda Analytics direttamente sotto il video. In questa scheda, sarà disponibile un collegamento per i proprietari per accedere al report di analisi per questo video specifico nel sistema del provider eCDN.

Se sei un amministratore di Teams, puoi anche elevare il tuo accesso per vedere la scheda Analytics e accedere al collegamento al report di analisi eCDN, anche se non sei proprietario dell'evento live o del video.

1. Come amministratore di Teams, vai alla pagina del lettore video.
1. Seleziona **Impostazioni**.
1. Selezionare **Visualizza in modalità amministratore**.
1. Seleziona la scheda **Analisi** .

## <a name="troubleshooting-issues"></a>Risoluzione dei problemi

Assicurarsi che la soluzione eCDN sia configurata correttamente nella rete e che Teams sia stato configurato correttamente per abilitare il provider in base alle istruzioni e alle stringhe di configurazione specifiche. Se i problemi persistono, alcune delle informazioni seguenti potrebbero essere utili.

### <a name="verify-setup-tool"></a>Verificare lo strumento di configurazione

Se si verificano problemi con la soluzione eCDN, è sempre possibile tornare indietro ed eseguire lo strumento **Verifica configurazione** . I messaggi dell'evento del provider eCDN visualizzati per il video di test possono fornire a te e al tuo provider eCDN ulteriori informazioni su ciò che non funziona.

- Vai a **Impostazioni** >  **Amministrazione Impostazioni** >  provider  > **eCDN****Verifica configurazione**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>Disabilitare eCDN per una sessione specifica tramite la stringa di query dell'URL

Per determinare se un problema riscontrato riguarda la soluzione eCDN o Teams, puoi disabilitare facilmente la soluzione eCDN per una sessione di riproduzione specifica tramite una stringa di query.

- Se l'URL di riproduzione contiene già un punto interrogativo, **?**, aggiungi **&disableSDN=true**.
- Se l'URL di riproduzione non ha un punto interrogativo, **?**, aggiungi **?disableSDN=true**.

### <a name="view-ecdn-info-in-browser-console"></a>Visualizzare informazioni eCDN nella console del browser

Se il provider di soluzioni eCDN lo supporta, può stampare le informazioni di debug durante l'inizializzazione della riproduzione tramite la soluzione. Queste informazioni aggiuntive possono essere utili per determinare gli errori. È possibile abilitare messaggi di debug extra console tramite la stringa di query.

- Se l'URL di riproduzione contiene già un punto interrogativo, **?**, aggiungi **&isSDNDebug=true**.
- Se l'URL di riproduzione non ha un punto interrogativo, **?**, aggiungere **?isSDNDebug=true**.

Seleziona **F12** sulla tastiera quando il browser è attivo e passa alla scheda **Console** per visualizzare tutte le informazioni stampate durante il caricamento della pagina con la stringa di query isSDNDebug=true impostata sull'URL di riproduzione.
