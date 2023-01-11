---
title: Configurazione del codificatore per lo streaming in Microsoft Teams
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
description: Questo articolo descriverà la configurazione RTMP basata su codificatore per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767988"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Uso di un codificatore per lo streaming live in Microsoft Teams

I codificatori di Teams consentono agli utenti di produrre eventi live direttamente da un codificatore esterno basato su hardware o software con Microsoft Teams.

## <a name="overview"></a>Panoramica

Un codificatore acquisisce contenuti audio e video da varie fonti utilizzate durante un evento live, ad esempio una fotocamera, un microfono, un'acquisizione dello schermo del desktop e così via. Comprime e converte i contenuti multimediali in un formato digitale adatto, quindi li invia a Teams per lo streaming live al pubblico. Consulta il [playbook Produzione personalizzata](https://aka.ms/CustomProductionVEP) per saperne di più su come usare le tecnologie di produzione di Teams (come NDI) con codificatori esterni.

## <a name="production-workflow-when-using-an-encoder"></a>Flusso di lavoro di produzione quando si usa un codificatore

Il flusso di lavoro per la produzione di un evento live di Teams è il seguente:

Un evento live è pianificato in Teams o Yammer e l'opzione **Codificatore di Teams** è selezionata. In questo modo viene fornito un endpoint RTMP, fornito con un URL RTMP(S) e una chiave corrispondente. L'URL e la chiave vengono utilizzati dal codificatore per connettersi all'endpoint RTMP per l'evento live pianificato.

### <a name="common-encoders-user-with-live-events"></a>Utenti di codificatori comuni con eventi live

I codificatori nei due elenchi seguenti sono stati testati da Microsoft per lo streaming live con Teams. Il primo elenco è un sottoinsieme di questi codificatori, che sono stati testati con il prodotto per facilità d'uso e configurazione rapida.

#### <a name="stream-ready-encoders"></a>Codificatori pronti per lo stream

|Encoder                                |Sito Web  |Dettagli  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |Offre video HD di alta qualità con Haivision Hub, una potente alternativa a RTMP. |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |I codificatori video H.264 e HEV offrono cascate video ABR di alta qualità per risoluzioni fino a 4K. |
|Open Broadcaster Software (OBS Studio) |[Aprire il software del broadcaster](https://obsproject.com/) |Acquisizione e mixaggio audio/video ad alte prestazioni in tempo reale, supporto di tutte le piattaforme di streaming e altro ancora. |
|vMix                                   |[vMix](https://www.vmix.com/) |Mixer per la visione software che controlla la registrazione, la miscelazione e lo streaming live di fotocamere, video, audio e altro ancora. |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |Software di webcasting che copre tutti i concetti di base + produzione di più fotocamere. |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |Sincronizza più dispositivi Apple con una o più fotocamere per l'acquisizione e la modifica di video in tempo reale. |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |Registrazione audio e video in tempo reale per lo streaming live su dispositivi connessi a Internet |
|Emittente XSplit                     |[Emittente XSplit](https://www.xsplit.com/) |Produce, mixa e offre contenuti video avanzati, tra cui il gioco per lo streaming live. |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |Suite open source di software per la gestione di file video, audio e altri file multimediali e flussi in tempo reale. |
|Camion di produzione          |[Camion di produzione](https://www.blueframetech.com/productiontruck) |Film e streaming di eventi sulla posizione da un furgone mobile o camion. |
|Produttore IA di Live Arena                 |Produttore IA |Studio di produzione integrato in Microsoft Teams come app per riunioni.|
|StreamYard                             |StreamYard |Live streaming studio nel browser.|
|Social network                              |Social network |Piattaforma di produzione video cloud, che offre un'esperienza all-in-one per la produzione e la distribuzione di contenuti video di qualità studio.|
|Brandlive                              |BrandLive |Piattaforma di produzione basata sul cloud.|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Haivision Makito X Encoder e Makito KB Encoder

Se si dispone di un codificatore Haivision X o Makito KB esistente, è possibile scegliere l'opzione appropriata nell'elenco a discesa e seguire l'elenco di istruzioni.

1. Seleziona **Avvia configurazione** per creare un canale per lo streaming live. Attendere il completamento della configurazione. Sullo schermo verrà visualizzato un messaggio **Pronto per la connessione** .
1. Al termine, scarica il set di impostazioni che contiene tutti i parametri di codifica, incluso l'URL di inserimento e il nome dell'evento. Importare il set di impostazioni nel codificatore e avviare il codificatore.
1. Indietro a Teams. Dopo aver potuto vedere l'anteprima dal codificatore, seleziona **Avvia evento** per passare dal vivo in modo che il pubblico possa vedere l'evento live.

> [!NOTE]
> Il supporto di Haivision KB Encoder per RTMPS non è ancora stato testato. Haivision Makito X Encoder non supporta RTMPS. Le impostazioni predefinite scaricate per entrambi i codificatori contengono l'URL di inserimento RTMP.

### <a name="switcher-studio"></a>Switcher Studio

È possibile usare Switcher Studio per avviare lo streaming su Teams usando iPhone o iPad.

1. Seleziona **Avvia configurazione** per creare un canale per lo streaming live. Attendere il completamento della configurazione. Sullo schermo verrà visualizzato un messaggio **Pronto per la connessione** .
2. Switcher Studio aprirà il dashboard di Switcher Studio per aggiungere l'evento live al tuo account.

> [!NOTE]
> Se non hai già un account Switcher Studio, dovrai crearne uno).

3. Al termine, puoi passare all'app Switcher Studio sul tuo iPhone o iPad, selezionare Teams nella scheda Output e iniziare lo streaming su Teams.
4. Indietro a Teams. Dopo aver potuto vedere l'anteprima dal codificatore, seleziona **Avvia evento** per passare dal vivo in modo che il pubblico possa vedere l'evento live.

> [!NOTE]
> Switcher Studio usa l'URL di inserimento RTMP.

### <a name="wirecast"></a>Wirecast

Se sei un utente esistente di Wirecast, puoi scegliere questa opzione dall'elenco a discesa per inviare un live stream a Teams. Tieni presente che ti servirà Wirecast versione 10 o successiva.

1. Seleziona **Avvia configurazione** per creare un canale per lo streaming live. Attendere il completamento della configurazione. Sullo schermo verrà visualizzato un messaggio **Pronto per la connessione** .
1. Il codificatore avvierà l'app Wirecast nel computer pre-configurato con i parametri di codifica corretti e l'URL di inserimento per l'evento live. Quando sei pronto, fai clic sull'icona di Teams nell'app Wirecast per avviare lo streaming in Teams.
1. Indietro a Teams. Dopo aver potuto vedere l'anteprima dal codificatore, seleziona **Avvia evento** per passare dal vivo in modo che il pubblico possa vedere l'evento live.

> [!NOTE]
> L'app Wirecast viene avviata con l'URL di inserimento RTMPS pre-configurato.
