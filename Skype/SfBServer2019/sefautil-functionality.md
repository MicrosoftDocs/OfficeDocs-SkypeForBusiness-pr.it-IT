---
title: Supporto per l'uso della funzionalità SEFAUtil in Skype PowerShell in Skype for Business Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come usare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676538"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Uso della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019

SEFAUtil (attivazione delle funzionalità dell'estensione secondaria) consente agli amministratori e agli agenti dell'help desk di Skype for Business Server di configurare le impostazioni di delega, inoltro di chiamata e ritiro delle chiamate di gruppo per conto degli utenti Skype for Business Server. SEFAUtil consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate per un utente specifico.

Dopo aver installato l'aggiornamento cumulativo di luglio Skype for Business Server 2019, le funzionalità seguenti disponibili solo tramite SEFAUtil saranno disponibili anche in Skype PowerShell:

- [Impostazioni di inoltro di chiamata](#call-forwarding-settings)
- [Impostazioni di delega](#delegation-settings)
- [Membri del team e impostazioni correlate](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Impostazioni di inoltro di chiamata

Gli amministratori possono modificare le impostazioni di inoltro di chiamata usando i comandi seguenti in PowerShell:

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Questo comando restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso valore sullo schermo.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Questo comando modifica le impostazioni di inoltro di chiamata dell'utente specificato. Questo comando restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso valore sullo schermo. Se il comando non ha esito positivo, verrà visualizzato un messaggio di errore appropriato.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Questo comando disabilita le impostazioni di inoltro di chiamata dell'utente .We show two different parameter examples here.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Questo comando modifica le impostazioni di inoltro di chiamata dell'utente.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Questo comando modifica le impostazioni dell'anello simultanee (anche in questo caso, con due esempi di parametri, uno per la mancata risposta alla segreteria telefonica e il secondo non ha risposta all'altro).

## <a name="delegation-settings"></a>Impostazioni di delega

Gli amministratori possono modificare le impostazioni di delega usando il comando seguente in PowerShell:

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Questo comando restituisce un oggetto dell'elenco di delegati e visualizza l'elenco di delegati dell'utente specificato. Se il comando non ha esito positivo, verrà visualizzato un messaggio di errore appropriato.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Questo comando modifica le impostazioni di delega dell'utente specificato, restituisce un oggetto dell'elenco dei delegati e visualizza l'elenco dei delegati. Se il comando non ha esito positivo, verrà visualizzato un messaggio di errore appropriato.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Questo comando aggiunge o rimuove un delegato.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Questo comando imposta un elenco di delegati su delegati specifici.

## <a name="team-members-and-related-settings"></a>Membri del team e impostazioni correlate

Gli amministratori possono modificare i membri del team e le impostazioni correlate usando il comando seguente in PowerShell:

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Questo comando restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo. Se il comando non ha esito positivo, verrà visualizzato un messaggio di errore appropriato.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Questo comando modifica l'elenco dei membri del team dell'utente specificato, restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo. Se il comando non ha esito positivo, verrà visualizzato un messaggio di errore appropriato.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Questo comando aggiunge o rimuove i membri del team.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Questo comando imposta un elenco di team su membri specifici.

## <a name="more-information"></a>Ulteriori informazioni

Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, in base al livello di accesso specificato di seguito:

- CsAdministrator - Ottenere e impostare per tutti i cmdlet
- CsVoiceAdministrator - Ottenere e impostare per tutti i cmdlet
- CsHelpDesk - Ottenere per tutti i cmdlet

Per altre informazioni su questi ruoli di amministratore, vedere [Creare amministratori Skype for Business Server Pannello di controllo](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L'amministratore può accedere a questi cmdlet direttamente o in remoto accedendo a un computer server.
Per una distribuzione ibrida, gli amministratori Skype for Business devono essere in grado di chiamare Get e Set per tutti i cmdlet. Per altre informazioni sull'elenco completo dei ruoli, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> L'individuazione automatica del server deve essere abilitata. Non verranno introdotti altri requisiti di licenza per l'uso dei cmdlet.
