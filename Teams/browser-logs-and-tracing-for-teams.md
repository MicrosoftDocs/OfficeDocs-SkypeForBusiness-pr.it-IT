---
title: Log del browser e traccia per Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui log browser e WebRTC prodotti da Microsoft Teams, dove sono disponibili, su come raccogliere i log con supporto tecnico Microsoft e su come possono aiutare con il monitoraggio e la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005468"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Log del browser e traccia per Teams

Per alcune categorie di errori, supporto tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser. Queste informazioni possono fornire dettagli importanti sullo stato del client Teams quando si verifica l'errore. Questo articolo descrive come raccogliere i log del browser e WebRTC per Teams.

## <a name="browser-logs"></a>Log del browser

Prima di avviare la traccia del browser, assicurarsi di avere eseguito l'accesso a Teams. È importante eseguire questa operazione prima di avviare la traccia in modo che non contenga informazioni di accesso riservate.

Dopo aver eseguito l'accesso, seleziona uno dei collegamenti seguenti, in base alle esigenze del browser, e segui i passaggi forniti. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Bordo](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nei passaggi sostituire tutti i riferimenti alla portale di Azure con il client teams.
  
## <a name="webrtc-logs-in-browsers"></a>Log di WebRTC nei browser

I log di WebRTC possono aiutare supporto tecnico Microsoft fornendo dettagli di connessione per le chiamate audio e video. Segui i passaggi per accedere ai log di WebRTC in Edge (Chromium) o Chrome:
  
1. Aprire una nuova scheda e passare a uno degli URL seguenti:
    - Edge (Chromium):`edge://webrtc-internals/`
    - Chrome: `chrome://webrtc-internals/`
  
2. Apri l'applicazione Web Di Teams e riproduci il problema.
  
3. Indietro alla scheda a cui è stato eseguito l'accesso nel passaggio 1 e verranno visualizzate almeno due schede:
    - Richieste GetUserMedia
    - `https://teams.microsoft.com/url`

4. Scegliere la scheda con il nome dell'applicazione Teams e salvare il contenuto della pagina.

## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)

[Configurare i file di log per il monitoraggio e la risoluzione dei problemi in Teams](/MicrosoftTeams/log-files)
