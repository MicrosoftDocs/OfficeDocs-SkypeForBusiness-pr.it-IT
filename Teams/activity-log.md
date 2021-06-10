---
title: Visualizzare le assegnazioni dei criteri nel log attività nell'Microsoft Teams di amministrazione
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel log attività nell'Microsoft Teams di amministrazione.
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
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="0a53f-103">Visualizzare le assegnazioni dei criteri nel log attività</span><span class="sxs-lookup"><span data-stu-id="0a53f-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="0a53f-104">Quando si assegnano criteri agli utenti nell Microsoft Teams di amministrazione, è possibile visualizzare lo stato di tali assegnazioni di criteri nel log attività.</span><span class="sxs-lookup"><span data-stu-id="0a53f-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="0a53f-105">Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'Microsoft Teams di amministrazione degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0a53f-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="0a53f-106">Tenere presente che il log attività non mostra le assegnazioni dei pacchetti di criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a53f-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Screenshot della pagina Log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="0a53f-108">Visualizzare le attività di assegnazione dei criteri nel log attività</span><span class="sxs-lookup"><span data-stu-id="0a53f-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="0a53f-109">Per visualizzare le assegnazioni dei criteri nel log attività:</span><span class="sxs-lookup"><span data-stu-id="0a53f-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="0a53f-110">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Dashboard** e quindi in **Log attività** selezionare **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="0a53f-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="0a53f-111">È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni non **avviate,** **in** corso o **completate.**</span><span class="sxs-lookup"><span data-stu-id="0a53f-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="0a53f-112">Verranno visualizzate le informazioni seguenti su ogni attività:</span><span class="sxs-lookup"><span data-stu-id="0a53f-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="0a53f-113">**Nome:** nome dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0a53f-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="0a53f-114">Fare clic sul collegamento per visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="0a53f-114">Click the link to view more details.</span></span> <span data-ttu-id="0a53f-115">Include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non avviate.</span><span class="sxs-lookup"><span data-stu-id="0a53f-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="0a53f-116">Verranno visualizzati anche l'elenco degli utenti nel batch e lo stato e il risultato per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="0a53f-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="0a53f-117">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="0a53f-117">Here's an example:</span></span>

        ![Screenshot del pulsante](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="0a53f-119">**Inviato:** data e ora di invio dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0a53f-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="0a53f-120">**Ora di completamento:** data e ora di completamento dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0a53f-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="0a53f-121">**Impatto su:** numero di utenti nel batch.</span><span class="sxs-lookup"><span data-stu-id="0a53f-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="0a53f-122">**Stato generale:** stato dell'assegnazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0a53f-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="0a53f-123">È anche possibile accedere al log attività dalla **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="0a53f-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="0a53f-124">Dopo aver fatto **clic su Applica** per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner.</span><span class="sxs-lookup"><span data-stu-id="0a53f-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="0a53f-125">Fare clic **sul collegamento Log** attività nel banner.</span><span class="sxs-lookup"><span data-stu-id="0a53f-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a53f-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0a53f-126">Related topics</span></span>

- [<span data-ttu-id="0a53f-127">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="0a53f-127">Assign policies to users</span></span>](assign-policies.md)
