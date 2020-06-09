---
title: Gestire i criteri di feedback in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i criteri di feedback per controllare se gli utenti dei team dell'organizzazione possono inviare commenti e suggerimenti sui team a Microsoft.
ms.openlocfilehash: 22e254cb2db6dc63e01c9c8ef5628fb97cfa0e16
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637955"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="d7810-103">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7810-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="d7810-104">Gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft per farci sapere come procedere, direttamente dall'interno dei client desktop e Web teams.</span><span class="sxs-lookup"><span data-stu-id="d7810-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="d7810-105">Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.</span><span class="sxs-lookup"><span data-stu-id="d7810-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="d7810-106">**Funzionalità Invia feedback**</span><span class="sxs-lookup"><span data-stu-id="d7810-106">**The Give feedback feature**</span></span>

<span data-ttu-id="d7810-107">Gli utenti possono inviare commenti e suggerimenti su teams per **aiutarci**a  >  **fornire feedback** in teams.</span><span class="sxs-lookup"><span data-stu-id="d7810-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="d7810-108">I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".</span><span class="sxs-lookup"><span data-stu-id="d7810-108">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="d7810-110">**Sondaggi**</span><span class="sxs-lookup"><span data-stu-id="d7810-110">**Surveys**</span></span>

<span data-ttu-id="d7810-111">Gli utenti possono anche valutare la propria esperienza con i team e inviarci i dettagli relativi alla valutazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="d7810-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="d7810-112">Questo sondaggio popup viene visualizzato agli utenti di tanto in tanto in teams.</span><span class="sxs-lookup"><span data-stu-id="d7810-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="d7810-113">Quando un utente fa clic su **Fornisci un feedback** nella notifica, il sondaggio viene visualizzato per il completamento.</span><span class="sxs-lookup"><span data-stu-id="d7810-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Screenshot della notifica e del modulo del sondaggio in teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="d7810-115">Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d7810-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="d7810-116">Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft tramite **feedback** e se ricevono il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d7810-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="d7810-117">Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita) e la funzionalità **Invia feedback** e il sondaggio sono abilitati nel criterio.</span><span class="sxs-lookup"><span data-stu-id="d7810-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="d7810-118">L'eccezione è teams for Education, in cui le funzionalità sono abilitate per insegnanti e disabili per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="d7810-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="d7810-119">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d7810-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="d7810-120">Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="d7810-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="d7810-121">Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="d7810-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="d7810-122">Dopo aver modificato il criterio globale o assegnato un criterio, è possibile che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="d7810-122">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="d7810-123">Supponiamo, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite **feedback** e ricevere sondaggi, ad eccezione dei nuovi assunti in formazione.</span><span class="sxs-lookup"><span data-stu-id="d7810-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="d7810-124">In questo scenario creerai un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti.</span><span class="sxs-lookup"><span data-stu-id="d7810-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="d7810-125">Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con le funzionalità attivate.</span><span class="sxs-lookup"><span data-stu-id="d7810-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="d7810-126">Si usa il cmdlet **New-CsTeamsFeedbackPolicy** , *che può essere [trovato qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d7810-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="d7810-127">Per disattivare e attivare le caratteristiche, impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7810-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="d7810-128">**Invia feedback**: imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="d7810-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="d7810-129">Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="d7810-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="d7810-130">**Sondaggi**: imposta il parametro **receiveSurveysMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di ricevere il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d7810-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="d7810-131">Per consentire agli utenti di ricevere il sondaggio e consentirne l'opt-out, imposta il parametro su **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="d7810-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="d7810-132">In teams gli utenti possono quindi accedere alla privacy **delle impostazioni**  >  **Privacy** e scegliere se partecipare ai sondaggi.</span><span class="sxs-lookup"><span data-stu-id="d7810-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="d7810-133">Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non riceveranno il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d7810-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="d7810-134">Creare criteri di feedback personalizzati</span><span class="sxs-lookup"><span data-stu-id="d7810-134">Create a custom feedback policy</span></span>

<span data-ttu-id="d7810-135">In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire feedback tramite **feedback** e il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d7810-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="d7810-136">Assegnare un criterio di feedback personalizzato</span><span class="sxs-lookup"><span data-stu-id="d7810-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="d7810-137">Assegnare un criterio di feedback personalizzato a un utente</span><span class="sxs-lookup"><span data-stu-id="d7810-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="d7810-138">In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.</span><span class="sxs-lookup"><span data-stu-id="d7810-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="d7810-139">Assegnare criteri di feedback personalizzati agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="d7810-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="d7810-140">È consigliabile assegnare un criterio di feedback personalizzato a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="d7810-140">You may want to assign a custom feedback policy to multiple users that you've already identified.</span></span> <span data-ttu-id="d7810-141">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7810-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="d7810-142">In questo esempio, assegniamo i criteri di feedback personalizzati denominati nuovi criteri di feedback di noleggio a tutti gli utenti nel gruppo nuove assunzioni Contoso.</span><span class="sxs-lookup"><span data-stu-id="d7810-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="d7810-143">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="d7810-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="d7810-144">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="d7810-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d7810-145">Assegnare tutti gli utenti del gruppo a un particolare criterio di feedback.</span><span class="sxs-lookup"><span data-stu-id="d7810-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="d7810-146">In questo esempio si tratta di nuovi criteri di feedback sulle assunzioni.</span><span class="sxs-lookup"><span data-stu-id="d7810-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="d7810-147">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d7810-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d7810-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d7810-148">Related topics</span></span>

- [<span data-ttu-id="d7810-149">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="d7810-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
