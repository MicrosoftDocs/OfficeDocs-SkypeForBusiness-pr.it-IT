---
title: Gestire l'app turni per l'organizzazione
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come configurare e gestire l'app turni in teams per gli operatori di I FIRSTLINE dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9298ed02c6b8559bdaf1e59c74a149a9d5164124
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141189"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="0352d-103">Gestire l'app turni per l'organizzazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0352d-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0352d-104">Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="0352d-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="0352d-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0352d-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="0352d-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0352d-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="0352d-107">StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="0352d-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="0352d-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="0352d-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="0352d-109">Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="0352d-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="0352d-110">Panoramica dei turni</span><span class="sxs-lookup"><span data-stu-id="0352d-110">Overview of Shifts</span></span>

<span data-ttu-id="0352d-111">L'app turni in Microsoft teams mantiene i dipendenti di I FIRSTLINE connessi e sincronizzati. È stato costruito per la prima volta per la gestione e la comunicazione del tempo veloce ed efficace per i team.</span><span class="sxs-lookup"><span data-stu-id="0352d-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="0352d-112">Turni consente ai dipendenti di I FIRSTLINE e ai loro manager di usare i loro dispositivi mobili per gestire le pianificazioni e tenersi in contatto.</span><span class="sxs-lookup"><span data-stu-id="0352d-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="0352d-113">I manager creano, aggiornano e gestiscono le pianificazioni di turno per i team.</span><span class="sxs-lookup"><span data-stu-id="0352d-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="0352d-114">Possono inviare messaggi a una sola persona ("c'è una fuoriuscita sul pavimento") o all'intero team ("il GM regionale arriva in 20 minuti").</span><span class="sxs-lookup"><span data-stu-id="0352d-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="0352d-115">Possono anche inviare documenti di policy, notiziari e video.</span><span class="sxs-lookup"><span data-stu-id="0352d-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="0352d-116">I dipendenti visualizzano i loro turni imminenti, possono vedere chi altro è programmato per il giorno, richiedere di scambiare o offrire un turno e richiedere il tempo libero.</span><span class="sxs-lookup"><span data-stu-id="0352d-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="0352d-117">È importante sapere che i turni attualmente non supportano gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="0352d-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="0352d-118">Ciò significa che gli ospiti di un team non possono essere aggiunti o usare le pianificazioni di turni quando l'accesso Guest è attivato in teams.</span><span class="sxs-lookup"><span data-stu-id="0352d-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="0352d-119">Disponibilità di turni</span><span class="sxs-lookup"><span data-stu-id="0352d-119">Availability of Shifts</span></span>

<span data-ttu-id="0352d-120">Turni è disponibile in tutti gli SKU aziendali in cui è disponibile teams.</span><span class="sxs-lookup"><span data-stu-id="0352d-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="0352d-121">Posizione dei dati di turni</span><span class="sxs-lookup"><span data-stu-id="0352d-121">Location of Shifts data</span></span>

<span data-ttu-id="0352d-122">Turni i dati sono attualmente archiviati in Azure nei data center in Nord America, Europa occidentale e Asia Pacifico.</span><span class="sxs-lookup"><span data-stu-id="0352d-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="0352d-123">Per altre informazioni sulla posizione di archiviazione dei dati, vedere [dove sono i dati](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="0352d-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="0352d-124">Configurare turni</span><span class="sxs-lookup"><span data-stu-id="0352d-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="0352d-125">Abilitare o disabilitare i turni nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0352d-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="0352d-126">Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0352d-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="0352d-127">Puoi disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0352d-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="0352d-128">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle >  **app teams\*\*\*\*Manage Apps** .</span><span class="sxs-lookup"><span data-stu-id="0352d-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="0352d-129">Nell'elenco delle app eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0352d-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="0352d-130">Per disattivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi fare clic su **blocca**.</span><span class="sxs-lookup"><span data-stu-id="0352d-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="0352d-131">Per attivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi fare clic su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="0352d-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="0352d-132">Abilitare o disabilitare turni per utenti specifici dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0352d-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="0352d-133">Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso di turni, verificare che i turni siano attivati per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) e quindi creare un criterio di autorizzazione per le app personalizzate e assegnarlo a tali utenti.</span><span class="sxs-lookup"><span data-stu-id="0352d-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="0352d-134">Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0352d-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="0352d-135">Usare i criteri di configurazione dell'app FirstlineWorker per aggiungere i turni ai team</span><span class="sxs-lookup"><span data-stu-id="0352d-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="0352d-136">I criteri di configurazione delle app consentono di personalizzare i team per evidenziare le app più importanti per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0352d-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="0352d-137">Le app impostate in un criterio sono bloccate alla barra&mdash;dell'app la barra sul lato del client desktop teams e nella parte inferiore dei client&mdash;per dispositivi mobili in cui gli utenti possono accedervi in modo rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="0352d-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="0352d-138">Teams include un criterio di configurazione dell'app FirstlineWorker predefinito che puoi assegnare a dipendenti di I FIRSTLINE nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0352d-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="0352d-139">Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate.</span><span class="sxs-lookup"><span data-stu-id="0352d-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="0352d-140">Per visualizzare i criteri di FirstlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai**criteri di configurazione**dell'app **Teams app** > .</span><span class="sxs-lookup"><span data-stu-id="0352d-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="0352d-141">![Screenshot dei criteri di configurazione dell'app FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot dei criteri di configurazione dell'app FirstlineWorker nell'interfaccia di amministrazione di Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="0352d-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="0352d-142">Assegnare i criteri di FirstlineWorker a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="0352d-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="0352d-143">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="0352d-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="0352d-144">Accanto a **criteri assegnati**scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="0352d-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="0352d-145">In **criteri di configurazione dell'app teams**selezionare **FirstlineWorker**e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0352d-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="0352d-146">Assegnare i criteri di configurazione dell'app FirstlineWorker ai membri di un gruppo</span><span class="sxs-lookup"><span data-stu-id="0352d-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="0352d-147">Puoi assegnare i criteri di configurazione dell'app FirstlineWorker ai membri di un gruppo, ad esempio un gruppo di sicurezza, connettendosi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0352d-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="0352d-148">Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0352d-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="0352d-149">In questo esempio, assegniamo i criteri di configurazione dell'app FirstlineWorker a tutti i membri dell'utente del gruppo di team Contoso I FIRSTLINE.</span><span class="sxs-lookup"><span data-stu-id="0352d-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="0352d-150">Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="0352d-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="0352d-151">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="0352d-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="0352d-152">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="0352d-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0352d-153">Assegnare i criteri di configurazione dell'app FirstlineWorker a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0352d-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="0352d-154">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0352d-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0352d-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0352d-155">Related topics</span></span>
- [<span data-ttu-id="0352d-156">Sposta la guida per gli operatori di I FIRSTLINE</span><span class="sxs-lookup"><span data-stu-id="0352d-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
