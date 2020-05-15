---
title: Supporto per l'utilizzo della funzionalità SEFAUtil in PowerShell in Skype for Business Server 2019
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
description: "Riepilogo: informazioni su come utilizzare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: 24040a3da5dc2549996463078a55324f3fc03657
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232567"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utilizzo della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019

SEFAUtil (funzione di estensione secondaria) consente agli amministratori e ai consulenti helpdesk di Skype for Business Server di configurare le impostazioni di squillo delegati, di inoltro di chiamata e di prelievo delle chiamate di gruppo per conto di un utente di Skype for Business Server. Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico. Dopo aver installato l'aggiornamento cumulativo di Skype for Business Server 2019 luglio, la funzionalità seguente che può essere gestita solo tramite SEFAUtil sarà gestibile anche tramite PowerShell:

- [Impostazioni di inoltro di chiamata](#call-forwarding-settings)
- [Impostazioni di delega](#delegation-settings)
- [Membri del team e impostazioni correlate](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Impostazioni di inoltro di chiamata

Gli amministratori possono modificare le impostazioni di inoltro di chiamata utilizzando il cmdlet seguente in PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Questo cmdlet consente di modificare le impostazioni di inoltro di chiamata dell'utente specificato. Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet consente di disabilitare le impostazioni di inoltro di chiamata dell'utente (vengono mostrati due esempi di parametri diversi).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Questo cmdlet consente di modificare le impostazioni di inoltro di chiamata dell'utente.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Questo cmdlet consente di modificare le impostazioni di SimulRing (di nuovo, con due esempi di parametri, uno per la segreteria telefonica senza risposta e il secondo senza risposta ad altri).

## <a name="delegation-settings"></a>Impostazioni di delega

Gli amministratori possono modificare le impostazioni di delega utilizzando il cmdlet seguente in PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati dell'utente specificato, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Questo cmdlet consente di modificare le impostazioni di delega dell'utente specificato, di restituire un oggetto dell'elenco delegati e di visualizzare l'elenco dei delegati, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove un delegato.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Questo cmdlet consente di impostare un elenco di delegati per deleghe specifici.

## <a name="team-members-and-related-settings"></a>Membri del team e impostazioni correlate

Gli amministratori possono modificare i membri del team e le impostazioni correlate utilizzando il cmdlet seguente in PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Questo cmdlet restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Questo cmdlet consente di modificare l'elenco dei membri del team dell'utente specificato, di restituire un oggetto che contiene l'elenco dei membri del team e di visualizzare l'oggetto sullo schermo, in caso di esito positivo. In caso di errore, verrà visualizzato un messaggio di errore appropriato.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Questo cmdlet aggiunge o rimuove i membri del team.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Questo cmdlet imposta un elenco di team per membri specifici.

## <a name="more-information"></a>Ulteriori informazioni

Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, per il livello di accesso specificato di seguito:

- CsAdministrator-Get e set per tutti i cmdlet
- CsVoiceAdministrator-Get e set per tutti i cmdlet
- CsHelpDesk-Get per tutti i cmdlet

Per ulteriori informazioni su questi ruoli di amministratore, vedere [creare gli amministratori del pannello di controllo di Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L'amministratore può accedere a questi cmdlet direttamente o in remoto accedendo a un computer server.
Per una distribuzione ibrida, gli amministratori di Skype for business dovrebbero essere in grado di chiamare Get e set per tutti i cmdlet. Per ulteriori informazioni sull'elenco completo dei ruoli, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> L'individuazione automatica del server deve essere abilitata. Non verranno introdotti ulteriori requisiti di licenza per l'utilizzo dei cmdlet.
