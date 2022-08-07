---
title: Riunioni di Teams in streaming
author: mkbond007
ms.author: mabond
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
description: Informazioni su come configurare e gestire lo streaming per le riunioni di Teams.
ms.openlocfilehash: 5e1e84fc3b0b4ed2f81b3f3a8c84450dc3cee56c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270181"
---
# <a name="stream-teams-meetings"></a>Riunioni di Teams in streaming

Questo articolo illustra come configurare lo streaming per le riunioni di Teams.

## <a name="what-is-streaming-and-how-does-it-work"></a>Che cos'è lo streaming e come funziona?

Lo streaming consente all'organizzazione di espandere la portata dell'utente e offre ai partecipanti altre opzioni per le riunioni. Quando si abilita lo streaming, gli organizzatori possono trasmettere riunioni e webinar in streaming agli endpoint esterni fornendo un URL RTMP (Real-Time Messaging Protocol) e una chiave per l'app di streaming personalizzata integrata in Teams.

> [!NOTE]
> Non è possibile riprodurre in streaming eventi live.

## <a name="set-up-streaming-with-powershell"></a>Configurare la riproduzione in streaming con PowerShell

È possibile configurare l'organizzazione per lo streaming con PowerShell. Attualmente, questo criterio non è disponibile nell'interfaccia di amministrazione di Teams. I criteri per utente vengono usati per specificare **chi** può abilitare lo streaming live. Per impostazione predefinita l'opzione è disattivata.

È possibile utilizzare il seguente attributo all'interno del Windows PowerShell **cmdlet Set-CsTeamsMeetingPolicy per configurare** lo streaming. Per ulteriori informazioni sul cmdlet, vedi [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Imposta **LiveStreamingMode** su **Abilitato** per attivare le funzionalità di streaming per uno o più utenti.

> [!IMPORTANT]
> È necessario attivare la registrazione delle riunioni prima che gli organizzatori possano trasmettere webinar in streaming. Per altre informazioni, vedere [Configurare webinar](set-up-webinars.md).

### <a name="assign-the-policy"></a>Assegnare il criterio

Per altre informazioni su come assegnare criteri con PowerShell, vedere [Assegnare criteri in Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri in Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Guida introduttiva: riunioni, webinar ed eventi live](quick-start-meetings-live-events.md)