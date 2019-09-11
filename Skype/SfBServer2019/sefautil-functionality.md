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
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come usare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: 6652e3b76a31ac4b315c70498ac2b01d4467b70e
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838099"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Uso della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019

SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori di Skype for Business Server e agli agenti helpdesk di configurare le impostazioni di chiamata delegata, di inoltro delle chiamate e di gruppo per conto di un utente di Skype for Business Server. Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente. Dopo aver installato l'aggiornamento cumulativo di Skype for Business Server 2019 luglio, le funzionalità seguenti che possono essere gestite solo tramite SEFAUtil saranno gestibili anche tramite PowerShell:

- [Impostazioni inoltro di chiamata](#call-forwarding-settings)
- [Impostazioni di delega](#delegation-settings)
- [Membri del team e impostazioni correlate](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Impostazioni inoltro di chiamata

Gli amministratori possono modificare le impostazioni di inoltro di chiamata usando il cmdlet seguente in PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente specificato. Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo, in caso di esito positivo. In caso di errore verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet disabilita le impostazioni di inoltro di chiamata dell'utente (qui vengono mostrati due diversi esempi di parametri).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Questo cmdlet modifica le impostazioni di SimulRing (di nuovo, con due esempi di parametri, uno per la segreteria telefonica senza risposta e il secondo senza risposta ad altri).

## <a name="delegation-settings"></a>Impostazioni di delega

Gli amministratori possono modificare le impostazioni di delega usando il cmdlet seguente in PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati dell'utente specificato in caso di esito positivo. In caso di errore verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Questo cmdlet modifica le impostazioni di delega dell'utente specificato, restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati, in caso di esito positivo. In caso di errore verrà visualizzato un messaggio di errore appropriato. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove un delegato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Questo cmdlet imposta un elenco delegato su delegati specifici.

## <a name="team-members-and-related-settings"></a>Membri del team e impostazioni correlate

Gli amministratori possono cambiare i membri del team e le impostazioni correlate usando il cmdlet seguente in PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo. In caso di errore verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Questo cmdlet modifica l'elenco dei membri del team dell'utente specificato, restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo. In caso di errore verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove i membri del team.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Questo cmdlet imposta un elenco di Team su membri specifici.

## <a name="more-information"></a>Ulteriori informazioni

Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, per il livello di accesso specificato di seguito:

- CsAdministrator-ottenere e impostare per tutti i cmdlet
- CsVoiceAdministrator-ottenere e impostare per tutti i cmdlet
- CsHelpDesk-Get per tutti i cmdlet

Per altre informazioni su questi ruoli di amministratore, vedere [creare amministratori del pannello di controllo di Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L'amministratore può accedere a questi cmdlet direttamente o in remoto accedendo a un computer server.
Per una distribuzione ibrida, gli amministratori di Skype for business dovrebbero poter chiamare Get e set per tutti i cmdlet. Per altre informazioni sull'elenco completo dei ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> L'individuazione automatica del server deve essere abilitata. Non verranno introdotti requisiti di licenza aggiuntivi per l'uso dei cmdlet.
