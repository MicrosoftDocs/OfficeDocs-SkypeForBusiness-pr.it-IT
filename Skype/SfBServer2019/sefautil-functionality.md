---
title: Supporto per l'uso della funzionalità SEFAUtil in PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come usare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: d97dd84a3d05cf18752e40dd73a8c5f7e9752d3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120507"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utilizzo della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019

SEFAUtil (Secondary Extension Feature Activation) consente agli amministratori di Skype for Business Server e agli agenti helpdesk di configurare le impostazioni di squillo delegato, inoltro di chiamata e prelievo chiamata di gruppo per conto di un utente di Skype for Business Server. Questo strumento consente inoltre agli amministratori di eseguire query nelle impostazioni di routing delle chiamate pubblicate per un determinato utente. Dopo aver installato l'aggiornamento cumulativo di luglio 2019 di Skype for Business Server, le funzionalità seguenti che attualmente possono essere gestite solo tramite SEFAUtil saranno gestibili anche tramite PowerShell:

- [Impostazioni di inoltro di chiamata](#call-forwarding-settings)
- [Impostazioni di delega](#delegation-settings)
- [Membri del team e impostazioni correlate](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Impostazioni di inoltro di chiamata

Gli amministratori possono modificare le impostazioni di inoltro di chiamata utilizzando il cmdlet seguente in PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente specificato. Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet disabilita le impostazioni di inoltro di chiamata dell'utente (qui vengono mostrati due diversi esempi di parametri).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Questo cmdlet modifica le impostazioni di SimulRing (anche in questo caso, con due esempi di parametri, uno per la segreteria telefonica senza risposta e il secondo senza risposta ad altri).

## <a name="delegation-settings"></a>Impostazioni di delega

Gli amministratori possono modificare le impostazioni di delega utilizzando il cmdlet seguente in PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto elenco di delegati e visualizza l'elenco dei delegati dell'utente specificato, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Questo cmdlet modifica le impostazioni di delega dell'utente specificato, restituisce un oggetto elenco di delegati e visualizza l'elenco dei delegati, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove un delegato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Questo cmdlet imposta un elenco di delegati su delegati specifici.

## <a name="team-members-and-related-settings"></a>Membri del team e impostazioni correlate

Gli amministratori possono modificare i membri del team e le impostazioni correlate utilizzando il cmdlet seguente in PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto contenente l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Questo cmdlet modifica l'elenco dei membri del team dell'utente specificato, restituisce un oggetto contenente l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove i membri del team.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Questo cmdlet imposta un elenco di team su membri specifici.

## <a name="more-information"></a>Ulteriori informazioni

Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, in base al livello di accesso specificato di seguito:

- CsAdministrator : get e set per tutti i cmdlet
- CsVoiceAdministrator - Get e Set per tutti i cmdlet
- CsHelpDesk - Get per tutti i cmdlet

Per ulteriori informazioni su questi ruoli di amministratore, vedere [Create Skype for Business Server Control Panel Administrators.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) L'amministratore può accedere a questi cmdlet accedendo direttamente o in remoto a un computer server.
Per una distribuzione ibrida, gli amministratori di Skype for Business dovrebbero essere in grado di chiamare Get e Set per tutti i cmdlet. Per ulteriori informazioni sull'elenco completo dei ruoli, vedere [Informazioni sui ruoli di amministratore.](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> L'individuazione automatica del server deve essere abilitata. Non verranno introdotti ulteriori requisiti di licenza per l'utilizzo dei cmdlet.