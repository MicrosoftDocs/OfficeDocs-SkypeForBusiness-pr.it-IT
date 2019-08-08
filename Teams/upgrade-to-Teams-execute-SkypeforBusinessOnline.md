---
title: Aggiornare Skype for business online a Microsoft Teams | Distribuire
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento a teams da Skype for business online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f4a7076a5911798664ea1b7668e7dee8c820ff1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235862"
---
<span data-ttu-id="217cc-103">![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="217cc-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="217cc-104">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="217cc-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="217cc-105">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="217cc-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="217cc-106">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="217cc-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="217cc-107">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="217cc-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="217cc-108">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="217cc-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="217cc-109">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="217cc-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="217cc-110">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="217cc-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="217cc-111">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="217cc-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="217cc-112">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="217cc-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="217cc-113">Eseguire l'aggiornamento da Skype for business online a teams</span><span class="sxs-lookup"><span data-stu-id="217cc-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="217cc-114">Seguire le indicazioni di questo articolo se si è completamente distribuito Skype for business online e si vuole aggiornare gli utenti da Skype for business a teams.</span><span class="sxs-lookup"><span data-stu-id="217cc-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="217cc-115">È possibile aggiornare gli utenti in modo selettivo o all-in, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando la modalità di coesistenza e l'aggiornamento appropriata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="217cc-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="217cc-116">Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato.</span><span class="sxs-lookup"><span data-stu-id="217cc-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="217cc-117">Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="217cc-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="217cc-118">Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="217cc-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="217cc-119">Assegnare la modalità di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="217cc-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="217cc-120">Puoi aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza di UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita usando l'interfaccia di amministrazione di Microsoft teams o una sessione remota di Windows PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="217cc-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="217cc-121">Puoi eseguire questa operazione per ogni utente o in base a un tenant, se vuoi aggiornare l'intero tenant in un solo passaggio.</span><span class="sxs-lookup"><span data-stu-id="217cc-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="217cc-122">Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)della coesistenza.</span><span class="sxs-lookup"><span data-stu-id="217cc-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="217cc-123">Aggiornare tutti gli utenti a teams in una sola volta</span><span class="sxs-lookup"><span data-stu-id="217cc-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="217cc-124">Seguire questa procedura per aggiornare tutti gli utenti ai team contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="217cc-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="217cc-125">Passaggio 1: notificare agli utenti la modifica (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="217cc-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="217cc-126">Nell'interfaccia di amministrazione di Microsoft teams selezionare l'**aggiornamento dei team**di **Impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="217cc-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="217cc-127">In **modalità**di coesistenza cambiare gli **utenti di Notify Skype for business che è disponibile un aggiornamento a teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="217cc-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="217cc-128">Passaggio 2: impostare la modalità di coesistenza su TeamsOnly per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="217cc-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="217cc-129">Nell'interfaccia di amministrazione di Microsoft teams selezionare **impostazioni a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="217cc-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="217cc-130">Selezionare modalità **solo teams** nell'elenco a discesa **modalità** di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="217cc-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="217cc-131">Aggiornare gli utenti in fasi</span><span class="sxs-lookup"><span data-stu-id="217cc-131">Upgrade users in stages</span></span>

<span data-ttu-id="217cc-132">Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="217cc-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="217cc-133">Passaggio 1: identificare i gruppi di utenti per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="217cc-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="217cc-134">Spesso le organizzazioni possono scegliere di aggiornare le loro organizzazioni in ondate di successo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="217cc-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="217cc-135">È consigliabile identificare prima di tutto questi utenti, in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="217cc-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="217cc-136">In alternativa, è consigliabile usare PowerShell per eseguire questa operazione in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="217cc-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="217cc-137">Dopo aver identificato il set di utenti per una determinata onda di aggiornamento, continuare con i passaggi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="217cc-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="217cc-138">Passaggio 2: impostare la notifica per gli utenti nell'onda di aggiornamento corrente (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="217cc-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="217cc-139">Se si usa l'interfaccia di amministrazione di Microsoft teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="217cc-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="217cc-140">Nell'interfaccia di amministrazione di Microsoft teams seleziona **utenti**e trova e seleziona la casella di controllo per un massimo di 20 utenti che devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="217cc-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="217cc-141">Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra del controllo ListView.</span><span class="sxs-lookup"><span data-stu-id="217cc-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="217cc-142">Nel riquadro **Modifica impostazioni** a destra, in **aggiornamento teams**, cambia **notifica l'opzione utente Skype for business** su **attiva**.</span><span class="sxs-lookup"><span data-stu-id="217cc-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="217cc-143">Nota: se il valore della modalità di coesistenza è "Usa impostazioni a livello di organizzazione", non vedrai questo interruttore, quindi dovrai prima impostare esplicitamente la modalità di coesistenza per questi utenti in qualsiasi valore predefinito sia per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="217cc-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="217cc-144">In alternativa, è possibile che sia più facile abilitare le notifiche per i gruppi di utenti contemporaneamente usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="217cc-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="217cc-145">Passaggio 3: impostare la modalità di coesistenza per gli utenti solo per i team</span><span class="sxs-lookup"><span data-stu-id="217cc-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="217cc-146">Quando si è pronti per aggiornare gli utenti nell'onda corrente per usare teams come unica applicazione, impostare la modalità di coesistenza per gli utenti solo per i team.</span><span class="sxs-lookup"><span data-stu-id="217cc-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="217cc-147">Se si usa l'interfaccia di amministrazione di Microsoft teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="217cc-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="217cc-148">Nell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**e quindi selezionare la casella di controllo per un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="217cc-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="217cc-149">Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra del controllo ListView.</span><span class="sxs-lookup"><span data-stu-id="217cc-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="217cc-150">Nel riquadro **Modifica impostazioni** a destra, in sezione **aggiornamento teams** , impostare la modalità di coesistenza su **Teams only** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="217cc-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="217cc-151">In alternativa, è possibile che sia più facile aggiornare i gruppi di utenti contemporaneamente usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="217cc-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="217cc-152">Passaggio 4: ripetere i passaggi 1-3 per le onde successive degli utenti</span><span class="sxs-lookup"><span data-stu-id="217cc-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="217cc-153">Quando si convalida l'aggiornamento alla modalità solo teams e si è pronti per espandersi, ripetere i passaggi precedenti per applicare TeamsOnly a più utenti.</span><span class="sxs-lookup"><span data-stu-id="217cc-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="217cc-154">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="217cc-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="217cc-155">Se la distribuzione di Skype for business online include il sistema telefonico con i piani per le chiamate e Microsoft è il provider PSTN (Public Switched Telephone Network), l'aggiornamento degli utenti a teams eseguirà automaticamente la transizione delle chiamate PSTN in ingresso ai team.</span><span class="sxs-lookup"><span data-stu-id="217cc-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="217cc-156">Se la distribuzione di Skype for business online include il sistema telefonico con Cloud Connector Edition, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="217cc-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
