---
title: Criteri di registrazione degli eventi live
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
description: Informazioni sui criteri di registrazione degli eventi live.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c0f5f089bf4f1a0dc2c28a0b718d89b9200a4676
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587335"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Criteri di registrazione degli eventi live in Microsoft Teams

Sono disponibili diverse opzioni per registrare un evento Microsoft Teams live. Le opzioni di registrazione vengono impostate usando i criteri di registrazione. Questo articolo descrive le varie impostazioni.

Le opzioni di registrazione vengono impostate usando il comando di PowerShell [Set-CsTeamsMeetingBroadcastPolicy.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)

## <a name="scheduling-and-option-behaviors"></a>Comportamenti di pianificazione e opzioni

Durante la pianificazione di una registrazione di un evento live sono disponibili due opzioni per l'organizzatore:

- Registrazione disponibile per produttori e relatori

  - File di registrazione: fornisce un file di registrazione che i produttori e i relatori possono scaricare al termine dell'evento.

- Registrazione disponibile per i partecipanti

  - DVR: un videoregistratore digitale (DVR) consente ai partecipanti di riavvolgere e mettere in pausa durante l'evento

  - VOD: un video su richiesta (VOD) consente ai partecipanti di guardare al termine dell'evento

## <a name="broadcast-recording-policy-setting"></a>Impostazione dei criteri di registrazione broadcast

Nell'ambito dei criteri di trasmissione, è possibile attivare o disattivare la registrazione per un evento live.

| &nbsp;| Registrazione disponibile per produttori e relatori | Registrazione disponibile per i partecipanti |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Registra sempre               | Disabilitato e selezionato                                | Abilitato e selezionato         |
| L'organizzatore può registrare o meno | Abilitato e selezionato per impostazione predefinita                  | Abilitato e selezionato per impostazione predefinita   |
| Non registrare mai               | Disabilitato e non selezionato                            | Disabilitato e non selezionato      |

## <a name="storage-and-persistence-behavior"></a>Archiviazione e persistenza

| Opzione                                       | Stato   | DVR                                                   | VOD                                                     | Registrazione                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Registrazione disponibile per i partecipanti | Selezionato     | DVR è disponibile e la risorsa Servizi multimediali di Azure (AMS) viene archiviata per 180 giorni | Il partecipante può accedere e guardare l'evento                     |                              |
|                                                  | Non selezionato | DVR è disponibile e la risorsa AMS viene archiviata per 180 giorni | Il partecipante non ottiene l'accesso all'evento al termine |                              |
||Disabilitato (non selezionato)|DVR è disponibile e la risorsa AMS viene eliminata dopo l'evento|Il partecipante non ottiene l'accesso all'evento al termine||
| Registrazione disponibile per produttori e relatori | Selezionato     |                                                           |                                                             | Viene creato e archiviato un MP4 |
|                                                  | Non selezionato |                                                           |                                                             | Non viene creato alcun file           |

### <a name="related-topics"></a>Argomenti correlati

- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
- [Teams delle riunioni in cloud](../cloud-recording.md)
