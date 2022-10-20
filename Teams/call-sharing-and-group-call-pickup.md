---
title: Condivisione delle chiamate e risposta alle chiamate di gruppo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: La condivisione delle chiamate e il ritiro delle chiamate di gruppo in Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613848"
---
# <a name="call-sharing-and-group-call-pickup"></a>Condivisione delle chiamate e risposta alle chiamate di gruppo

Le funzionalità di condivisione delle chiamate e di ritiro delle chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile.

Il ritiro delle chiamate di gruppo è meno fastidioso per i destinatari rispetto ad altre forme di condivisione delle chiamate perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo e possono decidere se rispondere. L'ordine in cui i membri del gruppo di chiamata vengono informati della chiamata in arrivo può essere specificato come simultaneo o in ordine (con 5 o meno membri).

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamata e i membri del gruppo di chiamata devono essere in modalità di distribuzione solo in Teams. Per altri dettagli sulle modalità di distribuzione di Teams, vedere [Informazioni su Microsoft Teams e la coesistenza e l'interoperabilità di Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licenza richiesta

Agli utenti deve essere assegnata una licenza di sistema Telefono di Microsoft Teams per configurare e utilizzare la condivisione delle chiamate e il ritiro delle chiamate di gruppo. Per altri dettagli sul modello di licenza, vedi [Ecco cosa ottieni con Sistema telefonico](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="limitations"></a>Limitazioni

Un utente può essere proprietario di un solo gruppo di chiamate. Ogni gruppo di chiamata configurato può avere un massimo di 25 utenti o 32.768 caratteri. Un utente può essere membro di un massimo di 25 gruppi di chiamate.

Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.

## <a name="enable-the-use-of-group-call-pickup"></a>Abilitare l'uso del ritiro delle chiamate di gruppo

È possibile abilitare i gruppi di chiamata configurando l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente. È possibile usare l'interfaccia di amministrazione di Teams o PowerShell. Quando l'opzione è abilitata, l'utente può configurare i propri gruppi di chiamate nel client di Teams. 

Importante: quando si disattivano i gruppi di chiamate per gli utenti, è necessario pulire le relazioni dei gruppi di chiamata per gli utenti nell'interfaccia di amministrazione di Teams per evitare un routing delle chiamate errato. 

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

Per configurare il ritiro delle chiamate di gruppo per gli utenti tramite l'interfaccia di amministrazione di Teams, vedere [Configurare le impostazioni delle chiamate per gli utenti](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usare PowerShell

Per configurare i gruppi di chiamate per gli utenti, usare i cmdlet del modulo PowerShell di Teams seguenti:

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>Esempi

L'esempio seguente crea un gruppo di chiamate per user1@contoso.com con i membri user2@contoso.com e user3@contoso.com e imposta l'inoltro di chiamata immediato al gruppo di chiamata per user1@contoso.com:

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Nell'esempio seguente viene illustrato come aggiornare il gruppo di chiamate di user1@contoso.com per aggiungere user5@contoso.com e rimuovere user6@contoso.com:

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>Altre informazioni

[Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Criteri per le chiamate di Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
