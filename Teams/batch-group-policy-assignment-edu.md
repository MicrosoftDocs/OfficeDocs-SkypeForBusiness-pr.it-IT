---
title: Assegnare criteri a grandi set di utenti dell'istituto di istruzione
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come assegnare criteri a grandi set di utenti dell'istituto di istruzione in base all'appartenenza ai gruppi o direttamente tramite un'attività batch per scopi scolastici remoti (telescolastica, telescolastica).
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092904"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="c126c-103">Assegnare criteri a grandi set di utenti dell'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="c126c-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="c126c-104">Per informazioni più esaustivo sull'assegnazione di criteri in Microsoft Teams, vedere [Assegnare criteri](assign-policies.md)agli utenti in Teams .</span><span class="sxs-lookup"><span data-stu-id="c126c-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="c126c-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c126c-105">Overview</span></span>

<span data-ttu-id="c126c-106">È necessario concedere a studenti e docenti l'accesso a diverse funzionalità di Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="c126c-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="c126c-107">È possibile identificare rapidamente gli utenti dell'organizzazione in base al tipo di licenza e quindi assegnare loro i criteri appropriati.</span><span class="sxs-lookup"><span data-stu-id="c126c-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="c126c-108">Questa esercitazione illustra come assegnare criteri di riunione a grandi set di utenti dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c126c-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="c126c-109">È possibile assegnare criteri usando l'Microsoft Teams di amministrazione e PowerShell e verranno mostrati entrambi i modi.</span><span class="sxs-lookup"><span data-stu-id="c126c-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="c126c-110">È possibile assegnare criteri di riunione a un gruppo di sicurezza di cui gli utenti sono membri o direttamente agli utenti su vasta scala tramite un'assegnazione di criteri batch.</span><span class="sxs-lookup"><span data-stu-id="c126c-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="c126c-111">Imparerai a:</span><span class="sxs-lookup"><span data-stu-id="c126c-111">You'll learn how to:</span></span>

