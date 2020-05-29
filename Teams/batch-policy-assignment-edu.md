---
title: Assegnare criteri a grandi gruppi di utenti nella tua scuola
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Informazioni su come usare l'assegnazione di criteri batch per assegnare i criteri a set di grandi dimensioni degli utenti nell'Istituto di istruzione in blocco per scopi scolastici remoti (Teleschool, tele-scuola).
f1keywords: ''
ms.openlocfilehash: 5772a260642b09232e4df5eec57751a39ec2a74a
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410441"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="3783d-103">Assegnare criteri a grandi gruppi di utenti nella tua scuola</span><span class="sxs-lookup"><span data-stu-id="3783d-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="3783d-104">È necessario offrire agli studenti e agli insegnanti l'accesso a funzionalità diverse in Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3783d-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="3783d-105">È possibile identificare rapidamente gli utenti dell'organizzazione per tipo di licenza e quindi assegnare il criterio appropriato.</span><span class="sxs-lookup"><span data-stu-id="3783d-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="3783d-106">In questa esercitazione viene illustrato come usare l' [assegnazione di criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) per assegnare un criterio di riunione agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="3783d-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="3783d-107">Tenere presente che in teams gli utenti ottengono automaticamente il criterio globale (org-Wide default) per un tipo di criteri teams, a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3783d-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="3783d-108">Poiché la popolazione studente è spesso il più grande insieme di utenti e spesso riceve le impostazioni più restrittive, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3783d-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="3783d-109">Modificare e applicare il criterio globale (predefinito a livello di organizzazione) per limitare le funzionalità per gli studenti.</span><span class="sxs-lookup"><span data-stu-id="3783d-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="3783d-110">Creare criteri personalizzati che consentano funzionalità di base, ad esempio la chat privata e la pianificazione delle riunioni, e assegnare i criteri al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="3783d-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="3783d-111">Tieni presente che il criterio globale verrà applicato a tutti gli utenti dell'Istituto di istruzione fino a quando non creerai un criterio personalizzato e lo assegnerò al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="3783d-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="3783d-112">In questa esercitazione gli studenti otterranno i criteri riunione globale e usiamo PowerShell per assegnare un criterio di riunione personalizzato denominato EducatorMeetingPolicy al personale e agli insegnanti in blocco.</span><span class="sxs-lookup"><span data-stu-id="3783d-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="3783d-113">Supponiamo che tu abbia modificato il criterio globale per adattare le impostazioni delle riunioni per gli studenti e creato un criterio personalizzato che definisce l'esperienza di riunione per il personale e gli educatori.</span><span class="sxs-lookup"><span data-stu-id="3783d-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Screenshot della pagina criteri riunione nell'interfaccia di amministrazione di Teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="3783d-115">Seguire questa procedura per assegnare un criterio di riunione personalizzato al personale e agli insegnanti in blocco.</span><span class="sxs-lookup"><span data-stu-id="3783d-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="3783d-116">Connettersi al modulo di Azure AD PowerShell per il grafico e al modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="3783d-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="3783d-117">Prima di eseguire la procedura descritta in questo articolo, è necessario installare e connettersi a Azure AD PowerShell per il modulo grafico (per identificare gli utenti tramite le licenze assegnate) e il modulo di PowerShell di Microsoft Teams (per assegnare i criteri a tali utenti).</span><span class="sxs-lookup"><span data-stu-id="3783d-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="3783d-118">Installare e connettersi al modulo di Azure AD PowerShell per il grafico</span><span class="sxs-lookup"><span data-stu-id="3783d-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="3783d-119">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore) e quindi eseguire le operazioni seguenti per installare il modulo di PowerShell per il grafico di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3783d-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="3783d-120">Eseguire la procedura seguente per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3783d-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="3783d-121">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3783d-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="3783d-122">Per altre informazioni, vedere [connettersi con il modulo di PowerShell per il grafico di Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3783d-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3783d-123">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3783d-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3783d-124">Eseguire la procedura seguente per installare il [modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="3783d-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="3783d-125">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3783d-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3783d-126">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="3783d-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="3783d-127">Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3783d-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="3783d-128">Identificare gli utenti</span><span class="sxs-lookup"><span data-stu-id="3783d-128">Identify your users</span></span>

