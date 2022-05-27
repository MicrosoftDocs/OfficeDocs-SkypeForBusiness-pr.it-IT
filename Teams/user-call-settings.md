---
title: Configurare le impostazioni delle chiamate per gli utenti
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
ms.openlocfilehash: 41d954f468166fd8600601f98ea98d5be129eccd
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681997"
---
# <a name="configure-call-settings-for-your-users"></a>Configurare le impostazioni di chiamata per gli utenti

Questo articolo descrive come l'amministratore può modificare le impostazioni di inoltro di chiamata e delega per gli utenti. È possibile modificare queste impostazioni, ad esempio se:

- Un utente è in malattia ed è necessario assicurarsi che le chiamate in arrivo all'utente vengano inoltrate a un collega.
- È necessario esaminare le impostazioni di inoltro di chiamata per tutti gli utenti di un reparto e correggerle potenzialmente nel modo appropriato.
- È stato impiegato un nuovo assistente ed è necessario aggiungerlo come delegato per un gruppo di dipendenti.

È possibile usare l'interfaccia di amministrazione di Teams o Teams cmdlet di PowerShell per visualizzare e modificare le impostazioni delle chiamate per gli utenti.

Per impostare le impostazioni di chiamata per un utente, all'utente deve essere assegnata una licenza di sistema Telefono Microsoft.

## <a name="use-the-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

È possibile usare l'interfaccia di amministrazione di Teams per configurare le impostazioni di inoltro di chiamata e senza risposta, il ritiro delle chiamate di gruppo e la delega delle chiamate per gli utenti.

Per configurare le impostazioni di inoltro di chiamata immediata:

1. Nell'interfaccia di amministrazione di Teams passare a **Gestisci utenti** >  e selezionare un utente.

2. Nella pagina dei dettagli dell'utente passare alla scheda **Voce** .

3. In **Regole di ricezione chiamata** selezionare **Inoltra immediatamente** e selezionare il tipo e la destinazione appropriati per l'inoltro di chiamata.

Per configurare lo squillo simultaneo, nella stessa pagina selezionare **Fai squillare i dispositivi dell'utente**. Nell'elenco a discesa **Consenti anche** selezionare l'impostazione appropriata per lo squillo simultaneo.

Per configurare le impostazioni senza risposta, nella stessa pagina selezionare l'impostazione appropriata nell'elenco a discesa **Se senza risposta** . Nell'elenco a discesa **Durata squilli per molti secondi prima del reindirizzamento** specificare il numero di secondi da attendere.

La configurazione della delega delle chiamate e del ritiro delle chiamate di gruppo viene integrata nelle impostazioni di inoltro di chiamata e senza risposta selezionando il tipo appropriato. Ad esempio, per configurare che le chiamate debbano squillare anche ai delegati dell'utente, nella stessa pagina selezionare **Delega chiamate** in **Consenti anche**. Quindi aggiungere i delegati appropriati selezionando **Aggiungi persone** e facendo clic su **Salva**.

## <a name="use-powershell"></a>Usare PowerShell

È possibile usare PowerShell per configurare le impostazioni di inoltro di chiamata e delega per gli utenti.  Verranno usati i cmdlet seguenti, disponibili in Teams modulo di PowerShell versione 4.0 o successiva:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) : mostra le impostazioni di inoltro di chiamata, i delegati e le informazioni sul delegante per un utente.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) : imposta le impostazioni di inoltro di chiamata per un utente.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - aggiunge un nuovo delegato con autorizzazioni per un utente.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) : modifica le autorizzazioni per un delegato esistente.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) : rimuove un delegato da un utente.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Visualizzare le impostazioni di inoltro di chiamata e delega per un utente

Per visualizzare le impostazioni di inoltro di chiamata e delega correnti per un utente, usare il cmdlet Get-CsUserCallingSettings, come illustrato nell'esempio seguente:

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
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

L'output mostra che user1 ha squillo simultaneo ai delegati configurati. Le chiamate senza risposta vengono inviate alla segreteria telefonica dopo 20 secondi. Utente2 è definito come delegato con tutte le autorizzazioni di delegato.

### <a name="set-call-forward-settings-for-a-user"></a>Impostare le impostazioni di inoltro di chiamata per un utente

Per inoltrare tutte le chiamate per user1 a user2, usare il cmdlet Set-CsUserCallingSettings, come illustrato nell'esempio seguente:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Per chiamare contemporaneamente tutti i delegati per user3, usare il cmdlet Set-CsUserCallingSettings, come illustrato nell'esempio seguente:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

L'esempio seguente usa il cmdlet Set-CsUserCallingSettings per configurare un gruppo di chiamate per user4 con user5 e user6 come membri. Tutte le chiamate ai membri del gruppo vengono inoltrate nell'ordine in cui sono definite:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Per ulteriori esempi, vedi [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Aggiungere un delegato chiamante per un utente

Per aggiungere user2 come delegato per user1 con tutte le autorizzazioni consentite, usare il cmdlet New-CsUserCallingDelegate, come illustrato nell'esempio seguente:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Modificare le autorizzazioni del delegato chiamante

Per modificare le autorizzazioni di delega, ad esempio per impedire a user2 di effettuare chiamate per user1, usare il cmdlet Set-CsUserCallingDelegate come illustrato nell'esempio seguente:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Rimuovere un delegato chiamante per un utente

Per rimuovere user2 come delegato per user1, usare il cmdlet Remove-CsUserCallingDelegate, come illustrato nell'esempio seguente:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>Argomenti correlati

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
