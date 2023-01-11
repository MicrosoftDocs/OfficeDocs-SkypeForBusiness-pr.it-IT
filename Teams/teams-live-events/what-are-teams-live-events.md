---
title: Cosa sono gli eventi live di Microsoft Teams?
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
- highpri
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: Informazioni su come gli eventi live consentono agli utenti di trasmettere video e contenuti ad ampi gruppi di destinatari online in Teams, Yammer e Stream.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 7fc4c6857bfce46ad3fabec54eceaf0514ad7dfa
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767537"
---
# <a name="what-are-microsoft-teams-live-events"></a>Cosa sono gli eventi live di Microsoft Teams

## <a name="overview"></a>Panoramica

Con gli eventi live di Teams, gli utenti dell'organizzazione possono trasmettere i video e i contenuti delle riunioni ad ampi gruppi di destinatari online.

Gli eventi live di Microsoft 365 portano lo streaming video live a un nuovo livello. Gli eventi live favoriscono la connessione durante l'intero ciclo di vita di interazione con i partecipanti: prima, durante e dopo gli eventi live. È possibile creare un evento live ovunque il pubblico, il team o la community risieda usando Teams o Yammer.  

Teams offre una collaborazione basata su chat, chiamate, riunioni ed eventi live, in modo da poter ampliare il gruppo di destinatari delle riunioni. Gli eventi live di Teams sono un'estensione delle riunioni di Teams. Questi consentono agli utenti di trasmettere video e contenuti a un gruppo di destinatari online. Questi sono pensati per le comunicazioni “uno-molti”, dove l'organizzatore dell'evento guida le interazioni e l’unica forma di partecipazione del pubblico è principalmente quella di visualizzare il contenuto condiviso dal presentatore. I partecipanti possono guardare l'evento in tempo reale o registrato in Yammer o Teams e interagire con i relatori usando una Q & A moderata o una conversazione di Yammer.

So, let's get started. First, take a look at the following diagram that shows high level components involved in Microsoft 365 live events and how they're connected.

![Componenti principali degli eventi live.](../media/live-events-flow-diagram.png  "Componenti chiave di eventi live, pianificazione, produzione, provider eCDN di terze parti certificati")

> [!NOTE]
> È opportuno sottolineare il fatto che gli eventi live di Teams, considerando la natura della tecnologia di trasmissione, spesso superano gli insiemi di dati (interni) standard delle riunioni.
>
> Dato che questo accade anche con altre trasmissioni di contenuti multimediali di dimensioni maggiori, facciamo affidamento sulle reti di distribuzione del contenuto per fornire i contenuti per gli eventi live ai destinatari. Questo contenuto è protetto da metodi di crittografia e soggetto all'autorizzazione da parte di token di accesso inviati unicamente ai destinatari in base alla configurazione delle riunioni degli eventi live.
>
> Dovrebbe essere prestata molta cura per assicurarsi che i contenuti della riunione siano adatti a un gruppo di destinatari così ampio o che il gruppo di destinatari venga ridotto in modo appropriato per i contenuti riservati.  
>
> Come succede spesso nel settore, eventuali compromessi ad altri elementi della sicurezza, quali il personale o l'infrastruttura, potrebbero avere ripercussioni sulla sicurezza degli eventi live. Le organizzazioni dovrebbero considerare di includere gli eventi live e altri servizi di trasmissione nella pianificazione della sicurezza e negli esercizi.

### <a name="event-group-roles"></a>Ruoli del gruppo eventi

