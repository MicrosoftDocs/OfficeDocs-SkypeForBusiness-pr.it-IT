---
title: Gestire i criteri di feedback in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: Informazioni su come usare i criteri di feedback per controllare se Teams utenti dell'organizzazione possono inviare feedback sulle Teams a Microsoft.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656722"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="a518b-103">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a518b-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="a518b-104">Gli utenti dell'organizzazione possono inviare feedback sulle Teams a Microsoft per farci sapere come stiamo facendo, direttamente dall'interno Teams desktop e client Web.</span><span class="sxs-lookup"><span data-stu-id="a518b-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="a518b-105">Stiamo continuamente migliorando l'esperienza Teams e usiamo questo feedback per migliorare Teams migliore.</span><span class="sxs-lookup"><span data-stu-id="a518b-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="a518b-106">I criteri di feedback non sono disponibili nelle distribuzioni GCC, GCC high o DOD.</span><span class="sxs-lookup"><span data-stu-id="a518b-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="a518b-107">**Caratteristica Invia feedback**</span><span class="sxs-lookup"><span data-stu-id="a518b-107">**The Give feedback feature**</span></span>

<span data-ttu-id="a518b-108">Gli utenti possono inviare commenti e suggerimenti su Teams inviandoci un  >  **feedback** in Teams.</span><span class="sxs-lookup"><span data-stu-id="a518b-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="a518b-109">I dati inviati tramite Invia **feedback** sono considerati "Dati di supporto" ai sensi del contratto di Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "Dati dei clienti" o "Dati personali".</span><span class="sxs-lookup"><span data-stu-id="a518b-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Screenshot dell'opzione Invia feedback in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="a518b-111">**Sondaggi**</span><span class="sxs-lookup"><span data-stu-id="a518b-111">**Surveys**</span></span>

<span data-ttu-id="a518b-112">Gli utenti possono anche valutare la loro esperienza con Teams e inviarci dettagli sulla valutazione che danno.</span><span class="sxs-lookup"><span data-stu-id="a518b-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="a518b-113">Questo sondaggio popup viene visualizzato per gli utenti di tanto in tanto in Teams.</span><span class="sxs-lookup"><span data-stu-id="a518b-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="a518b-114">Quando un utente seleziona **Invia feedback** nella notifica, il sondaggio viene visualizzato per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a518b-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![notifica e modulo del sondaggio in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="a518b-116">Specificare se gli utenti possono inviare commenti e suggerimenti Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a518b-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="a518b-117">Gli amministratori possono controllare se gli utenti dell'organizzazione possono inviare feedback su Teams a Microsoft tramite Inviare **feedback** e se ricevono il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="a518b-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="a518b-118">Per impostazione predefinita, a tutti gli utenti dell'organizzazione viene assegnato automaticamente il criterio globale (impostazione predefinita a livello di organizzazione) e la caratteristica Invia **feedback** e il sondaggio sono abilitati nel criterio.</span><span class="sxs-lookup"><span data-stu-id="a518b-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="a518b-119">L'eccezione è Teams per l'istruzione, in cui le funzionalità sono abilitate per i docenti e disabilitate per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="a518b-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="a518b-120">È possibile modificare i criteri globali o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a518b-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="a518b-121">Dopo aver modificato i criteri globali o aver assegnato un criterio personalizzato, l'applicazione delle modifiche può richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="a518b-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="a518b-122">Si supponga, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite Invia **feedback** e ricevere sondaggi ad eccezione dei nuovi assunti nella formazione.</span><span class="sxs-lookup"><span data-stu-id="a518b-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="a518b-123">In questo scenario si crea un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti.</span><span class="sxs-lookup"><span data-stu-id="a518b-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="a518b-124">Tutti gli altri utenti dell'organizzazione ottengono i criteri globali con le funzionalità attivate.</span><span class="sxs-lookup"><span data-stu-id="a518b-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="a518b-125">Per gestire i criteri di feedback, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a518b-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="a518b-126">Usare il cmdlet **New-CsTeamsFeedbackPolicy,** disponibile *qui, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* per creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a518b-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="a518b-127">Usare il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a518b-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="a518b-128">Usare **Set-CsTeamsFeedbackPolicy** per impostare flag specifici.</span><span class="sxs-lookup"><span data-stu-id="a518b-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="a518b-129">Per disattivare e attivare le funzionalità, impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a518b-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="a518b-130">**Inviare feedback:** impostare il **parametro userInitiatedMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di inviare feedback.</span><span class="sxs-lookup"><span data-stu-id="a518b-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="a518b-131">Se si imposta il **parametro su disabled,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="a518b-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="a518b-132">**Sondaggi:** impostare il **parametro receiveSurveysMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di ricevere il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="a518b-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="a518b-133">Per fare in modo che gli utenti ricevano il sondaggio e consentano loro di rifiutare esplicitamente, impostare il parametro **su enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="a518b-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="a518b-134">In Teams, gli utenti possono quindi passare a Impostazioni Privacy e scegliere se partecipare  >   ai sondaggi.</span><span class="sxs-lookup"><span data-stu-id="a518b-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="a518b-135">Se si imposta il **parametro su disabled,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non riceveranno il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="a518b-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="a518b-136">**Posta** elettronica: usare il flag **AllowEmailCollection** per aggiungere un campo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a518b-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="a518b-137">Creare criteri di feedback personalizzati</span><span class="sxs-lookup"><span data-stu-id="a518b-137">Create a custom feedback policy</span></span>

<span data-ttu-id="a518b-138">In questo esempio viene creato un criterio di feedback denominato Criteri di feedback per i nuovi assunti e viene disattivata la possibilità di inviare feedback tramite Invia **feedback** e il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="a518b-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="a518b-139">Assegnare criteri di feedback personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="a518b-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="a518b-140">In questo esempio viene assegnato un criterio personalizzato denominato Criteri di feedback per i nuovi assunti a un utente denominato utente1.</span><span class="sxs-lookup"><span data-stu-id="a518b-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="a518b-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a518b-141">Related topics</span></span>

- [<span data-ttu-id="a518b-142">Teams Panoramica di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a518b-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a518b-143">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="a518b-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
