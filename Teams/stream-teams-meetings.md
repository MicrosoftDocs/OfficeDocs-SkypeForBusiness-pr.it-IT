---
title: Trasmettere in Teams riunioni
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Scopri come configurare e gestire lo streaming per le riunioni Teams riunioni.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127546"
---
# <a name="stream-teams-meetings"></a>Trasmettere in Teams riunioni

Questo articolo ti aiuterà a configurare lo streaming per Teams riunioni.

## <a name="what-is-streaming-and-how-does-it-work"></a>Che cos'è lo streaming e come funziona?

Lo streaming consente all'organizzazione di espandere la portata e offre ai partecipanti alla riunione più opzioni per le riunioni. Quando si abilita lo streaming, gli organizzatori possono trasmettere riunioni e webinar a endpoint esterni fornendo un URL RTMP (Real-Time Messaging Protocol) e una chiave per l'app di streaming personalizzata predefinita in Teams.

> [!NOTE]
> Non è possibile trasmettere in streaming eventi live.

## <a name="set-up-streaming-with-powershell"></a>Configurare lo streaming con PowerShell

È possibile configurare l'organizzazione per lo streaming con PowerShell. Attualmente, questo criterio non è disponibile nell'Teams di amministrazione. I criteri per utente vengono usati per specificare gli utenti **che possono** abilitare lo streaming live. Per impostazione predefinita l'opzione è disattivata.

È possibile usare l'attributo Windows PowerShell seguente nel cmdlet **Set-CsTeamsMeetingPolicy all'interno del cmdlet Set-CsTeamsMeetingPolicy** per configurare lo streaming. Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Impostare **LiveStreamingMode** su **Enabled per** attivare le funzionalità di streaming per uno o più utenti.

> [!IMPORTANT]
> È necessario attivare la registrazione della riunione prima che gli organizzatori possano trasmettere webinar. Per altre informazioni, vedere [Configurare webinar.](set-up-webinars.md)

### <a name="assign-the-policy"></a>Assegnare il criterio

Per altre informazioni su come assegnare criteri con PowerShell, vedere [Assegnare criteri in Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri in Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Guida introduttiva: riunioni, webinar ed eventi live](quick-start-meetings-live-events.md)