Gli eventi live in Teams consentono a utenti con diversi ruoli (organizzatore, produttore, relatore e partecipante) di trasmettere un evento e parteciparvi con successo. Per altre informazioni, vedere [Ruoli del gruppo di eventi](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Componenti fondamentali

Nell'immagine riportata sopra sono disponibili cinque componenti fondamentali usati con gli eventi live in Teams.

> [!NOTE]
> Per una panoramica su come configurare gli eventi live e sull'esperienza partecipante, vedere questi brevi [video](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).

### <a name="scheduling"></a>Pianificazione

Teams consente agli organizzatori di creare un evento con le autorizzazioni appropriate per i partecipanti, designare i membri del team per l'evento, selezionare una modalità di produzione e invitare i partecipanti. Se l'evento live è stato creato dall'interno di un gruppo Yammer, i partecipanti all'evento live potranno interagire con i partecipanti all'evento tramite la conversazione di Yammer.

![Schermata nuovo evento live.](../media/teams-live-events-schedule.png "Screenshot che mostra la schermata Nuovo evento live per creare e programmare un nuovo evento live")

> [!IMPORTANT]
> Teams non consentirà agli utenti di pianificare le riunioni o gli eventi live quando sono offline o in caso di larghezza di banda limitata.

### <a name="production"></a>Produzione

L'input video è il base dell'evento live e può variare da una singola webcam a una produzione video professionale con più telecamere. Gli eventi live in Microsoft 365 supportano una vasta gamma di scenari di produzione, tra cui eventi prodotti in Teams usando una webcam o eventi prodotti tramite app o dispositivo esterno. È possibile scegliere queste opzioni in base ai requisiti di progetto e al budget. È possibile produrre eventi in due modi:

- **Teams**: questo metodo di produzione consente agli utenti di produrre gli eventi live in Teams usando la webcam o usando l’ingresso A/V dai sistemi di sala riunioni di Teams. Questa è l'opzione migliore e più rapida se si desidera utilizzare i dispositivi audio e video collegati al PC o se si invitano presentatori da remoto a partecipare all'evento. Questa opzione consente agli utenti di usare facilmente le loro webcam e condividere lo schermo come input durante l’evento.

- **Codificatore di Teams**: consente agli utenti di produrre i propri eventi live direttamente da un codificatore esterno basato su hardware o software con [Teams](../teams-stream-overview.md). Questa opzione è ideale se si hanno già attrezzature di qualità, ad esempio i media mixer, che supportano lo streaming di un servizio RTMP (Real Time Messaging Protocol). Questo tipo di produzione viene in genere usato in eventi di grandi dimensioni, ad esempio le assemblee generali esecutive, in cui un singolo flusso proveniente da un mixer multimediale viene trasmesso ai destinatari.

    ![un evento live prodotto tramite un app o un dispositivo esterno.](../media/teams-live-events-external-encoder.png "Screenshot che mostra un evento live prodotto tramite un’app esterna o un metodo di produzione da dispositivo")

### <a name="streaming-platform"></a>Piattaforma di streaming

La piattaforma di streaming degli eventi live è composta da quanto segue:

- **Servizi multimediali di Microsoft Azure**:  I [servizi multimediali di Microsoft Azure](/azure/media-services/previous/) offrono servizi di streaming video con qualità broadcast per raggiungere gruppi di destinatari sui dispositivi mobili più diffusi. I servizi multimediali consentono di migliorare l'accessibilità, la distribuzione e la scalabilità, semplificando la distribuzione di contenuti ai gruppi di destinatari locali o in tutto il mondo, proteggendo al contempo il contenuto.
- **Rete CDN di Azure**: una volta che lo streaming è live, questo viene trasmesso attraverso la [Rete CDN di Azure](/azure/cdn/). I servizi multimediali di Azure forniscono una rete CDN integrata per gli endpoint che trasmettono in streaming. Ciò consente di visualizzare lo streaming in tutto il mondo senza buffering.

### <a name="enterprise-content-delivery-network-ecdn"></a>Rete aziendale per la distribuzione di contenuti (eCDN)

L'obiettivo dell’eCDN consiste nell'estrarre il contenuto video da Internet e distribuirlo in tutta l'organizzazione senza influire sulle prestazioni della rete. È possibile usare la [soluzione eCDN di prima parte Microsoft](/ecdn) o, in alternativa, uno dei seguenti partner eCDN certificati per ottimizzare la rete per gli eventi live tenuti all'interno dell'organizzazione:

- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [Ramp](https://rampecdn.com)
- [Riverbed](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>Esperienza partecipanti

L'esperienza del partecipante è l'aspetto più importante degli eventi live. Infatti, è essenziale che non vi siano problemi per la partecipazione. L'esperienza dei partecipanti usa Teams (per gli eventi prodotti in Teams) e Azure Media Player (per gli eventi prodotti in un'app o un dispositivo esterno) e funziona su desktop, browser e dispositivi mobili (iOS, Android). Microsoft 365 e Office 365 si integrano a Yammer e Teams come hub di collaborazione e fanno sì che l'esperienza dei partecipanti agli eventi live sia integrata in tali strumenti di collaborazione.

![Esempio dell'esperienza del partecipante agli eventi live.](../media/teams-live-events-attendee.png "Screenshot che mostra l'esperienza dei partecipanti agli eventi live")

### <a name="live-event-usage-report"></a>Report sull'uso degli eventi live

Gli amministratori del tenant possono visualizzare le analisi di utilizzo in tempo reale per gli eventi live nell'interfaccia di amministrazione di Microsoft Teams.  Il [report sull'uso degli eventi live](../teams-analytics-and-reports/teams-live-event-usage-report.md) mostra la panoramica delle attività degli eventi nell'organizzazione.  Gli amministratori possono visualizzare le informazioni sull'utilizzo degli eventi, inclusi lo stato dell'evento, l'ora di inizio, le visualizzazioni e il tipo di produzione.  

## <a name="next-steps"></a>Passaggi successivi

Passare a [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati

- [Introduzione agli eventi live di Microsoft Teams](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventi live in Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventi in streaming live in Microsoft Teams](../teams-stream-overview.md)
