---
title: Visualizzare le assegnazioni dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821316"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="54ba2-103">Visualizzare le assegnazioni dei criteri nel log attività</span><span class="sxs-lookup"><span data-stu-id="54ba2-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="54ba2-104">Quando si assegnano criteri agli utenti nell'interfaccia di amministrazione di Microsoft Teams, è possibile visualizzare lo stato di tali assegnazioni nel log attività.</span><span class="sxs-lookup"><span data-stu-id="54ba2-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="54ba2-105">Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="54ba2-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="54ba2-106">Tenere presente che il log attività non mostra le assegnazioni dei pacchetti dei criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54ba2-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Screenshot della pagina Log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="54ba2-108">Visualizzare le attività di assegnazione dei criteri nel log attività</span><span class="sxs-lookup"><span data-stu-id="54ba2-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="54ba2-109">Per visualizzare le assegnazioni dei criteri nel log attività:</span><span class="sxs-lookup"><span data-stu-id="54ba2-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="54ba2-110">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Dashboard,** quindi in **Log** attività seleziona **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="54ba2-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="54ba2-111">È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni non **iniziate,** **in** corso o **completate.**</span><span class="sxs-lookup"><span data-stu-id="54ba2-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="54ba2-112">Verranno visualizzate le informazioni seguenti su ogni attività:</span><span class="sxs-lookup"><span data-stu-id="54ba2-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="54ba2-113">**Nome:** nome dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="54ba2-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="54ba2-114">Fare clic sul collegamento per visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="54ba2-114">Click the link to view more details.</span></span> <span data-ttu-id="54ba2-115">Questo include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non iniziate.</span><span class="sxs-lookup"><span data-stu-id="54ba2-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="54ba2-116">Verrà visualizzato anche l'elenco di utenti nel batch e lo stato e il risultato di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="54ba2-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="54ba2-117">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="54ba2-117">Here's an example:</span></span>

        ![Screenshot della](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="54ba2-119">**Inviato:** data e ora di invio dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="54ba2-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="54ba2-120">**Ora di completamento:** data e ora di completamento dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="54ba2-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="54ba2-121">**Impatto su:** numero di utenti nel batch.</span><span class="sxs-lookup"><span data-stu-id="54ba2-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="54ba2-122">**Stato generale:** stato dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="54ba2-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="54ba2-123">Puoi anche accedere al log attività dalla **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="54ba2-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="54ba2-124">Dopo aver fatto **clic su** Applica per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner.</span><span class="sxs-lookup"><span data-stu-id="54ba2-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="54ba2-125">Fai clic **sul collegamento Log** attività nel banner.</span><span class="sxs-lookup"><span data-stu-id="54ba2-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54ba2-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="54ba2-126">Related topics</span></span>

- [<span data-ttu-id="54ba2-127">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="54ba2-127">Assign policies to users</span></span>](assign-policies.md)