- <span data-ttu-id="c126c-112">**Usare [l'assegnazione dei criteri ai](#assign-a-policy-to-a-group) gruppi per assegnare un criterio riunione a un gruppo di sicurezza (scelta consigliata).**</span><span class="sxs-lookup"><span data-stu-id="c126c-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="c126c-113">Questo metodo consente di assegnare un criterio in base all'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="c126c-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="c126c-114">È possibile assegnare un criterio a un gruppo di sicurezza o a una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c126c-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="c126c-115">Quando i membri vengono aggiunti o rimossi dal gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="c126c-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="c126c-116">È consigliabile usare questo metodo perché riduce il tempo necessario per gestire i criteri per i nuovi utenti o quando cambiano i ruoli degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="c126c-117">Questo metodo è ideale per gruppi di un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="c126c-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="c126c-118">**Usare [l'assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare un criterio di riunione direttamente agli utenti in blocco.**</span><span class="sxs-lookup"><span data-stu-id="c126c-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="c126c-119">È possibile assegnare un criterio per un massimo di 5.000 utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="c126c-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="c126c-120">Se si hanno più di 5.000 utenti, è possibile inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="c126c-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="c126c-121">Con questo metodo, quando si hanno nuovi utenti, sarà necessario eseguire di nuovo l'assegnazione batch per assegnare i criteri a questi nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="c126c-122">Tenere presente che in Teams gli utenti ottengono automaticamente i criteri globali (impostazione predefinita a livello di organizzazione) per un tipo di criteri Teams a meno che non si creino e assegnino criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c126c-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="c126c-123">Poiché la popolazione degli studenti è spesso il set più grande di utenti e spesso ricevono le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c126c-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="c126c-124">Creare criteri personalizzati che consentano funzionalità di base come la chat privata e la pianificazione delle riunioni e assegnare i criteri al personale e ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="c126c-125">Assegnare i criteri personalizzati al personale e ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="c126c-126">Modificare e applicare il criterio Globale (impostazione predefinita a livello di organizzazione) per limitare le funzionalità per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="c126c-127">Tenere presente che i criteri globali verranno applicati a tutti gli utenti dell'istituto di istruzione finché non si crea un criterio personalizzato e lo si assegna al personale e ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="c126c-128">In questa esercitazione gli studenti riceveranno i criteri riunione globali e verrà assegnato un criterio di riunione personalizzato denominato EducatorMeetingPolicy a personale e docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="c126c-129">Si presuppone che siano stati modificati i criteri globali [](policy-packages-edu.md) per personalizzare le impostazioni delle riunioni per gli studenti e che siano stati creati criteri personalizzati che definiscono l'esperienza di riunione per personale e docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Screenshot della pagina Criteri riunione nell'interfaccia di amministrazione Teams riunione](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="c126c-131">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="c126c-131">Assign a policy to a group</span></span>

<span data-ttu-id="c126c-132">Seguire questa procedura per creare un gruppo di sicurezza per il personale e i docenti e quindi assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy a tale gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c126c-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="c126c-133">Nozioni preliminari</span><span class="sxs-lookup"><span data-stu-id="c126c-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c126c-134">Quando si assegna un criterio a un gruppo, l'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="c126c-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c126c-135">Ad esempio, se a un utente viene assegnato direttamente un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza su un criterio ereditato da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="c126c-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="c126c-136">Questo significa anche che se un utente ha un criterio di riunione a cui è stato assegnato direttamente, sarà necessario rimuovere i criteri riunione dall'utente prima di poter ereditare i criteri riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c126c-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="c126c-137">Prima di iniziare, è importante comprendere le regole di precedenza e la [classificazione](assign-policies.md#precedence-rules) [delle assegnazioni di gruppo.](assign-policies.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="c126c-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="c126c-138">Assicurarsi di leggere e comprendere i concetti descritti in Informazioni sull'assegnazione dei criteri **[ai gruppi.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**</span><span class="sxs-lookup"><span data-stu-id="c126c-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="c126c-139">È necessario completare tutti questi passaggi perché il personale e i docenti ereditino un criterio di riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c126c-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="c126c-140">[Creare gruppi di sicurezza](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="c126c-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="c126c-141">[Assegnare un criterio a un gruppo di sicurezza](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="c126c-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="c126c-142">[Rimuovere un criterio assegnato direttamente agli utenti](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="c126c-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="c126c-143">Creare gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c126c-143">Create security groups</span></span>

<span data-ttu-id="c126c-144">Prima di tutto, creare un gruppo di sicurezza per il personale e i docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="c126c-145">Con [School Data Sync](/SchoolDataSync/) (SDS), è possibile creare facilmente gruppi di sicurezza [per docenti e studenti](/SchoolDataSync/edu-security-groups) dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c126c-145">With [School Data Sync](/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="c126c-146">È consigliabile usare SDS per creare i gruppi di sicurezza necessari per gestire i criteri per l'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c126c-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="c126c-147">Se non è possibile distribuire SDS all'interno dell'ambiente, usare questo script di [PowerShell](scripts/powershell-script-security-groups-edu.md) per creare due gruppi di sicurezza, uno per tutti i membri del personale e i docenti a cui è assegnata una licenza per istituti di istruzione e un altro per tutti gli studenti a cui è assegnata una licenza per studenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="c126c-148">È necessario eseguire regolarmente questo script per mantenere i gruppi aggiornati e aggiornati.</span><span class="sxs-lookup"><span data-stu-id="c126c-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="c126c-149">Assegnare un criterio a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c126c-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c126c-150">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c126c-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="c126c-151">Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri di chiamata Teams, per i criteri di parcheggio di chiamata Teams, per i criteri di Teams, per gli eventi live Teams, per i criteri per le riunioni Teams e per i criteri di messaggistica Teams.</span><span class="sxs-lookup"><span data-stu-id="c126c-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="c126c-152">Per altri tipi di criteri, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c126c-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="c126c-153">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="c126c-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c126c-154">Selezionare la scheda **Assegnazione criteri di** gruppo.</span><span class="sxs-lookup"><span data-stu-id="c126c-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="c126c-155">Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna criteri a **gruppo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c126c-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Screenshot del riquadro Modifica impostazioni con i criteri riunione](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="c126c-157">Nella casella **Selezionare un gruppo** cercare e aggiungere il gruppo di sicurezza che contiene il personale e i docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="c126c-158">Nella casella **Seleziona rango** immettere **1**.</span><span class="sxs-lookup"><span data-stu-id="c126c-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="c126c-159">Nella casella **Selezionare un criterio** selezionare **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="c126c-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="c126c-160">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="c126c-160">Select **Apply**.</span></span>

<span data-ttu-id="c126c-161">Per rimuovere un'assegnazione di  Criteri di gruppo, nella scheda Assegnazione criteri di gruppo della pagina dei criteri selezionare l'assegnazione di gruppo e quindi **scegliere Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="c126c-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="c126c-162">Per modificare la classificazione di un'assegnazione di gruppo, è necessario prima rimuovere l'assegnazione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c126c-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="c126c-163">Seguire quindi i passaggi precedenti per assegnare il criterio a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="c126c-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="c126c-164">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="c126c-165">Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti i Teams di criteri.</span><span class="sxs-lookup"><span data-stu-id="c126c-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="c126c-166">Vedere [New-CsGroupPolicyAssignment per](/powershell/module/teams/new-csgrouppolicyassignment) l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="c126c-166">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c126c-167">Installare e connettersi al modulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c126c-168">Eseguire le operazioni seguenti per installare [il Teams di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="c126c-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="c126c-169">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c126c-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c126c-170">Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="c126c-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c126c-171">Quando richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c126c-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="c126c-172">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="c126c-172">Assign a policy to a group</span></span>

<span data-ttu-id="c126c-173">Eseguire le operazioni seguenti per assegnare il criterio di riunione denominato EducatorMeetingPolicy al gruppo di sicurezza che contiene il personale e i docenti e impostare la classificazione delle assegnazioni su 1.</span><span class="sxs-lookup"><span data-stu-id="c126c-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="c126c-174">È possibile specificare un gruppo di sicurezza usando l'ID oggetto, l'indirizzo SIP (Session Initiation Protocol) o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c126c-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="c126c-175">In questo esempio viene utilizzato un indirizzo di posta elettronica (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c126c-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="c126c-176">Rimuovere un criterio assegnato direttamente agli utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="c126c-177">Tenere presente che se a un utente è stato assegnato direttamente un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="c126c-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="c126c-178">Questo significa che se un utente ha un criterio di riunione a cui è stato assegnato direttamente, sarà necessario rimuovere i criteri riunione dall'utente prima di poter ereditare i criteri riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c126c-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="c126c-179">Per altre informazioni, vedere [Informazioni necessarie sull'assegnazione dei criteri ai gruppi.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)</span><span class="sxs-lookup"><span data-stu-id="c126c-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="c126c-180">Seguire questa procedura per rimuovere i criteri riunione assegnati direttamente al personale e ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c126c-181">Installare e connettersi al modulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c126c-182">Eseguire le operazioni seguenti per installare [il Teams di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="c126c-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="c126c-183">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c126c-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c126c-184">Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="c126c-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c126c-185">Quando viene richiesto, accedere usando le stesse credenziali di amministratore usate per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c126c-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="c126c-186">Annullare l'assegnazione di un criterio assegnato direttamente agli utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="c126c-187">Eseguire le operazioni seguenti per rimuovere un criterio di riunione dagli utenti a cui è stato assegnato direttamente il criterio.</span><span class="sxs-lookup"><span data-stu-id="c126c-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="c126c-188">È possibile specificare gli utenti in base all'indirizzo di posta elettronica o all'ID oggetto.</span><span class="sxs-lookup"><span data-stu-id="c126c-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="c126c-189">In questo esempio i criteri riunione vengono rimossi dagli utenti specificati dal loro indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c126c-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="c126c-190">In questo esempio i criteri riunione vengono rimossi dall'elenco degli utenti in un file di testo denominato user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="c126c-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="c126c-191">Ottenere le assegnazioni dei criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="c126c-191">Get policy assignments for a group</span></span>

<span data-ttu-id="c126c-192">Eseguire le operazioni seguenti per visualizzare tutti i criteri assegnati a un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="c126c-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="c126c-193">Si noti che i gruppi sono sempre elencati in base all'ID gruppo, anche se per assegnare il criterio è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c126c-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="c126c-194">Ottenere i criteri assegnati a un utente</span><span class="sxs-lookup"><span data-stu-id="c126c-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="c126c-195">Eseguire le operazioni seguenti per visualizzare tutti i criteri assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="c126c-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="c126c-196">L'esempio seguente mostra come ottenere i criteri assegnati a reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c126c-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="c126c-197">Assegnare un criterio a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="c126c-198">Seguire questa procedura per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy direttamente al personale e ai docenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="c126c-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c126c-199">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="c126c-200">Connessione al modulo di PowerShell di Azure AD per Graph e al modulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="c126c-201">Prima di eseguire i passaggi descritti in questo articolo, è necessario installare e connettersi al modulo di PowerShell di Azure AD per Graph (per identificare gli utenti in base alle licenze assegnate) e al modulo di PowerShell di Microsoft Teams (per assegnare i criteri a tali utenti).</span><span class="sxs-lookup"><span data-stu-id="c126c-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="c126c-202">Installare e connettersi al modulo powershell di Azure AD Graph</span><span class="sxs-lookup"><span data-stu-id="c126c-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="c126c-203">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire quanto segue per installare Azure Active Directory PowerShell per Graph modulo.</span><span class="sxs-lookup"><span data-stu-id="c126c-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="c126c-204">Eseguire le operazioni seguenti per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c126c-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="c126c-205">Quando richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c126c-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="c126c-206">Per altre informazioni, vedere [Connessione con il Azure Active Directory PowerShell per Graph modulo](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="c126c-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c126c-207">Installare e connettersi al modulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c126c-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c126c-208">Eseguire le operazioni seguenti per installare [il Teams di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="c126c-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="c126c-209">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c126c-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c126c-210">Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="c126c-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c126c-211">Quando viene richiesto, accedere usando le stesse credenziali di amministratore usate per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c126c-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="c126c-212">Identificare gli utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-212">Identify your users</span></span>

<span data-ttu-id="c126c-213">Eseguire prima di tutto quanto segue per identificare il personale e i docenti in base al tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="c126c-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="c126c-214">Questo indica quali SKU sono in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c126c-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="c126c-215">È quindi possibile identificare personale e docenti a cui è assegnato uno SKU per istituti di docente.</span><span class="sxs-lookup"><span data-stu-id="c126c-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="c126c-216">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="c126c-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="c126c-217">In questo esempio l'output mostra che lo SkuId della licenza docenti è "e97c048c-37a4-45fb-ab50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="c126c-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="c126c-218">Per visualizzare un elenco di SKU Education e ID SKU, vedere Informazioni di riferimento [su SKU education.](sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="c126c-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="c126c-219">Quindi, eseguiamo quanto segue per identificare gli utenti che hanno questa licenza e raccoglierli tutti insieme.</span><span class="sxs-lookup"><span data-stu-id="c126c-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="c126c-220">Assegnare un criterio in blocco</span><span class="sxs-lookup"><span data-stu-id="c126c-220">Assign a policy in bulk</span></span>

<span data-ttu-id="c126c-221">Ora assegniamo i criteri appropriati agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="c126c-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="c126c-222">Il numero massimo di utenti per cui è possibile assegnare o aggiornare criteri è 5.000 alla volta.</span><span class="sxs-lookup"><span data-stu-id="c126c-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="c126c-223">Ad esempio, se si hanno più di 5.000 personale e docenti, sarà necessario inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="c126c-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="c126c-224">Eseguire le operazioni seguenti per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="c126c-225">Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare al criterio che si sta assegnando e ```PolicyType``` ```PolicyName``` al nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="c126c-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="c126c-226">Ottenere lo stato di un'assegnazione in blocco</span><span class="sxs-lookup"><span data-stu-id="c126c-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="c126c-227">Ogni assegnazione in blocco restituisce un ID operazione, che è possibile usare per tenere traccia dello stato di avanzamento delle assegnazioni dei criteri o identificare eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="c126c-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="c126c-228">Ad esempio, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c126c-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="c126c-229">Per visualizzare lo stato dell'assegnazione di ogni utente nell'operazione batch, eseguire quanto segue.</span><span class="sxs-lookup"><span data-stu-id="c126c-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="c126c-230">I dettagli di ogni utente sono nella ```UserState``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="c126c-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="c126c-231">Assegnare un criterio in blocco se si hanno più di 5.000 utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="c126c-232">Eseguire prima di tutto quanto segue per verificare il numero di personale e docenti disponibili:</span><span class="sxs-lookup"><span data-stu-id="c126c-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="c126c-233">Invece di fornire l'intero elenco di ID utente, eseguire quanto segue per specificare i primi 5.000 e quindi i successivi 5.000 e così via.</span><span class="sxs-lookup"><span data-stu-id="c126c-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="c126c-234">È possibile modificare l'intervallo di ID utente finché non si raggiunge l'elenco completo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c126c-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="c126c-235">Ad esempio, immettere ```$faculty[0..4999``` per il primo batch, usare per il ```$faculty[5000..9999``` secondo batch, immettere per il terzo batch ```$faculty[10000..14999``` e così via.</span><span class="sxs-lookup"><span data-stu-id="c126c-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="c126c-236">Ottenere i criteri assegnati a un utente</span><span class="sxs-lookup"><span data-stu-id="c126c-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="c126c-237">Eseguire le operazioni seguenti per visualizzare tutti i criteri assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="c126c-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="c126c-238">L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c126c-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="c126c-239">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c126c-239">FAQ</span></span>

<span data-ttu-id="c126c-240">**Non ho familiarità con PowerShell per Teams. Dove si possono trovare altre informazioni?**</span><span class="sxs-lookup"><span data-stu-id="c126c-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="c126c-241">Per una panoramica dell'uso di PowerShell per gestire Teams, vedere panoramica Teams [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c126c-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="c126c-242">Per altre informazioni sui cmdlet usati in questo articolo, vedere:</span><span class="sxs-lookup"><span data-stu-id="c126c-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="c126c-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="c126c-243">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="c126c-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="c126c-244">Get-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="c126c-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="c126c-245">New-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="c126c-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="c126c-246">Get-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="c126c-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="c126c-247">Get-CsUserPolicyAssignment</span></span>](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="c126c-248">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c126c-248">Related topics</span></span>

- [<span data-ttu-id="c126c-249">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="c126c-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="c126c-250">Criteri e pacchetti di criteri di Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="c126c-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="c126c-251">Gestire i criteri di riunione in Teams</span><span class="sxs-lookup"><span data-stu-id="c126c-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)