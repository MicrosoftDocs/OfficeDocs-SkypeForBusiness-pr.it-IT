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
description: Questo articolo illustra la configurazione RTMP basata su codificatore per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767981"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Configurazione di codificatori per lo streaming di eventi live in Microsoft Teams

Teams accetta feed in tempo reale da una varietà di codificatori diversi che esempono RTMP o RTMPS. Ogni codificatore è diverso, quindi assicurati di seguire le linee guida per le configurazioni del codificatore quando invii a Teams.

Per informazioni su come configurare un evento live in Teams, leggere le informazioni sulla creazione di eventi live. Se si usa già un codificatore integrato con Teams, leggere le informazioni sulla [configurazione di codificatori per lo streaming live](teams-encoder-setup.md).

## <a name="configuration-steps"></a>Passaggi di configurazione

Dopo aver pianificato l'evento live con Teams o Yammer e aver selezionato l'opzione **Codificatore di Teams** , sarà possibile recuperare l'URL e il codice RTMP dall'invito alla riunione e usarli per inviare il feed nell'interfaccia utente del produttore di Teams.

### <a name="gather-the-rtmp-information"></a>Raccogliere le informazioni RTMP

#### <a name="scheduled-in-teams"></a>Pianificato in Teams

1. Aprire il client di Teams e passare al **Calendario**.
1. Seleziona l'evento live pianificato e seleziona il pulsante a doppia freccia per visualizzare i dettagli dell'invito.
1. Scendere fino alla sezione **RTMP nei dettagli** .
1. Seleziona il collegamento **Ottieni RTMP** per copiare l'URL di inserimento RTMP negli Appunti.
1. Seleziona la **chiave Get RTMP** per copiare il tasto RTMP negli Appunti.

#### <a name="scheduled-in-yammer"></a>Pianificato in Yammer

1. Passare alla community di Yammer in cui è stato pianificato l'evento.
1. Selezionare la scheda **Eventi** per visualizzare i prossimi eventi pianificati.
1. Selezionare l'evento desiderato per visualizzare la pagina dei dettagli.
1. Sul lato destro, in **Prodotti agricoli**, selezionare il collegamento alle **informazioni RTMP** per esporre l'URL e la chiave RTMP.

## <a name="encoder-setup"></a>Configurazione del codificatore

1. Dopo aver raccolto le informazioni RTMP, verificare che il codificatore sia configurato con le impostazioni corrette secondo le impostazioni consigliate di seguito.
1. Immetti l'URL e il codice RTMP nelle impostazioni di streaming del codificatore (consulta la documentazione del produttore per informazioni specifiche).
1. Configura il codificatore con le origini audio e video desiderate.
1. Apri il client di Teams e unisciti alla presa d'aria in tempo reale come Producer.
1. Avviare lo streaming dal codificatore all'URL di inserimento di Teams RTMP.
1. Nella finestra Teams Producer, dopo alcuni secondi, il feed RTMP del codificatore apparirà nell'area del relatore.
1. Fai clic sul feed RTMP nell'area del relatore per inserirlo nella coda sul lato sinistro.
1. Una volta che sei soddisfatto del feed, seleziona **Invia live** - il feed verrà visualizzato anche sul lato destro della finestra Producer.
1. Selezionare **Avvia** per avviare lo stream.

## <a name="recommended-encoder-settings"></a>Impostazioni del codificatore consigliate

### <a name="ingest-protocols"></a>Protocolli di inserimento

- RTMPS a bitrate singolo o RTMP

### <a name="video-format"></a>Formato video

- Codec: H.264
- Profilo: Alto (livello 4.0)
- Velocità in bit: fino a 5 Mbps (5000 kbps)
- CBR (Strict Constant Bitrate)
- Fotogramma chiave/COPIA: 2 secondi
  - Deve essere presente una cornice IDR all'inizio di ogni
  - Frequenza fotogrammi: 29,97 fps o 30 fps
  - Risoluzione: 1280 x 720 (720P)
  - Modalità interlacciato: Progressive

### <a name="audio-format"></a>Formato audio

- Codec: AAC (LC)
- Velocità in bit: 192 kbps
- Frequenza di esempio: 48 kHz o 44,1 kHz (consigliato 48 kHz)

### <a name="playback-requirements"></a>Requisiti di riproduzione

- Per riprodurre contenuto in Teams, è necessario che sia un flusso audio che un flusso video siano presenti.

### <a name="configuration-tips"></a>Suggerimenti per la configurazione

- Se possibile, usa una connessione Internet con collegamento a internet.
- Per determinare i requisiti di larghezza di banda è necessario raddoppiare le velocità in bit dello streaming. Anche se questo non è un requisito obbligatorio, contribuirà a ridurre l'impatto della congestione di rete.
- Quando si utilizzano codificatori basati su software, chiudere tutti i programmi non necessari.
- Non modificare la configurazione del codificatore dopo che è stato avviato il push. Ha effetti negativi sull'evento e può causare l'evento instabile. Se si vuole eseguire questa operazione prima dell'avvio dell'evento, è necessario disconnettersi usando i controlli producer in Teams e riavviare la configurazione.
- Se il codificatore viene disconnesso durante l'evento live, ricollegarlo mantenendo gli stessi timestamp del processo continuo. Qualsiasi discontinuità può causare problemi audio o video in determinati browser e dispositivi.
- Concediti un ampio tempo per configurare l'evento. Per gli eventi su larga scala, è consigliabile avviare la configurazione un'ora prima dell'evento.
