---
title: Criteri per la registrazione di eventi live
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni sui criteri di registrazione di eventi live.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615175"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Criteri per la registrazione di eventi live in Microsoft Teams

Sono disponibili diverse opzioni per registrare un evento live di Microsoft Teams. Le opzioni di registrazione vengono impostate usando i criteri di registrazione. Questo articolo descrive le varie impostazioni.

Le opzioni di registrazione vengono impostate usando il comando di PowerShell [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)

## <a name="scheduling-and-option-behaviors"></a>Pianificazione e comportamenti delle opzioni

Durante la pianificazione di una registrazione di un evento live sono disponibili due opzioni per l'organizzatore:

- Registrazione disponibile per produttori e relatori

  - File di registrazione: fornisce un file di registrazione che produttori e relatori possono scaricare al termine dell'evento.

- Registrazione disponibile per i partecipanti

  - DVR: un registratore video digitale (DVR) consente ai partecipanti di riavvolgere e fermarsi durante l'evento

  - VOD: un video su richiesta (VOD) consente ai partecipanti di guardarsi una volta finito l'evento

## <a name="broadcast-recording-policy-setting"></a>Impostazione dei criteri di registrazione per le trasmissioni

Nell'ambito dei criteri di trasmissione è presente un'impostazione che consente di attivare o disattivare la registrazione per un evento live.

|                                 | Registrazione disponibile per produttori e relatori | Registrazione disponibile per i partecipanti |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Registra sempre               | Disabilitato e selezionato                                | Disabilitato e selezionato         |
| L'organizzatore può registrare o meno | Abilitato e non selezionato per impostazione predefinita                  | Abilitato e non selezionato per impostazione predefinita   |
| Non registrare mai               | Disabilitato e non selezionato                            | Disabilitato e non selezionato      |

Quando il criterio è impostato su **Registra sempre,** nella pagina dei criteri sono selezionate le opzioni seguenti:

![Impostazioni dei criteri per gli eventi live](../media/live-event-recording-policy.png "Screenshot dell'impostazione dei criteri per gli eventi live nell'interfaccia di amministrazione di Microsoft Teams.")

## <a name="storage-and-persistence-behavior"></a>Comportamento di archiviazione e persistenza

| Opzione                                       | Stato   | DVR                                                   | VOD                                                     | Registrazione                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Registrazione disponibile per produttori e relatori | Selezionato     | DVR è disponibile e la risorsa Servizi multimediali di Azure è archiviata per 180 giorni | Il partecipante può accedere all'evento e guardarlo                     |                              |
|                                                  | Non selezionato | DVR è disponibile e la risorsa AMS viene archiviata per 180 giorni | Al termine dell'evento, il partecipante non accederà all'evento |                              |
||Disabilitato (non selezionato)|DVR è disponibile e la risorsa AMS viene eliminata dopo l'evento|Al termine dell'evento, il partecipante non accederà all'evento||
| Registrazione disponibile per produttori e relatori | Selezionato     |                                                           |                                                             | Viene creato e archiviato un file MP4 |
|                                                  | Non selezionato |                                                           |                                                             | Non viene creato alcun file           |

### <a name="related-topics"></a>Argomenti correlati

- [Che cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
- [Registrazione riunione nel cloud di Teams](../cloud-recording.md)
