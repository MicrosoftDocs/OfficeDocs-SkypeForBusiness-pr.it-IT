---
title: Aspetto condiviso della linea in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
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
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Informazioni sulla funzionalità Condividi l'aspetto della linea in Microsoft Teams.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614098"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aspetto condiviso della linea in Microsoft Teams

L'aspetto della riga condivisa consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per suo conto. Questa funzionalità è utile se un utente ha un assistente amministrativo che gestisce regolarmente le chiamate dell'utente. Nel contesto dell'aspetto della riga condivisa, un responsabile è una persona che autorizza un delegato a effettuare o ricevere chiamate per suo conto. Un delegato può effettuare o ricevere chiamate per conto del delegante.

> [!IMPORTANT]
> Questa funzionalità è disponibile solo in modalità di distribuzione di Teams. Per altri dettagli sulle modalità di distribuzione di Teams, vedere [Informazioni su Microsoft Teams e coesistenza e interoperabilità di Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Sia i responsabili che i delegati devono avere una licenza Sistema telefonico con connettività PSTN (Piano per chiamate, Connessione operatore o Routing diretto). L'esperienza di linea condivisa fa parte della delega ed è inclusa in Sistema telefonico. Per altre informazioni sulle licenze, vedere [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="shared-line-appearance-feature-availability"></a>Disponibilità della funzionalità Aspetto linea condivisa

L'aspetto della linea condivisa è attualmente supportato dalle app e dai dispositivi seguenti.

| Funzionalità | Teams Desktop | Teams Mac App | Teams Web App (Edge) |App Teams per dispositivi mobili iOS/Android | Telefono IP teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurare la delega | Sì | Sì | Sì | No | Sì |
| Ricevere chiamate per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un numero di telefono per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un utente di Teams per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Visualizzare la visualizzazione delegato delle righe condivise | Sì | Sì | Sì | No | Sì |
| Visualizzare la visualizzazione delegato delle attività di chiamata del responsabile | Sì | Sì | Sì | No | Sì |
| Visualizzare la visualizzazione responsabile dei delegati | Sì | Sì | Sì | No | Sì |
| Il delegato o il responsabile può sospendere o riprendere la gestione | Sì | Sì | Sì | No | Sì |

## <a name="limitations"></a>Limitazioni

I responsabili possono aggiungere fino a 25 delegati e i delegati possono avere fino a 25 responsabili. Non esistono limiti al numero di relazioni di delega che è possibile creare in un tenant. 
 
Se il delegante e il delegato non si trovano nella stessa posizione geografica, il provider PSTN deve consentire che l'ID chiamante venga visualizzato da una posizione geografica diversa per una chiamata delegata. 

La configurazione della delega circolare non è consentita. Se anche gli utenti delegati dispongono di deleghe tra loro, potranno vedere solo la loro delega e non la delega iniziale.

## <a name="enable-delegation-and-shared-line-appearance"></a>Abilitare l'aspetto della delega e della riga condivisa

È possibile abilitare la delega usando l'impostazione **TeamsCallingPolicy AllowDelegation** . È possibile usare l'interfaccia di amministrazione di Teams o PowerShell di Teamms. 

Se abilitato, l'utente finale può configurare le relazioni di delega direttamente in Teams. 

> [!IMPORTANT]
> Quando si disattiva la delega per un utente, è necessario anche pulire le relazioni di delega per tale utente nell'interfaccia di amministrazione di Teams per evitare un routing delle chiamate errato.

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

Per configurare la delega e l'aspetto della riga condivisa tramite l'interfaccia di amministrazione di Teams, vedere [Configurare le impostazioni delle chiamate per gli utenti](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usare PowerShell

Per configurare l'aspetto della delega e della riga condivisa con Teams PowerShell, usare i cmdlet seguenti:

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>Esempi

Nell'esempio seguente user2@contoso.com viene aggiunto come delegato di user1@contoso.com con le autorizzazioni per effettuare e ricevere chiamate per conto dell'utente1 e per modificare le impostazioni per altri delegati:

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

Nel prossimo esempio, user2@contoso.com delegato non è più autorizzato a effettuare chiamate per conto dell'utente1:

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

Nell'esempio seguente user2@contoso.com viene rimosso come delegato di user1@contoso.com:

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>Altre informazioni

[Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Criteri per le chiamate di Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
