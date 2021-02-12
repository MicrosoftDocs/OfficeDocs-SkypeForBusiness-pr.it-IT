---
title: Eseguire l'aggiornamento da Skype for Business online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione di Skype for Business Online.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578259"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="46cc2-103">Eseguire l'aggiornamento da Skype for Business online a Teams</span><span class="sxs-lookup"><span data-stu-id="46cc2-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="46cc2-104">![Diagramma percorso di aggiornamento, enfatizzando distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="46cc2-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="46cc2-105">Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="46cc2-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="46cc2-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="46cc2-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="46cc2-107">Integrare gli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="46cc2-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="46cc2-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="46cc2-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="46cc2-109">Coesistenza e interoperabilità comprensibili di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="46cc2-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="46cc2-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="46cc2-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="46cc2-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="46cc2-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="46cc2-112">Organizzazione preparata</span><span class="sxs-lookup"><span data-stu-id="46cc2-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="46cc2-113">Ha diretto un pilota</span><span class="sxs-lookup"><span data-stu-id="46cc2-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="46cc2-114">Segui le indicazioni in questo articolo se hai distribuito completamente Skype for Business online e desideri aggiornare gli utenti da Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="46cc2-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="46cc2-115">È possibile aggiornare gli utenti in modo selettivo o all-in, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando agli utenti la modalità di coesistenza e aggiornamento appropriata.</span><span class="sxs-lookup"><span data-stu-id="46cc2-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46cc2-116">Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato.</span><span class="sxs-lookup"><span data-stu-id="46cc2-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="46cc2-117">Per ottimizzare la realizzazione dei vantaggi e garantire alla tua organizzazione il tempo necessario per implementare il tuo aggiornamento, ti consigliamo di iniziare oggi stesso il tuo percorso verso Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46cc2-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="46cc2-118">Ricorda che un aggiornamento riuscito allinea la preparazione tecnica e quella degli utenti, quindi assicurati di avvalerti delle indicazioni riportate qui mentre ti snavigare verso Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46cc2-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="46cc2-119">Assegnare la modalità di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="46cc2-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="46cc2-120">Puoi aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita utilizzando l'interfaccia di amministrazione di Microsoft Teams o una sessione di Windows PowerShell remota di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="46cc2-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="46cc2-121">È possibile eseguire questa operazione a livello di utente o a livello di tenant se si vuole aggiornare l'intero tenant in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="46cc2-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="46cc2-122">Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](https://aka.ms/SkypeToTeams-SetCoexistence) e aggiornamento [e TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="46cc2-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="46cc2-123">Aggiornare tutti gli utenti a Teams contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="46cc2-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="46cc2-124">Seguire questa procedura per aggiornare tutti gli utenti a Teams contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="46cc2-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="46cc2-125">Passaggio 1: Informare gli utenti della modifica (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="46cc2-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="46cc2-126">Nell'interfaccia di amministrazione di Microsoft Teams, selezionare Impostazioni **a livello di organizzazione Aggiornamento** di  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="46cc2-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="46cc2-127">In **modalità coesistenza,** imposta l'interruttore Informa gli utenti di Skype for Business che è disponibile un aggiornamento **a** **Teams.**</span><span class="sxs-lookup"><span data-stu-id="46cc2-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="46cc2-128">Passaggio 2: Impostare la modalità di coesistenza su TeamsOnly per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="46cc2-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="46cc2-129">Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni a livello di organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="46cc2-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="46cc2-130">Selezionare **modalità Solo** teams nell'elenco a discesa Modalità di **coesistenza.**</span><span class="sxs-lookup"><span data-stu-id="46cc2-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="46cc2-131">Aggiornare gli utenti in più fasi</span><span class="sxs-lookup"><span data-stu-id="46cc2-131">Upgrade users in stages</span></span>

<span data-ttu-id="46cc2-132">Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="46cc2-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="46cc2-133">Passaggio 1: Identificare i gruppi di utenti per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="46cc2-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="46cc2-134">Spesso le organizzazioni possono scegliere di aggiornare la propria organizzazione in gruppi di utenti di successo.</span><span class="sxs-lookup"><span data-stu-id="46cc2-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="46cc2-135">È prima di tutto necessario identificare questi utenti in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46cc2-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="46cc2-136">In alternativa, è possibile usare PowerShell per eseguire questa operazione in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="46cc2-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="46cc2-137">Dopo aver identificato il set di utenti per una determinata ondata di aggiornamenti, continuare con i passaggi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="46cc2-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="46cc2-138">Passaggio 2: Impostare la notifica per gli utenti nella fase di aggiornamento corrente (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="46cc2-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="46cc2-139">Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="46cc2-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="46cc2-140">Nell'interfaccia di amministrazione di Microsoft Teams selezionare Utenti e trovare e selezionare più caselle di controllo per un massimo di 20 utenti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="46cc2-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="46cc2-141">Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="46cc2-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="46cc2-142">Nel riquadro **Modifica impostazioni a** destra, in Aggiornamento **Teams,** modifica Informa l'utente **di Skype for Business** su **Attiva.**</span><span class="sxs-lookup"><span data-stu-id="46cc2-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="46cc2-143">Nota: se il valore della modalità di coesistenza è "Usa impostazioni a livello di organizzazione", questo parametro non viene visualizzato, quindi è necessario prima impostare esplicitamente la modalità di coesistenza per questi utenti sul valore predefinito per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46cc2-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="46cc2-144">In alternativa, può risultare più facile abilitare le notifiche per gruppi di utenti contemporaneamente con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46cc2-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="46cc2-145">Passaggio 3: Impostare la modalità di coesistenza per gli utenti solo su Teams</span><span class="sxs-lookup"><span data-stu-id="46cc2-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="46cc2-146">Quando si è pronti ad aggiornare gli utenti nella corrente per usare Teams come unica applicazione, impostare la modalità di coesistenza per gli utenti solo su Teams.</span><span class="sxs-lookup"><span data-stu-id="46cc2-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="46cc2-147">Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="46cc2-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="46cc2-148">Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti,** quindi selezionare la casella di controllo per un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="46cc2-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="46cc2-149">Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="46cc2-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="46cc2-150">Nel riquadro **Modifica impostazioni a** destra, nella sezione aggiornamento di **Teams,** impostare la modalità di coesistenza su **Solo team** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="46cc2-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="46cc2-151">In alternativa, può risultare più semplice aggiornare gruppi di utenti contemporaneamente con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46cc2-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="46cc2-152">Passaggio 4: Ripetere i passaggi da 1 a 3 per gruppi di utenti successivi</span><span class="sxs-lookup"><span data-stu-id="46cc2-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="46cc2-153">Quando si convalida l'aggiornamento alla modalità Solo Teams ed è pronto per l'espansione, ripetere i passaggi precedenti per applicare TeamsOnly a più utenti.</span><span class="sxs-lookup"><span data-stu-id="46cc2-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="46cc2-154">Opzioni di connettività Sistema telefonico e PSTN</span><span class="sxs-lookup"><span data-stu-id="46cc2-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="46cc2-155">Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="46cc2-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="46cc2-156">Se l'utente è in modalità Isole, il Sistema telefonico è supportato solo con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="46cc2-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="46cc2-157">Opzioni di connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="46cc2-157">PSTN connectivity options</span></span>

<span data-ttu-id="46cc2-158">Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due scenari possibili quando si passa dalla modalità Skype for Business Online alla modalità TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="46cc2-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="46cc2-159">Un utente in Skype for Business online, con un Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46cc2-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="46cc2-160">Al momento dell'aggiornamento, l'utente continuerà a disporre di un piano per le chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46cc2-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="46cc2-161">Questo è lo scenario più semplice che richiede solo un paio di passaggi.</span><span class="sxs-lookup"><span data-stu-id="46cc2-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="46cc2-162">Per ulteriori informazioni, consulta [Da Skype for Business online con Piani per chiamate Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="46cc2-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="46cc2-163">Un utente in Skype for Business online, con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="46cc2-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="46cc2-164">L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly abbia funzionalità PSTN.</span><span class="sxs-lookup"><span data-stu-id="46cc2-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="46cc2-165">Per ulteriori informazioni, [vedere Da Skype for Business online con voce locale.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="46cc2-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>