<span data-ttu-id="3783d-129">Prima di tutto, Esegui le operazioni seguenti per identificare il personale e gli educatori per tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="3783d-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="3783d-130">Questo spiega quali SKU sono in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3783d-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="3783d-131">È quindi possibile identificare il personale e gli insegnanti che hanno un SKU di facoltà assegnato.</span><span class="sxs-lookup"><span data-stu-id="3783d-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="3783d-132">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="3783d-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="3783d-133">In questo esempio l'output mostra che la licenza di facoltà SkuId è "e97c048c-37a4-45fb-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="3783d-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="3783d-134">Per visualizzare un elenco di SKU per l'istruzione e ID SKU, vedere informazioni di [riferimento su SKU per l'](sku-reference-edu.md)istruzione.</span><span class="sxs-lookup"><span data-stu-id="3783d-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="3783d-135">Eseguiamo quindi le operazioni seguenti per identificare gli utenti con questa licenza e raccoglierli tutti insieme.</span><span class="sxs-lookup"><span data-stu-id="3783d-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="3783d-136">Assegnare un criterio in blocco</span><span class="sxs-lookup"><span data-stu-id="3783d-136">Assign a policy in bulk</span></span>

<span data-ttu-id="3783d-137">A questo punto, assegniamo i criteri appropriati agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="3783d-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="3783d-138">Il numero massimo di utenti per cui è possibile assegnare o aggiornare i criteri è 5.000 alla volta.</span><span class="sxs-lookup"><span data-stu-id="3783d-138">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="3783d-139">Ad esempio, se si hanno più di 5.000 personale ed educatori, è necessario inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="3783d-139">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>


<span data-ttu-id="3783d-140">Eseguire la procedura seguente per assegnare il criterio della riunione denominato EducatorMeetingPolicy al personale e agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="3783d-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="3783d-141">Per assegnare un tipo di criterio diverso in blocco, ad esempio TeamsMessagingPolicy, è necessario passare ```PolicyType``` al criterio che si sta assegnando e ```PolicyName``` al nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="3783d-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="3783d-142">Ottenere lo stato di un'assegnazione in blocco</span><span class="sxs-lookup"><span data-stu-id="3783d-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="3783d-143">Ogni assegnazione in blocco restituisce un ID operazione, che può essere usato per tenere traccia dell'avanzamento delle assegnazioni dei criteri o per identificare eventuali errori che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="3783d-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="3783d-144">Ad esempio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3783d-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="3783d-145">Per visualizzare lo stato di assegnazione di ogni utente nell'operazione batch, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="3783d-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="3783d-146">I dettagli di ogni utente si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3783d-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="3783d-147">Assegnare un criterio in blocco se si hanno più di 5.000 utenti</span><span class="sxs-lookup"><span data-stu-id="3783d-147">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="3783d-148">Prima di tutto, eseguire le operazioni seguenti per verificare il numero di membri del personale e gli insegnanti:</span><span class="sxs-lookup"><span data-stu-id="3783d-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="3783d-149">Invece di fornire l'intero elenco di ID utente, eseguire la procedura seguente per specificare il primo 5.000 e quindi il successivo 5.000 e così via.</span><span class="sxs-lookup"><span data-stu-id="3783d-149">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="3783d-150">Puoi modificare l'intervallo di ID utente fino a raggiungere l'elenco completo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3783d-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="3783d-151">Ad esempio, immetti ```$faculty[0..4999``` per il primo batch, USA ```$faculty[5000..9999``` per il secondo batch, immetti ```$faculty[10000..14999``` per il terzo batch e così via.</span><span class="sxs-lookup"><span data-stu-id="3783d-151">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="3783d-152">Ottenere i criteri assegnati a un utente</span><span class="sxs-lookup"><span data-stu-id="3783d-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="3783d-153">Eseguire la procedura seguente per visualizzare tutti i criteri assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="3783d-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="3783d-154">L'esempio seguente mostra come ottenere i criteri assegnati a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3783d-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="3783d-155">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="3783d-155">FAQ</span></span>

<span data-ttu-id="3783d-156">**Voglio assicurarmi che tutti gli utenti che sono studenti, personale ed educatori ottengano automaticamente i criteri assegnati. Come è possibile eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="3783d-156">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="3783d-157">Il team del prodotto teams sta lavorando per supportare l'assegnazione di criteri ai gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3783d-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="3783d-158">A questo punto è possibile creare gruppi per studenti e docenti e quindi i criteri appropriati per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="3783d-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="3783d-159">Tieni presente che le assegnazioni degli utenti esplicite, ad esempio i criteri assegnati con questa esercitazione, sostituiranno i criteri ereditati da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3783d-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="3783d-160">Quando questa funzionalità è supportata, verranno fornite altre istruzioni su come usare l'assegnazione dei criteri per raggruppare e aggiornare gli utenti per assicurarsi che vengano assegnati i criteri di gruppo ereditati.</span><span class="sxs-lookup"><span data-stu-id="3783d-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="3783d-161">**Non si ha familiarità con PowerShell per Teams. Dove è possibile ottenere altre informazioni?**</span><span class="sxs-lookup"><span data-stu-id="3783d-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="3783d-162">Vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3783d-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3783d-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3783d-163">Related topics</span></span>

- [<span data-ttu-id="3783d-164">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="3783d-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="3783d-165">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="3783d-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="3783d-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="3783d-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="3783d-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="3783d-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
