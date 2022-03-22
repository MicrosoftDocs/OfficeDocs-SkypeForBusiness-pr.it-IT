---
title: Configurare le impostazioni di chiamata per gli utenti
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Informazioni su come configurare le impostazioni utente per l'inoltro di chiamata e la delega.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689122"
---
# <a name="configure-call-settings-for-your-users"></a>Configurare le impostazioni di chiamata per gli utenti

Questo articolo descrive come l'amministratore può modificare le impostazioni di inoltro di chiamata e delega per gli utenti. È consigliabile modificare queste impostazioni, ad esempio se:

- Un utente è in malattia ed è necessario assicurarsi che le chiamate in arrivo all'utente siano inoltrate a un collega.

- È necessario controllare le impostazioni di inoltro di chiamata per tutti gli utenti di un reparto e correggerle in base alle esigenze.

- È stato assunto un nuovo assistente ed è necessario aggiungere l'assistente come delegato per un gruppo di dipendenti.

È possibile usare l Teams di amministrazione o Teams cmdlet di PowerShell per visualizzare e modificare le impostazioni delle chiamate per gli utenti.

Per impostare le impostazioni di chiamata per un utente, l'utente deve avere una licenza Telefono Microsoft di sistema.

## <a name="use-the-teams-admin-center"></a>Usare l'Teams di amministrazione

È possibile usare l'interfaccia Teams di amministrazione per configurare il ritiro delle chiamate di gruppo e la delega delle chiamate per gli utenti. 

> [!NOTE]
> L'opzione per la configurazione delle impostazioni di inoltro di chiamata non è attualmente disponibile nell'Teams di amministrazione.

Per configurare il ritiro delle chiamate di gruppo:

1. Nell'Teams di amministrazione passare a **UtentiManage**  >  utenti e selezionare un utente.

2. Nella pagina dei dettagli dell'utente passare alla **scheda** Voce.

3. In **Ritiro chiamata di gruppo** selezionare **Aggiungi persone**. 

4. Specificare le impostazioni per **Ritardo chiamata e ordine**.

Per configurare la delega, nella stessa pagina passare a **Delega chiamata** e selezionare **Aggiungi persone**.

## <a name="use-powershell"></a>Usare PowerShell

È possibile usare PowerShell per configurare le impostazioni di inoltro di chiamata e delega per gli utenti.  Si useranno i cmdlet seguenti, disponibili nel modulo Teams PowerShell versione 4.0 o successiva:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) : mostra le impostazioni di inoltro di chiamata, i delegati e le informazioni sul delegante per un utente.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) : imposta le impostazioni di inoltro di chiamata per un utente.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) : aggiunge un nuovo delegato con le autorizzazioni per un utente.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) : modifica le autorizzazioni per un delegato esistente.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) : rimuove un delegato da un utente.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Visualizzare le impostazioni di inoltro di chiamata e delega per un utente

Per visualizzare le impostazioni correnti di inoltro di chiamata e delega per un utente, usare il cmdlet Get-CsUserCallingSettings, come illustrato nell'esempio seguente:

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

L'output mostra che l'utente1 ha squillo simultaneo ai delegati configurati. Le chiamate senza risposta vengono inviate alla segreteria telefonica dopo 20 secondi. Utente2 è definito come delegato con tutte le autorizzazioni di delegato.


### <a name="set-call-forward-settings-for-a-user"></a>Impostare le impostazioni di inoltro di chiamata per un utente

Per inoltrare tutte le chiamate per user1 a user2, usare il cmdlet Set-CsUserCallingSettings, come illustrato nell'esempio seguente: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Per squillare contemporaneamente tutti i delegati per user3, usare il cmdlet Set-CsUserCallingSettings, come illustrato nell'esempio seguente: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

L'esempio seguente usa il cmdlet Set-CsUserCallingSettings per configurare un gruppo di chiamate per user4 con user5 e user6 come membri. Tutte le chiamate ai membri del gruppo vengono inoltrate nell'ordine in cui sono definiti: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Per altri esempi, vedere [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Aggiungere un delegato chiamante per un utente

Per aggiungere user2 come delegato per user1 con tutte le autorizzazioni consentite, usare il cmdlet New-CsUserCallingDelegate, come illustrato nell'esempio seguente: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Modificare le autorizzazioni dei delegati chiamanti

Per modificare le autorizzazioni dei delegati, ad esempio per non consentire a user2 di effettuare chiamate per user1, usare il cmdlet Set-CsUserCallingDelegate, come illustrato nell'esempio seguente: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Rimuovere un delegato chiamante per un utente

Per rimuovere user2 come delegato per user1, usare il cmdlet Remove-CsUserCallingDelegate, come illustrato nell'esempio seguente: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Argomenti correlati

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
