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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: ce387ec406a9ccfd6ee45a67f2613a45c219f21f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349700"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gestire i criteri dei team in Microsoft Teams

Come amministratore, puoi usare i criteri di teams in Microsoft teams per controllare gli utenti che possono eseguire in team e canali. Ad esempio, puoi impostare se gli utenti possono scoprire team privati nei risultati della ricerca e nella raccolta team e se gli utenti possono creare canali privati.

Per gestire i criteri dei team, è possibile **passare a**criteri teams teams nell'interfaccia di amministrazione di  >  **Teams policies** Microsoft teams. È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente. Dopo aver modificato il criterio globale o assegnato un criterio, è possibile che le modifiche abbiano effetto.

## <a name="create-a-custom-teams-policy"></a>Creare un criterio teams personalizzato

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri**teams teams.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri di Teams](media/teams-policies.png)
4. Scegliere le impostazioni desiderate:

- **Scoprire team privati**:<a name="discoverteams"> </a> attivare questa impostazione per consentire agli utenti di individuare team privati nei risultati della ricerca e nella raccolta team.
- **Creare canali privati**: <a name="createchannels"> </a>attivare questa impostazione per consentire agli utenti di creare canali privati.

5. Fare clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare un criterio Teams

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri**teams teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare un criterio team personalizzati agli utenti

È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

### <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare un criterio team personalizzati agli utenti

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri Team**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.

Per assegnare un criterio a più utenti alla volta:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi cerca gli utenti o filtra la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.  

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri**teams teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Assegnare criteri Team personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio teams personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

In questo esempio viene assegnato un criterio teams denominato criteri marketing teams a tutti gli utenti nel gruppo marketing di contoso.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Ottenere i membri del gruppo specificato.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un determinato criterio teams. In questo esempio si tratta di criteri per i team di marketing.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'individuazione di team privati in Teams](manage-discovery-of-private-teams.md)
- [Canali privati in teams](private-channels.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)
