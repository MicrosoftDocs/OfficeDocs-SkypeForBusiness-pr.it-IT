---
title: Usare Teams con i servizi desktop remoto
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare Microsoft Teams con i servizi Desktop remoto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ac88778fca7034446d0ec42a0a4a65d7c76f979
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278898"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="b966f-103">Teams in Servizi Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="b966f-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="b966f-104">Questo articolo descrive i requisiti e le limitazioni per l'uso di Microsoft Teams in un ambiente Servizi Desktop remoto.</span><span class="sxs-lookup"><span data-stu-id="b966f-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="b966f-105">Che cos'è Servizi Desktop remoto?</span><span class="sxs-lookup"><span data-stu-id="b966f-105">What is RDS?</span></span>

<span data-ttu-id="b966f-106">Servizi Desktop remoto è la piattaforma ideale per la creazione di soluzioni di virtualizzazione per ogni esigenza del cliente finale.</span><span class="sxs-lookup"><span data-stu-id="b966f-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="b966f-107">Servizi Desktop remoto consente di distribuire singole applicazioni virtualizzate, offrire un accesso sicuro a dispositivi mobili e Desktop remoto e offrire agli utenti finali la possibilità di eseguire le applicazioni e i desktop dal cloud.</span><span class="sxs-lookup"><span data-stu-id="b966f-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="b966f-108">Servizi Desktop remoto offre flessibilità della distribuzione, efficienza dei costi ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="b966f-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="b966f-109">Servizi Desktop remoto offre numerose opzioni di distribuzione, tra cui Windows Server 2016 per le distribuzioni locali, Microsoft Azure per le distribuzioni cloud e una solida gamma di soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="b966f-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="b966f-110">A seconda dell'ambiente e delle preferenze, è possibile configurare la soluzione Servizi Desktop remoto per la virtualizzazione basata su sessione come infrastruttura VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="b966f-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="b966f-111">Attualmente Teams in un ambiente di servizi desktop remoto è disponibile con supporto per la collaborazione e la funzionalità di chat.</span><span class="sxs-lookup"><span data-stu-id="b966f-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="b966f-112">Per assicurare un'esperienza utente ottimale, seguire le indicazioni fornite in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b966f-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="b966f-113">Teams su VDI con chat e collaborazione</span><span class="sxs-lookup"><span data-stu-id="b966f-113">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="b966f-114">Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello utente per disattivare le funzionalità di chiamata e riunione in Teams.</span><span class="sxs-lookup"><span data-stu-id="b966f-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="b966f-115">Impostare i criteri per disattivare la funzionalità di chiamata e riunione</span><span class="sxs-lookup"><span data-stu-id="b966f-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="b966f-116">È possibile impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b966f-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="b966f-117">La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore).</span><span class="sxs-lookup"><span data-stu-id="b966f-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b966f-118">Se non si vedono immediatamente le modifiche per un determinato account, riprovare tra qualche ora.</span><span class="sxs-lookup"><span data-stu-id="b966f-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="b966f-119">[**Criteri di chiamata:**](teams-calling-policy.md)Teams include il criterio di chiamata DisallowCalling incorporato, in cui tutte le funzionalità di chiamata sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="b966f-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="b966f-120">Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="b966f-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="b966f-121">[**Criteri riunione:**](meeting-policies-in-teams.md)Teams include il criterio predefinito per le riunioni AllOff, in cui tutte le funzionalità per le riunioni sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="b966f-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="b966f-122">Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="b966f-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b966f-123">Assegnare criteri tramite l'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b966f-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b966f-124">Per assegnare il criterio di chiamata DisallowCalling e il criterio Riunione AllOff a un utente:</span><span class="sxs-lookup"><span data-stu-id="b966f-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="b966f-125">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="b966f-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b966f-126">Selezionare l'utente selezionandolo a sinistra del nome utente e quindi **selezionando Modifica impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="b966f-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="b966f-127">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b966f-127">Do the following steps:</span></span>

    <span data-ttu-id="b966f-128">a.</span><span class="sxs-lookup"><span data-stu-id="b966f-128">a.</span></span>  <span data-ttu-id="b966f-129">In **Criteri di chiamata** selezionare **DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="b966f-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="b966f-130">b.</span><span class="sxs-lookup"><span data-stu-id="b966f-130">b.</span></span>  <span data-ttu-id="b966f-131">In **Criteri riunione** selezionare **AllOff.**</span><span class="sxs-lookup"><span data-stu-id="b966f-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="b966f-132">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="b966f-132">Select **Apply**.</span></span>

<span data-ttu-id="b966f-133">Per assegnare un criterio a più utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="b966f-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b966f-134">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="b966f-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b966f-135">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b966f-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b966f-136">Per selezionare tutti gli utenti, &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="b966f-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b966f-137">Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**</span><span class="sxs-lookup"><span data-stu-id="b966f-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="b966f-138">In caso contrario, è anche possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b966f-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="b966f-139">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare al criterio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="b966f-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b966f-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b966f-140">For example:</span></span>

    - <span data-ttu-id="b966f-141">Passare ai **criteri per**  >  **le chiamate** vocali, quindi selezionare **DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="b966f-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="b966f-142">Passare a **Criteri**  >  **riunione riunioni,** quindi selezionare **AllOff.**</span><span class="sxs-lookup"><span data-stu-id="b966f-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="b966f-143">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="b966f-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="b966f-144">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b966f-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b966f-145">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b966f-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b966f-146">Dopo aver aggiunto gli utenti, selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b966f-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b966f-147">Assegnare criteri con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b966f-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="b966f-148">L'esempio seguente mostra come utilizzare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.</span><span class="sxs-lookup"><span data-stu-id="b966f-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="b966f-149">Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b966f-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b966f-150">L'esempio seguente mostra come utilizzare il cmdlet [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione AllOff a un utente.</span><span class="sxs-lookup"><span data-stu-id="b966f-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="b966f-151">Per altre informazioni sull'uso di PowerShell per gestire i criteri di riunione, vedi [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b966f-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>
