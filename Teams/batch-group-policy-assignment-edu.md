---
title: Assegnare criteri a grandi gruppi di utenti nella tua scuola
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come assegnare criteri a grandi insiemi di utenti nell'Istituto di istruzione in base all'appartenenza al gruppo o direttamente tramite un'assegnazione batch per scopi scolastici remoti (Teleschool, tele-School).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534102"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="269d7-103">Assegnare criteri a grandi gruppi di utenti nella tua scuola</span><span class="sxs-lookup"><span data-stu-id="269d7-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="269d7-104">Per una storia più ampia sull'assegnazione di criteri in Microsoft teams, vedere [assegnare criteri agli utenti in teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="269d7-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="269d7-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="269d7-105">Overview</span></span>

<span data-ttu-id="269d7-106">È necessario offrire agli studenti e agli insegnanti l'accesso a funzionalità diverse in Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="269d7-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="269d7-107">È possibile identificare rapidamente gli utenti dell'organizzazione per tipo di licenza e quindi assegnare il criterio appropriato.</span><span class="sxs-lookup"><span data-stu-id="269d7-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="269d7-108">In questa esercitazione viene illustrato come assegnare un criterio di riunione a set di utenti di grandi dimensioni nell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="269d7-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="269d7-109">Puoi assegnare criteri usando l'interfaccia di amministrazione di Microsoft teams e PowerShell e ti mostreremo entrambi i modi.</span><span class="sxs-lookup"><span data-stu-id="269d7-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="269d7-110">È possibile assegnare un criterio di riunione a un gruppo di sicurezza che gli utenti sono membri o direttamente agli utenti in scala tramite un'assegnazione di criteri batch.</span><span class="sxs-lookup"><span data-stu-id="269d7-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="269d7-111">Imparerai a:</span><span class="sxs-lookup"><span data-stu-id="269d7-111">You'll learn how to:</span></span>

- <span data-ttu-id="269d7-112">**Usare l' [assegnazione dei criteri per i gruppi](#assign-a-policy-to-a-group) per assegnare un criterio di riunione a un gruppo di sicurezza (scelta consigliata)**.</span><span class="sxs-lookup"><span data-stu-id="269d7-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="269d7-113">Questo metodo consente di assegnare un criterio in base all'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="269d7-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="269d7-114">È possibile assegnare un criterio a un gruppo di sicurezza o a una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="269d7-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="269d7-115">Quando i membri vengono aggiunti o rimossi dal gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="269d7-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="269d7-116">Ti consigliamo di usare questo metodo perché riduce il tempo necessario per gestire i criteri per i nuovi utenti o quando cambiano i ruoli degli utenti.</span><span class="sxs-lookup"><span data-stu-id="269d7-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="269d7-117">Questo metodo funziona meglio per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="269d7-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="269d7-118">**Usare l' [assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare un criterio di riunione direttamente agli utenti in blocco**.</span><span class="sxs-lookup"><span data-stu-id="269d7-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="269d7-119">È possibile assegnare un criterio per un massimo di 5.000 utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="269d7-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="269d7-120">Se si hanno più di 5.000 utenti, è possibile inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="269d7-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="269d7-121">Con questo metodo, quando si hanno nuovi utenti, è necessario eseguire di nuovo l'assegnazione batch per assegnare i criteri a tali nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="269d7-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="269d7-122">Tenere presente che in teams gli utenti ottengono automaticamente il criterio globale (org-Wide default) per un tipo di criteri teams, a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="269d7-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="269d7-123">Poiché la popolazione studente è spesso il più grande insieme di utenti e spesso riceve le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="269d7-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="269d7-124">Creare criteri personalizzati che consentano funzionalità di base, ad esempio la chat privata e la pianificazione delle riunioni, e assegnare i criteri al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="269d7-125">Assegnare i criteri personalizzati al personale e agli educatori.</span><span class="sxs-lookup"><span data-stu-id="269d7-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="269d7-126">Modificare e applicare il criterio globale (predefinito a livello di organizzazione) per limitare le funzionalità per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="269d7-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="269d7-127">Tieni presente che il criterio globale verrà applicato a tutti gli utenti dell'Istituto di istruzione fino a quando non creerai un criterio personalizzato e lo assegnerò al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="269d7-128">In questa esercitazione gli studenti otterranno i criteri globali per le riunioni e assegnerò un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="269d7-129">Supponiamo che tu abbia modificato il criterio globale per adattare le impostazioni delle riunioni per gli studenti e [creato un criterio personalizzato](policy-packages-edu.md) che definisce l'esperienza di riunione per il personale e gli educatori.</span><span class="sxs-lookup"><span data-stu-id="269d7-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Screenshot della pagina criteri riunione nell'interfaccia di amministrazione di Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="269d7-131">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="269d7-131">Assign a policy to a group</span></span>

<span data-ttu-id="269d7-132">Seguire questa procedura per creare un gruppo di sicurezza per il personale e gli educatori e quindi assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="269d7-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="269d7-133">Nozioni preliminari</span><span class="sxs-lookup"><span data-stu-id="269d7-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="269d7-134">Quando si assegna un criterio a un gruppo, l'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="269d7-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="269d7-135">Ad esempio, se un utente ha direttamente assegnato un criterio (individualmente o tramite un'assegnazione batch), tale criterio ha la precedenza su un criterio ereditato da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="269d7-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="269d7-136">Ciò significa anche che, se un utente ha un criterio di riunione direttamente assegnato a tali criteri, sarà necessario rimuovere i criteri della riunione dall'utente prima che possano ereditare i criteri di una riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="269d7-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="269d7-137">Prima di iniziare, è importante comprendere [le regole di precedenza](assign-policies.md#precedence-rules) e la [classificazione delle assegnazioni di gruppo](assign-policies.md#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="269d7-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="269d7-138">Verificare di **aver letto e compreso i concetti che [occorre sapere sull'assegnazione dei criteri ai gruppi](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span><span class="sxs-lookup"><span data-stu-id="269d7-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="269d7-139">È necessario completare tutti questi passaggi per il personale e gli educatori per ereditare i criteri di una riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="269d7-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="269d7-140">[Creare gruppi di sicurezza](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="269d7-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="269d7-141">[Assegnare un criterio a un gruppo di sicurezza](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="269d7-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="269d7-142">[Rimuovere un criterio direttamente assegnato agli utenti](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="269d7-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="269d7-143">Creare gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="269d7-143">Create security groups</span></span>

<span data-ttu-id="269d7-144">Prima di tutto, crea un gruppo di sicurezza per il personale e gli educatori.</span><span class="sxs-lookup"><span data-stu-id="269d7-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="269d7-145">Con [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), puoi [facilmente creare gruppi di sicurezza per educatori e studenti](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) nella tua scuola.</span><span class="sxs-lookup"><span data-stu-id="269d7-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="269d7-146">Ti consigliamo di usare SDS per creare i gruppi di sicurezza necessari per gestire i criteri per la tua scuola.</span><span class="sxs-lookup"><span data-stu-id="269d7-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="269d7-147">Se non si riesce a distribuire SDS nell'ambiente, usare [questo script di PowerShell](scripts/powershell-script-security-groups-edu.md) per creare due gruppi di sicurezza, uno per tutti i membri del personale e gli educatori che hanno una licenza di facoltà e un altro per tutti gli studenti a cui è assegnata una licenza per studenti.</span><span class="sxs-lookup"><span data-stu-id="269d7-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="269d7-148">È necessario eseguire questo script in modo sistematico per aggiornare i gruppi.</span><span class="sxs-lookup"><span data-stu-id="269d7-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="269d7-149">Assegnare un criterio a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="269d7-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="269d7-150">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="269d7-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="269d7-151">Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft teams è disponibile solo per i criteri di chiamata dei team, i criteri di parcheggio per i team, i criteri per i team, i criteri per le riunioni dei team e i criteri di messaggistica di team.</span><span class="sxs-lookup"><span data-stu-id="269d7-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="269d7-152">Per altri tipi di criteri, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="269d7-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="269d7-153">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="269d7-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="269d7-154">Selezionare la scheda **assegnazione criteri di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="269d7-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="269d7-155">Selezionare **Aggiungi gruppo**e quindi nel riquadro **Assegna criteri a gruppo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="269d7-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Screenshot del riquadro Modifica impostazioni che mostra i criteri delle riunioni](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="269d7-157">Nella casella **selezionare un gruppo** cercare e aggiungere il gruppo di sicurezza che contiene il personale e gli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="269d7-158">Nella casella **Seleziona rango** immettere **1**.</span><span class="sxs-lookup"><span data-stu-id="269d7-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="269d7-159">Nella casella **selezionare un criterio** selezionare **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="269d7-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="269d7-160">Selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="269d7-160">Select **Apply**.</span></span>

<span data-ttu-id="269d7-161">Per rimuovere un'assegnazione di criteri di gruppo, nella scheda assegnazione criteri di **gruppo** della pagina Criteri selezionare l'assegnazione del gruppo e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="269d7-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="269d7-162">Per modificare la classificazione di un'assegnazione di gruppo, è necessario rimuovere prima di tutto l'assegnazione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="269d7-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="269d7-163">Seguire quindi la procedura descritta in precedenza per assegnare i criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="269d7-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="269d7-164">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="269d7-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="269d7-165">Attualmente, l'assegnazione dei criteri ai gruppi che usano PowerShell non è disponibile per tutti i tipi di criteri teams.</span><span class="sxs-lookup"><span data-stu-id="269d7-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="269d7-166">Vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="269d7-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="269d7-167">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269d7-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="269d7-168">Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="269d7-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="269d7-169">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="269d7-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="269d7-170">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="269d7-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="269d7-171">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="269d7-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="269d7-172">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="269d7-172">Assign a policy to a group</span></span>

<span data-ttu-id="269d7-173">Eseguire la procedura seguente per assegnare il criterio della riunione denominato EducatorMeetingPolicy al gruppo di sicurezza che contiene il personale e gli insegnanti e impostare la classificazione delle assegnazioni su 1.</span><span class="sxs-lookup"><span data-stu-id="269d7-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="269d7-174">Puoi specificare un gruppo di sicurezza usando l'ID oggetto, l'indirizzo SIP (Session Initiation Protocol) o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="269d7-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="269d7-175">In questo esempio usiamo un indirizzo di posta elettronica (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="269d7-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="269d7-176">Rimuovere un criterio assegnato direttamente agli utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="269d7-177">Tenere presente che se all'utente è stato assegnato un criterio direttamente (individualmente o tramite un'assegnazione batch), tale criterio ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="269d7-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="269d7-178">Ciò significa che se un utente ha un criterio di riunione direttamente assegnato a tali criteri, sarà necessario rimuovere i criteri della riunione dall'utente prima che possano ereditare i criteri di una riunione da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="269d7-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="269d7-179">Per altre informazioni, vedere [cosa occorre sapere sull'assegnazione dei criteri ai gruppi](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="269d7-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="269d7-180">Seguire questa procedura per rimuovere i criteri della riunione direttamente assegnati al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="269d7-181">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269d7-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="269d7-182">Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="269d7-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="269d7-183">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="269d7-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="269d7-184">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="269d7-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="269d7-185">Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="269d7-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="269d7-186">Annullare l'assegnazione di un criterio assegnato direttamente agli utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="269d7-187">Eseguire la procedura seguente per rimuovere un criterio della riunione dagli utenti a cui è stato assegnato direttamente il criterio.</span><span class="sxs-lookup"><span data-stu-id="269d7-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="269d7-188">Puoi specificare gli utenti tramite l'indirizzo di posta elettronica o l'ID oggetto.</span><span class="sxs-lookup"><span data-stu-id="269d7-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="269d7-189">In questo esempio, il criterio della riunione viene rimosso dagli utenti specificati dall'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="269d7-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="269d7-190">In questo esempio, il criterio della riunione viene rimosso dall'elenco di utenti in un file di testo denominato user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="269d7-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="269d7-191">Ottenere le assegnazioni dei criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="269d7-191">Get policy assignments for a group</span></span>

<span data-ttu-id="269d7-192">Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="269d7-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="269d7-193">Tieni presente che i gruppi sono sempre elencati dall'ID del gruppo, anche se l'indirizzo SIP o l'indirizzo di posta elettronica è stato usato per assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="269d7-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="269d7-194">Ottenere i criteri assegnati a un utente</span><span class="sxs-lookup"><span data-stu-id="269d7-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="269d7-195">Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="269d7-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="269d7-196">L'esempio seguente mostra come ottenere i criteri assegnati a reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="269d7-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="269d7-197">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="269d7-198">Seguire questa procedura per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy direttamente al personale e agli insegnanti in blocco.</span><span class="sxs-lookup"><span data-stu-id="269d7-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="269d7-199">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="269d7-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="269d7-200">Connettersi al modulo di Azure AD PowerShell per il grafico e al modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="269d7-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="269d7-201">Prima di eseguire la procedura descritta in questo articolo, è necessario installare e connettersi a Azure AD PowerShell per il modulo grafico (per identificare gli utenti tramite le licenze assegnate) e il modulo di PowerShell di Microsoft Teams (per assegnare i criteri a tali utenti).</span><span class="sxs-lookup"><span data-stu-id="269d7-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="269d7-202">Installare e connettersi al modulo di Azure AD PowerShell per il grafico</span><span class="sxs-lookup"><span data-stu-id="269d7-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="269d7-203">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire le operazioni seguenti per installare il modulo di PowerShell per il grafico di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="269d7-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="269d7-204">Eseguire la procedura seguente per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="269d7-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="269d7-205">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="269d7-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="269d7-206">Per altre informazioni, vedere [connettersi con il modulo di PowerShell per il grafico di Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="269d7-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="269d7-207">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269d7-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="269d7-208">Eseguire la procedura seguente per installare il [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già installato).</span><span class="sxs-lookup"><span data-stu-id="269d7-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="269d7-209">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="269d7-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="269d7-210">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="269d7-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="269d7-211">Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="269d7-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="269d7-212">Identificare gli utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-212">Identify your users</span></span>

<span data-ttu-id="269d7-213">Prima di tutto, Esegui le operazioni seguenti per identificare il personale e gli educatori per tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="269d7-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="269d7-214">Questo spiega quali SKU sono in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="269d7-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="269d7-215">È quindi possibile identificare il personale e gli insegnanti che hanno un SKU di facoltà assegnato.</span><span class="sxs-lookup"><span data-stu-id="269d7-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="269d7-216">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="269d7-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="269d7-217">In questo esempio l'output mostra che la licenza di facoltà SkuId è "e97c048c-37a4-45fb-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="269d7-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="269d7-218">Per visualizzare un elenco di SKU per l'istruzione e ID SKU, vedere informazioni di [riferimento su SKU per l'](sku-reference-edu.md)istruzione.</span><span class="sxs-lookup"><span data-stu-id="269d7-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="269d7-219">Eseguiamo quindi le operazioni seguenti per identificare gli utenti con questa licenza e raccoglierli tutti insieme.</span><span class="sxs-lookup"><span data-stu-id="269d7-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="269d7-220">Assegnare un criterio in blocco</span><span class="sxs-lookup"><span data-stu-id="269d7-220">Assign a policy in bulk</span></span>

<span data-ttu-id="269d7-221">A questo punto, assegniamo i criteri appropriati agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="269d7-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="269d7-222">Il numero massimo di utenti per cui è possibile assegnare o aggiornare i criteri è 5.000 alla volta.</span><span class="sxs-lookup"><span data-stu-id="269d7-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="269d7-223">Ad esempio, se si hanno più di 5.000 personale ed educatori, è necessario inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="269d7-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="269d7-224">Eseguire la procedura seguente per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="269d7-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="269d7-225">Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare ```PolicyType``` al criterio che si sta assegnando e ```PolicyName``` al nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="269d7-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="269d7-226">Ottenere lo stato di un'assegnazione in blocco</span><span class="sxs-lookup"><span data-stu-id="269d7-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="269d7-227">Ogni assegnazione in blocco restituisce un ID operazione, che può essere usato per tenere traccia dell'avanzamento delle assegnazioni dei criteri o per identificare eventuali errori che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="269d7-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="269d7-228">Ad esempio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="269d7-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="269d7-229">Per visualizzare lo stato di assegnazione di ogni utente nell'operazione batch, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="269d7-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="269d7-230">I dettagli di ogni utente si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="269d7-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="269d7-231">Assegnare un criterio in blocco se si hanno più di 5.000 utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="269d7-232">Prima di tutto, eseguire le operazioni seguenti per verificare il numero di membri del personale e gli insegnanti:</span><span class="sxs-lookup"><span data-stu-id="269d7-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="269d7-233">Invece di fornire l'intero elenco di ID utente, eseguire la procedura seguente per specificare il primo 5.000 e quindi il successivo 5.000 e così via.</span><span class="sxs-lookup"><span data-stu-id="269d7-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="269d7-234">Puoi modificare l'intervallo di ID utente fino a raggiungere l'elenco completo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="269d7-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="269d7-235">Ad esempio, immetti ```$faculty[0..4999``` per il primo batch, USA ```$faculty[5000..9999``` per il secondo batch, immetti ```$faculty[10000..14999``` per il terzo batch e così via.</span><span class="sxs-lookup"><span data-stu-id="269d7-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="269d7-236">Ottenere i criteri assegnati a un utente</span><span class="sxs-lookup"><span data-stu-id="269d7-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="269d7-237">Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="269d7-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="269d7-238">L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="269d7-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="269d7-239">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="269d7-239">FAQ</span></span>

<span data-ttu-id="269d7-240">**Non si ha familiarità con PowerShell per Teams. Dove è possibile ottenere altre informazioni?**</span><span class="sxs-lookup"><span data-stu-id="269d7-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="269d7-241">Per una panoramica sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="269d7-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="269d7-242">Per altre informazioni sui cmdlet usati in questo articolo, vedere:</span><span class="sxs-lookup"><span data-stu-id="269d7-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="269d7-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="269d7-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="269d7-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="269d7-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="269d7-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="269d7-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="269d7-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="269d7-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="269d7-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="269d7-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="269d7-248">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="269d7-248">Related topics</span></span>

- [<span data-ttu-id="269d7-249">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="269d7-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="269d7-250">Criteri per i team e pacchetti di criteri per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="269d7-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="269d7-251">Gestire i criteri di riunione in Teams</span><span class="sxs-lookup"><span data-stu-id="269d7-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
