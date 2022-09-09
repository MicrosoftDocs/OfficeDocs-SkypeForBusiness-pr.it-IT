---
title: Panoramica della licenza Microsoft Teams Rooms nell'interfaccia di amministrazione di Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Informazioni su e confrontare Teams Rooms le licenze e la disponibilità delle funzionalità nell'interfaccia di amministrazione di Teams.
ms.openlocfilehash: d88e7a0c0a6c17fb22f1cc94fcd4de65a3ff79a2
ms.sourcegitcommit: 732a7f3e120cfa221d42b4e8af2cf9ff623488a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "67633636"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Panoramica della licenza Microsoft Teams Rooms nell'interfaccia di amministrazione di Teams

L'interfaccia di amministrazione di Teams consente di visualizzare e gestire Teams Rooms dispositivi e le relative periferiche da una posizione centralizzata. Questo articolo illustra [le funzionalità di gestione](#comparison-of-teams-rooms-feature-availability-by-license) disponibili, a seconda che a un dispositivo Teams Rooms sia assegnata una licenza Microsoft Teams Rooms Basic o Microsoft Teams Rooms Pro.

Per altre informazioni sulle licenze di Microsoft Teams Rooms, vedere [licenze di Microsoft Teams Rooms](rooms-licensing.md).

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>Vedere quali licenze sono assegnate ai dispositivi Teams Rooms

È possibile vedere la licenza dei dispositivi accedendo ai dispositivi Teams nell'interfaccia di amministrazione di Teams e quindi selezionando la categoria di dispositivi (Teams Rooms in Windows, Teams Rooms su Android e Surface Hub) che si vuole visualizzare. Ad esempio, se selezioni **dispositivi** >  Teams **Teams Rooms in Windows**, vedrai qualcosa di simile all'immagine seguente. La colonna **Licenza** mostra il Teams Rooms licenza assegnata a ogni dispositivo.

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Teams Rooms elenco dell'inventario con lo stato attivo sulle licenze Standard, Pro e Pro (versione di valutazione).":::

I dispositivi con licenza **Pro** possono accedere a tutte le funzionalità dell'interfaccia di amministrazione di Teams. I dispositivi con altre licenze possono accedere a un sottoinsieme di tali funzionalità. È possibile vedere quali caratteristiche sono disponibili per ogni licenza in [Confronto tra Teams Rooms disponibilità delle funzionalità in base alla licenza](#comparison-of-teams-rooms-feature-availability-by-license).

> [!IMPORTANT]
> Se si selezionano più dispositivi che includono licenze di Microsoft Teams Rooms Basic e Microsoft Teams Rooms Pro, le azioni che richiedono una licenza Microsoft Teams Rooms Pro verranno eseguite solo sui dispositivi a cui è stata assegnata la licenza. L'azione non verrà eseguita sui dispositivi a cui è assegnata la licenza Microsoft Teams Rooms Basic.

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>Vedere quali funzionalità richiedono una licenza Microsoft Teams Rooms Pro

Le funzionalità che richiedono una licenza Microsoft Teams Rooms Pro possono essere identificate cercando l'icona :::image type="icon" source="../media/mtr-pro-icon.png" border="false"::: nella pagina dei dettagli di un dispositivo. Se al dispositivo attualmente selezionato non è assegnata una licenza di Microsoft Teams Rooms Pro, non sarà possibile eseguire l'azione e verrà visualizzata una richiesta di aggiornamento.

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="Teams Rooms finestra di dialogo di riavvio del dispositivo con l'icona Pro.":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>Confronto tra Teams Rooms disponibilità delle funzionalità per licenza

La tabella seguente mostra le funzionalità di gestione disponibili nell'interfaccia di amministrazione di Teams per ogni licenza di Microsoft Teams Rooms.

|                                               | Microsoft Teams Rooms Di base | Microsoft Teams Rooms Pro |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **Aggiornamenti automatici dei dispositivi**                  | &#x2714;                    | &#x2714;                  |
| **Analisi di base dei dispositivi**                    | &#x2714;                    | &#x2714;                  |
| **Integrità di base del dispositivo**                       | &#x2714;                    | &#x2714;                  |
| **Dashboard qualità chiamata**                    | &#x2714;                    | &#x2714;                  |
| **Creare e visualizzare aree di lavoro**                | &#x2714;                    | &#x2714;                  |
| **Telemetria in tempo reale**                       | &#x2714;                    | &#x2714;                  |
| **Aggiornamenti regolari delle funzionalità**                   | &#x2714;                    | &#x2714;                  |
| **Accesso remoto e disconnessione**               | &#x2714;                    | &#x2714;                  |
| **Configurazioni di dispositivi Android**             |                             | &#x2714;                  |
| **Avvisi per i dispositivi**                             |                             | &#x2714;                  |
| **Analisi dei dispositivi - integrità e utilizzo** |                             | &#x2714;                  |
| **Visualizzazione dettagli dispositivo**                        |                             | &#x2714;                  |
| **Dettagli sull'integrità del dispositivo**                     |                             | &#x2714;                  |
| **Tag dispositivo**                               |                             | &#x2714;                  |
| **API Graph**                                |                             | &#x2714;                  |
| **Aggiornamenti manuali dei dispositivi**                     |                             | &#x2714;                  |
| **Riavvio remoto**                            |                             | &#x2714;                  |
| **Gestione delle periferiche dei dispositivi Windows**     |                             | &#x2714;                  |
| **Impostazioni dei dispositivi Windows**                   |                             | &#x2714;                  |
