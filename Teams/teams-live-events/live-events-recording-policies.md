---
title: Criteri per la registrazione di eventi live
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Informazioni sui criteri di registrazione di eventi live.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794114"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Criteri di registrazione di eventi live in Microsoft Teams

Sono disponibili diverse opzioni per la registrazione di un evento live di Microsoft Teams. Le opzioni di registrazione vengono impostate usando i criteri di registrazione. Questo articolo descrive le varie impostazioni.

Le opzioni di registrazione vengono impostate utilizzando il comando di PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy).

## <a name="scheduling-and-option-behaviors"></a>Comportamento di pianificazione e opzioni

Sono disponibili due opzioni per gli organizzatori durante la pianificazione della registrazione di un evento live:

- Registrazione disponibile per produttori e relatori

  - File di registrazione: fornisce un file di registrazione che i produttori e i relatori possono scaricare dopo la fine dell'evento.

- Registrazione disponibile per i partecipanti

  - DVR: un registratore video digitale (DVR) consente ai partecipanti di riavvolgere e sospendere durante l'evento

  - VOD: un video su richiesta (VOD) consente ai partecipanti di guardare dopo la fine dell'evento

## <a name="broadcast-recording-policy-setting"></a>Impostazione dei criteri di registrazione della trasmissione

Nell'ambito dei criteri di trasmissione, è disponibile un'impostazione che consente di attivare o disattivare la registrazione per un evento live.

| &nbsp;| Registrazione disponibile per produttori e relatori | Registrazione disponibile per i partecipanti |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Registra sempre               | Disabilitato e selezionato                                | Abilitato e selezionato         |
| L'organizzatore può registrare o meno | Abilitato e selezionato per impostazione predefinita                  | Abilitato e selezionato per impostazione predefinita   |
| Non registrare mai               | Disabilitato e non selezionato                            | Disabilitato e non selezionato      |

## <a name="storage-and-persistence-behavior"></a>Comportamento di archiviazione e persistenza

| Opzione                                       | Stato   | DVR                                                   | VOD                                                     | Registrazione                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Registrazione disponibile per i partecipanti | Selezionato     | DVR è disponibile e la risorsa di Azure Media Services (AMS) viene archiviata per 180 giorni | Il partecipante può accedere e guardare l'evento                     |                              |
|                                                  | Non selezionato | DVR è disponibile e la risorsa AMS viene archiviata per 180 giorni | Il partecipante non otterrà accesso all'evento dopo la fine |                              |
||Disabilitato (non selezionato)|DVR è disponibile e la risorsa AMS viene eliminata dopo l'evento|Il partecipante non otterrà accesso all'evento dopo la fine||
| Registrazione disponibile per produttori e relatori | Selezionato     |                                                           |                                                             | Viene creato e archiviato un MP4 per 180 giorni |
|                                                  | Non selezionato |                                                           |                                                             | Non viene creato alcun file           |

### <a name="related-topics"></a>Argomenti correlati

- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
- [Registrazione di riunioni di Teams cloud](../cloud-recording.md)
