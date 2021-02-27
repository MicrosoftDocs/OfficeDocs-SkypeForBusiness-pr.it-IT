---
title: Gestire i criteri di chiamata e voce in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348035"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Gestire i criteri di chiamata e voce in Microsoft Teams

I criteri di chiamata e voce vengono utilizzati per controllare le chiamate e le chiamate in Microsoft Teams.

## <a name="emergency-calling-policies"></a>Criteri per le chiamate di emergenza

I criteri per [le chiamate di emergenza vengono](manage-emergency-calling-policies.md) utilizzati per configurare cosa accade quando un utente dell'organizzazione effettua una chiamata di emergenza. Questi criteri vengono gestiti nell'interfaccia di amministrazione di Teams o tramite Windows PowerShell.

![Schermata dei criteri per le chiamate di emergenza.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Criteri per l'instradamento delle chiamate di emergenza

Se l'organizzazione ha implementato l'instradamento diretto del sistema **telefonico,** è possibile utilizzare i criteri di instradamento delle chiamate di emergenza per determinare dove vengono instradati le chiamate di emergenza, se sono abilitati o meno i servizi di emergenza e quali numeri sono utilizzati per i servizi di emergenza. [](manage-emergency-call-routing-policies.md) Questi criteri vengono gestiti tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.

![Screenshot dei criteri di instradamento delle chiamate di emergenza.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Criteri ID chiamante

[I criteri ID chiamante](caller-id-policies.md) vengono usati per modificare o bloccare l'ID chiamante.

![Screenshot del criterio ID chiamante.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Criteri di routing vocale

Un [criterio di routing](manage-voice-routing-policies.md) vocale è un contenitore per i record di utilizzo PSTN (Public Switched Telephone Network). È possibile usare questi criteri se l'organizzazione ha distribuito **l'instradamento diretto del sistema telefonico.** I criteri di routing vocale possono essere gestiti con PowerShell o nell'interfaccia di amministrazione di Teams.

![Screenshot dei criteri di instradamento vocale.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Criteri di chiamata

[I criteri di](teams-calling-policy.md) chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti, tra cui se un utente può effettuare chiamate private, inviare chiamate ai gruppi di chiamata e instradare le chiamate alla segreteria telefonica.

![Screenshot del criterio di chiamata.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Chiamare il parco e recuperare i criteri

[Il call park e il recupero](call-park-and-retrieve.md) consentono agli utenti di mettere in attesa altri utenti e consentire allo stesso utente o a qualcun altro di continuare la chiamata.

![Screenshot del parco chiamate e recupera i criteri.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Creare e impostare piani di chiamata

[I piani di chiamata](create-and-manage-dial-plans.md) traducono i numeri di telefono composto per l'autorizzazione e l'instradamento delle chiamate. È possibile creare e gestire piani di chiamata tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.

![Schermata del piano di chiamata.](media/dial-plans.png)

## <a name="related-topics"></a>Argomenti correlati

* [Gestire i criteri per le chiamate di emergenza in Microsoft Teams](manage-emergency-calling-policies.md)
* [Gestire i criteri del routing delle chiamate di emergenza](manage-emergency-call-routing-policies.md)
* [Gestire i criteri ID chiamante in Microsoft Teams](caller-id-policies.md)
* [Gestire i criteri di routing vocale](manage-voice-routing-policies.md)
* [Criteri per le chiamate in Microsoft Teams](teams-calling-policy.md)
* [Chiamare il parco e recuperare in Microsoft Teams](call-park-and-retrieve.md)
* [Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)
* [Gestire Teams con i criteri](manage-teams-with-policies.md)
