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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i criteri di feedback per controllare se gli utenti dei team dell'organizzazione possono inviare commenti e suggerimenti sui team a Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184681"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="b1d47-103">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1d47-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b1d47-104">Gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft per **contribuire** > a**fornire feedback** nei client teams.</span><span class="sxs-lookup"><span data-stu-id="b1d47-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="b1d47-105">Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.</span><span class="sxs-lookup"><span data-stu-id="b1d47-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="b1d47-107">I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto di Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".</span><span class="sxs-lookup"><span data-stu-id="b1d47-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="b1d47-108">Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1d47-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="b1d47-109">Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1d47-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="b1d47-110">Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita a livello globale) e la funzionalità è abilitata nel criterio.</span><span class="sxs-lookup"><span data-stu-id="b1d47-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="b1d47-111">L'eccezione è teams for Education, in cui la funzionalità è abilitata per insegnanti e disabili per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="b1d47-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="b1d47-112">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b1d47-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="b1d47-113">Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="b1d47-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="b1d47-114">Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="b1d47-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="b1d47-115">Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="b1d47-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="b1d47-116">Supponiamo, ad esempio, di consentire a tutti gli utenti dell'organizzazione di inviare commenti e suggerimenti ad eccezione dei nuovi assunti in formazione.</span><span class="sxs-lookup"><span data-stu-id="b1d47-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="b1d47-117">In questo scenario creerai un criterio personalizzato per disattivare la caratteristica e assegnarla ai nuovi assunti.</span><span class="sxs-lookup"><span data-stu-id="b1d47-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="b1d47-118">Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con la funzionalità attivata.</span><span class="sxs-lookup"><span data-stu-id="b1d47-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="b1d47-119">Puoi usare il cmdlet **New-CsTeamsFeedbackPolicy** per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b1d47-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="b1d47-120">Imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="b1d47-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="b1d47-121">Impostando il parametro \*\*\*\* su Disabled si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="b1d47-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="b1d47-122">Creare criteri di feedback personalizzati</span><span class="sxs-lookup"><span data-stu-id="b1d47-122">Create a custom feedback policy</span></span>

<span data-ttu-id="b1d47-123">In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="b1d47-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="b1d47-124">Assegnare un criterio di feedback personalizzato</span><span class="sxs-lookup"><span data-stu-id="b1d47-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="b1d47-125">Assegnare un criterio di feedback personalizzato a un utente</span><span class="sxs-lookup"><span data-stu-id="b1d47-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="b1d47-126">In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.</span><span class="sxs-lookup"><span data-stu-id="b1d47-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="b1d47-127">Assegnare criteri di feedback personalizzati agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="b1d47-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="b1d47-128">È consigliabile assegnare un criterio di feedback personalizzato a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="b1d47-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="b1d47-129">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b1d47-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="b1d47-130">In questo esempio, assegniamo i criteri di feedback personalizzati denominati nuovi criteri di feedback di noleggio a tutti gli utenti nel gruppo nuove assunzioni Contoso.</span><span class="sxs-lookup"><span data-stu-id="b1d47-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="b1d47-131">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="b1d47-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="b1d47-132">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="b1d47-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b1d47-133">Assegnare tutti gli utenti del gruppo a un particolare criterio di feedback.</span><span class="sxs-lookup"><span data-stu-id="b1d47-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="b1d47-134">In questo esempio si tratta di nuovi criteri di feedback sulle assunzioni.</span><span class="sxs-lookup"><span data-stu-id="b1d47-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="b1d47-135">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b1d47-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1d47-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b1d47-136">Related topics</span></span>

- [<span data-ttu-id="b1d47-137">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="b1d47-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)