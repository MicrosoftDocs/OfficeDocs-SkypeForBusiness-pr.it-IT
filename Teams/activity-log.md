---
title: Visualizzare le assegnazioni dei criteri nel registro attività nell'interfaccia di amministrazione di Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel registro attività nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350080"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="8318b-103">Visualizzare le assegnazioni dei criteri nel registro attività</span><span class="sxs-lookup"><span data-stu-id="8318b-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="8318b-104">Quando si assegnano criteri agli utenti nell'interfaccia di amministrazione di Microsoft teams, è possibile visualizzare lo stato di tali assegnazioni dei criteri nel registro attività.</span><span class="sxs-lookup"><span data-stu-id="8318b-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="8318b-105">Il registro attività Mostra le assegnazioni dei criteri ai batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="8318b-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="8318b-106">Tieni presente che il log attività non Mostra le assegnazioni dei pacchetti di criteri, le assegnazioni di criteri ai batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams o le assegnazioni di criteri tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8318b-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Screenshot della pagina del log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="8318b-108">Visualizzare le attività di assegnazione dei criteri nel registro attività</span><span class="sxs-lookup"><span data-stu-id="8318b-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="8318b-109">Per visualizzare le assegnazioni dei criteri nel registro attività:</span><span class="sxs-lookup"><span data-stu-id="8318b-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="8318b-110">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard**e quindi in **Registro attività**Selezionare **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8318b-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="8318b-111">È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni **non avviate**, **in corso**o **completate**.</span><span class="sxs-lookup"><span data-stu-id="8318b-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="8318b-112">Verranno visualizzate le informazioni seguenti su ogni assegnazione:</span><span class="sxs-lookup"><span data-stu-id="8318b-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="8318b-113">**Name**: nome dell'assegnazione di criteri.</span><span class="sxs-lookup"><span data-stu-id="8318b-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="8318b-114">Fare clic sul collegamento per visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="8318b-114">Click the link to view more details.</span></span> <span data-ttu-id="8318b-115">Include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non avviate.</span><span class="sxs-lookup"><span data-stu-id="8318b-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="8318b-116">Vedrai anche l'elenco degli utenti nel batch e lo stato e il risultato per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="8318b-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="8318b-117">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="8318b-117">Here's an example:</span></span>

        ![Screenshot della](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="8318b-119">**Inviato**: data e ora in cui è stata inviata l'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="8318b-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="8318b-120">**Ora di completamento**: data e ora l'assegnazione dei criteri è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8318b-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="8318b-121">**Impatto su**: numero di utenti nel batch.</span><span class="sxs-lookup"><span data-stu-id="8318b-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="8318b-122">**Stato complessivo**: stato dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="8318b-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="8318b-123">È anche possibile accedere al log attività dalla pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="8318b-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="8318b-124">Dopo aver fatto clic su **applica** per inviare un'assegnazione di criteri di massa, viene visualizzato un banner nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="8318b-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="8318b-125">Fare clic sul collegamento del **log attività** nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8318b-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8318b-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8318b-126">Related topics</span></span>

- [<span data-ttu-id="8318b-127">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="8318b-127">Assign policies to users</span></span>](assign-policies.md)
