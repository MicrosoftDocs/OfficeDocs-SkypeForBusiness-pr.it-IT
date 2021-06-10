---
title: Gestire i criteri vocali e delle chiamate in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni sui criteri Teams vocali e chiamate.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460586"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Gestire i criteri vocali e delle chiamate in Microsoft Teams

I criteri vocali e di chiamata vengono usati per controllare la voce e le chiamate in Microsoft Teams.

## <a name="emergency-calling-policies"></a>Criteri per le chiamate di emergenza

I criteri per [le chiamate di emergenza](manage-emergency-calling-policies.md) vengono utilizzati per configurare ciò che accade quando un utente dell'organizzazione effettua una chiamata di emergenza. Questi criteri vengono gestiti nell'interfaccia Teams di amministrazione o usando Windows PowerShell.

![Screenshot dei criteri per le chiamate di emergenza.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Criteri di routing delle chiamate di emergenza

Se l'organizzazione ha distribuito **Sistema telefonico Routing** [](manage-emergency-call-routing-policies.md) diretto, è possibile usare i criteri di routing delle chiamate di emergenza per determinare dove vengono instradati le chiamate di emergenza, se sono abilitati i servizi di emergenza ottimizzati e quali numeri vengono usati per i servizi di emergenza. Questi criteri vengono gestiti con PowerShell o nell'Microsoft Teams di amministrazione.

![Screenshot dei criteri di routing delle chiamate di emergenza.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Criteri id chiamante

[I criteri id chiamante](caller-id-policies.md) vengono usati per modificare o bloccare l'ID chiamante.

![Screenshot dei criteri per l'ID chiamante.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Criteri di routing vocale

Un [criterio di routing vocale](manage-voice-routing-policies.md) è un contenitore per i record di utilizzo PSTN (Public Switched Telephone Network). È possibile usare questi criteri se l'organizzazione ha distribuito Sistema telefonico **Routing diretto**. I criteri di routing vocale possono essere gestiti con PowerShell o nell'Teams di amministrazione.

![Screenshot dei criteri di routing vocale.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Criteri di chiamata

[I criteri di](teams-calling-policy.md) chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti, ad esempio se un utente può effettuare chiamate private, inviare chiamate a gruppi di chiamate e instradare le chiamate alla segreteria telefonica.

![Screenshot dei criteri di chiamata.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Parcheggio di chiamata e criteri di recupero

[Il parcheggio di chiamata e il recupero](call-park-and-retrieve.md) consentono agli utenti di mettere in attesa altri utenti e consente allo stesso utente o a un altro utente di continuare la chiamata.

![Screenshot del parco chiamate e dei criteri di recupero.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Creare e impostare dial plan

[I dial plan traducono](create-and-manage-dial-plans.md) i numeri di telefono dialed per l'autorizzazione e l'instradamento delle chiamate. È possibile creare e gestire i dial plan tramite PowerShell o nell'Microsoft Teams di amministrazione.

![Screenshot del piano di chiamata.](media/dial-plans.png)

## <a name="related-topics"></a>Argomenti correlati

* [Gestire i criteri per le chiamate di emergenza in Microsoft Teams](manage-emergency-calling-policies.md)
* [Gestire i criteri del routing delle chiamate di emergenza](manage-emergency-call-routing-policies.md)
* [Gestire i criteri dell'ID chiamante in Microsoft Teams](caller-id-policies.md)
* [Gestire i criteri di routing vocale](manage-voice-routing-policies.md)
* [Criteri di chiamata in Microsoft Teams](teams-calling-policy.md)
* [Parcheggio di chiamata e recupero in Microsoft Teams](call-park-and-retrieve.md)
* [Creare e impostare dial plan](create-and-manage-dial-plans.md)
* [Gestire Teams con i criteri](manage-teams-with-policies.md)
