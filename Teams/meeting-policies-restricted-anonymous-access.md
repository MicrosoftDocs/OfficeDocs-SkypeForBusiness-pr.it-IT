---
title: Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Informazioni su come rimuovere i criteri di riunione di RestrictedAnonymousAccess teams dagli utenti dell'organizzazione.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806256"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="7e9bd-103">Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="7e9bd-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="7e9bd-104">I [criteri di riunione](meeting-policies-in-teams.md) in Microsoft teams vengono usati per controllare le caratteristiche disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="7e9bd-105">Teams include un criterio predefinito denominato RestrictedAnonymousAccess, che contiene impostazioni predefinite che includono la restrizione degli utenti anonimi all'avvio di una riunione.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="7e9bd-106">Gli utenti anonimi sono utenti che non sono stati autenticati. Le impostazioni predefinite nel criterio della riunione non possono essere modificate o modificate dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="7e9bd-107">Questo articolo illustra come usare PowerShell per rimuovere i criteri della riunione RestrictedAnonymousAccess dagli utenti a cui è stato assegnato questo criterio.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="7e9bd-108">Per altre informazioni su come gestire i team tramite PowerShell, vedere [Panoramica di PowerShell per Team](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="7e9bd-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7e9bd-109">Before you start</span></span>

<span data-ttu-id="7e9bd-110">Installare e connettersi al [modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="7e9bd-111">Per informazioni dettagliate, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="7e9bd-112">Ottenere le assegnazioni dei criteri per le riunioni dei team per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7e9bd-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="7e9bd-113">Eseguire la procedura seguente per ottenere le assegnazioni dei criteri per le riunioni dei team per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="7e9bd-114">In questo esempio viene restituito l'output seguente, che indica che a due utenti sono assegnati i criteri per le riunioni di RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="7e9bd-115">Annullare l'assegnazione del criterio della riunione RestrictedAnonymous dagli utenti</span><span class="sxs-lookup"><span data-stu-id="7e9bd-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="7e9bd-116">Per rimuovere i criteri della riunione RestrictedAnonymous dagli utenti, è possibile usare il cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se si dispone di un numero limitato di utenti (ad esempio, meno di 100 utenti).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="7e9bd-117">Se si ha un numero elevato di utenti, ad esempio più di 100 utenti, è più efficiente usare il cmdlet  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) per inviare un'operazione batch.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="7e9bd-118">Usare il cmdlet Policy Grant-CsTeamsMeeting</span><span class="sxs-lookup"><span data-stu-id="7e9bd-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="7e9bd-119">Eseguire la procedura seguente per rimuovere i criteri della riunione RestrictedAnonymous dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="7e9bd-120">Usare il cmdlet New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="7e9bd-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="7e9bd-121">Con l' [assegnazione dei criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users), il numero massimo di utenti per cui è possibile rimuovere o aggiornare i criteri è 5.000 alla volta.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="7e9bd-122">Ad esempio, se si hanno più di 5.000 utenti, è necessario inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="7e9bd-123">Per ottenere risultati ottimali, non inviare più batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="7e9bd-124">Consentire ai batch di completare l'elaborazione prima di inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="7e9bd-125">Il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) è nel modulo di PowerShell teams.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="7e9bd-126">Prima di eseguire questa procedura, installare e connettersi al [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="7e9bd-127">Per informazioni dettagliate, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="7e9bd-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="7e9bd-128">Eseguire i comandi seguenti per rimuovere i criteri della riunione RestrictedAnonymousAccess da un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="7e9bd-129">Ottenere lo stato dell'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="7e9bd-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="7e9bd-130">Ogni assegnazione batch restituisce un ID operazione, che è possibile usare per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni e identificare gli eventuali errori che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="7e9bd-131">Ad esempio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e9bd-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="7e9bd-132">Verificare che **ErrorCount** sia **0** (zero) e che **OverallStatus** sia **completato**.</span><span class="sxs-lookup"><span data-stu-id="7e9bd-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e9bd-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7e9bd-133">Related topics</span></span>

- [<span data-ttu-id="7e9bd-134">Gestire i criteri di riunione in Teams</span><span class="sxs-lookup"><span data-stu-id="7e9bd-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="7e9bd-135">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="7e9bd-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="7e9bd-136">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="7e9bd-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
