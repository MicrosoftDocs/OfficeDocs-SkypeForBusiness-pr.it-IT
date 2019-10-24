---
title: Gestire i criteri dei team in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri per i team dell'organizzazione per controllare gli utenti che possono eseguire in team e canali.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 5edaa21f3d9a2438532f8cc7f45f182c105b2f1e
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37570136"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gestire i criteri dei team in Microsoft Teams

Come amministratore, puoi usare i criteri di teams in Microsoft teams per controllare gli utenti che possono eseguire in team e canali. Ad esempio, puoi impostare se gli utenti possono scoprire team privati nei risultati della ricerca e nella raccolta team e se gli utenti possono creare canali privati.

Per gestire i criteri dei team, è possibile **passare a** > **criteri** teams teams nell'interfaccia di amministrazione di Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione otterranno automaticamente il criterio globale a meno che non si creino e non si assegnano criteri personalizzati.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente. Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.

## <a name="create-a-custom-teams-policy"></a>Creare un criterio teams personalizzato

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri di Teams](media/teams-policies.png)
4. Scegliere le impostazioni desiderate:

- [**Scoprire team privati**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): attivare questa impostazione per consentire agli utenti di individuare team privati nei risultati della ricerca e nella raccolta team.
- [**Creare canali privati**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): attivare questa impostazione per consentire agli utenti di creare canali privati.

5. Fai clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare un criterio Teams

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare un criterio team personalizzati agli utenti

È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

### <a name="assign-a-custom-teams-policy-to-a-user"></a>Assegnare un criterio teams personalizzato a un utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri Team**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.

Per assegnare un criterio teams personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).

In alternativa, è anche possibile eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Selezionare **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per ogni utente che si vuole aggiungere.
5. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Assegnare criteri Team personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio teams personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

In questo esempio viene assegnato un criterio teams denominato criteri marketing teams a tutti gli utenti nel gruppo marketing di contoso.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Ottenere i membri del gruppo specificato.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un determinato criterio teams. In questo esempio si tratta di criteri per i team di marketing.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'individuazione di team privati in teams](manage-discovery-of-private-teams.md)
