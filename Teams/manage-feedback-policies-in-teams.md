---
title: Gestire i criteri di feedback in Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804696"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="43871-103">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43871-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="43871-104">Gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft per farci sapere come procedere, direttamente dall'interno dei client desktop e Web teams.</span><span class="sxs-lookup"><span data-stu-id="43871-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="43871-105">Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.</span><span class="sxs-lookup"><span data-stu-id="43871-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="43871-106">I criteri di feedback non sono disponibili nelle distribuzioni GCC, GCC High o DOD.</span><span class="sxs-lookup"><span data-stu-id="43871-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="43871-107">**Funzionalità Invia feedback**</span><span class="sxs-lookup"><span data-stu-id="43871-107">**The Give feedback feature**</span></span>

<span data-ttu-id="43871-108">Gli utenti possono inviare commenti e suggerimenti su teams per **aiutarci** a  >  **fornire feedback** in teams.</span><span class="sxs-lookup"><span data-stu-id="43871-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="43871-109">I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".</span><span class="sxs-lookup"><span data-stu-id="43871-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="43871-111">**Sondaggi**</span><span class="sxs-lookup"><span data-stu-id="43871-111">**Surveys**</span></span>

<span data-ttu-id="43871-112">Gli utenti possono anche valutare la propria esperienza con i team e inviarci i dettagli relativi alla valutazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="43871-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="43871-113">Questo sondaggio popup viene visualizzato agli utenti di tanto in tanto in teams.</span><span class="sxs-lookup"><span data-stu-id="43871-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="43871-114">Quando un utente fa clic su **Fornisci un feedback** nella notifica, il sondaggio viene visualizzato per il completamento.</span><span class="sxs-lookup"><span data-stu-id="43871-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Screenshot della notifica e del modulo del sondaggio in teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="43871-116">Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="43871-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="43871-117">Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft tramite **feedback** e se ricevono il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="43871-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="43871-118">Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita) e la funzionalità **Invia feedback** e il sondaggio sono abilitati nel criterio.</span><span class="sxs-lookup"><span data-stu-id="43871-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="43871-119">L'eccezione è teams for Education, in cui le funzionalità sono abilitate per insegnanti e disabili per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="43871-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="43871-120">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="43871-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="43871-121">Dopo aver modificato il criterio globale o assegnato un criterio personalizzato, è possibile che le modifiche apportate vengano applicate in poche ore.</span><span class="sxs-lookup"><span data-stu-id="43871-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="43871-122">Supponiamo, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite **feedback** e ricevere sondaggi, ad eccezione dei nuovi assunti in formazione.</span><span class="sxs-lookup"><span data-stu-id="43871-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="43871-123">In questo scenario creerai un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti.</span><span class="sxs-lookup"><span data-stu-id="43871-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="43871-124">Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con le funzionalità attivate.</span><span class="sxs-lookup"><span data-stu-id="43871-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="43871-125">Puoi gestire i criteri di feedback usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43871-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="43871-126">Usa il cmdlet **New-CsTeamsFeedbackPolicy** , *che può essere [trovato qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43871-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="43871-127">Per disattivare e attivare le caratteristiche, impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="43871-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="43871-128">**Invia feedback**: imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="43871-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="43871-129">Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="43871-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="43871-130">**Sondaggi**: imposta il parametro **receiveSurveysMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di ricevere il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="43871-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="43871-131">Per consentire agli utenti di ricevere il sondaggio e consentirne l'opt-out, imposta il parametro su **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="43871-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="43871-132">In teams gli utenti possono quindi accedere alla privacy **delle impostazioni**  >   e scegliere se partecipare ai sondaggi.</span><span class="sxs-lookup"><span data-stu-id="43871-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="43871-133">Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non riceveranno il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="43871-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="43871-134">Creare criteri di feedback personalizzati</span><span class="sxs-lookup"><span data-stu-id="43871-134">Create a custom feedback policy</span></span>

<span data-ttu-id="43871-135">In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire feedback tramite **feedback** e il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="43871-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="43871-136">Assegnare criteri di feedback personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="43871-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="43871-137">In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.</span><span class="sxs-lookup"><span data-stu-id="43871-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="43871-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="43871-138">Related topics</span></span>

- [<span data-ttu-id="43871-139">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="43871-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="43871-140">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="43871-140">Assign policies to your users in Teams</span></span>](assign-policies.md)