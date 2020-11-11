---
title: Configurare le festività in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: Informazioni su come configurare le festività in Microsoft teams per l'uso con gli operatori automatici.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993472"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="ae966-103">Configurare le festività in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae966-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="ae966-104">È possibile usare la caratteristica teams Holidays per inviare messaggi alternativi e routing ai chiamanti per date e ore specifiche quando i reparti, le code di chiamata o le persone dell'organizzazione seguiranno diverse ore lavorative o non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="ae966-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="ae966-105">Ad esempio, potresti creare una festività per il giorno del nuovo anno in cui l'organizzazione potrebbe essere chiusa.</span><span class="sxs-lookup"><span data-stu-id="ae966-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="ae966-106">Le festività create in questo articolo sono disponibili quando si [configura un operatore automatico](create-a-phone-system-auto-attendant.md), ognuno con le proprie impostazioni di saluto e di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ae966-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="ae966-107">Creare una festività</span><span class="sxs-lookup"><span data-stu-id="ae966-107">Create a holiday</span></span>

<span data-ttu-id="ae966-108">Per creare una festività</span><span class="sxs-lookup"><span data-stu-id="ae966-108">To create a holiday</span></span>

1. <span data-ttu-id="ae966-109">Nell'interfaccia di amministrazione di Microsoft teams, vai a vacanze **impostazioni a livello di organizzazione**  >  **Holidays**.</span><span class="sxs-lookup"><span data-stu-id="ae966-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="ae966-110">Selezionare **nuova festività**.</span><span class="sxs-lookup"><span data-stu-id="ae966-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="ae966-111">Immettere un nome per la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="ae966-112">Selezionare **Aggiungi nuova data**.</span><span class="sxs-lookup"><span data-stu-id="ae966-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="ae966-113">In **ora inizio** selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="ae966-114">Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="ae966-115">In **fine ora** selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="ae966-116">Usare l'elenco a discesa per selezionare un'ora di fine per la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="ae966-117">L' **ora di fine** deve essere successiva all' **ora di inizio**.</span><span class="sxs-lookup"><span data-stu-id="ae966-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="ae966-118">Se la festività è per un giorno intero (ad esempio un periodo di 24 ore), l' **ora di fine** deve essere impostata sul giorno successivo e sull'ora di 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="ae966-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="ae966-119">Ad esempio, se l'organizzazione è chiusa il 1 ° gennaio per il giorno del nuovo anno, impostare l' **ora di inizio** su gennaio 1 12:00 AM e impostare l' **ora di fine** del 2 gennaio @ 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="ae966-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="ae966-120">Facoltativamente, aggiungere altre date per le festività periodiche.</span><span class="sxs-lookup"><span data-stu-id="ae966-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="ae966-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae966-121">Select **Save**.</span></span>

    ![Screenshot dell'interfaccia utente per le festività con date configurate per tre anni](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="ae966-123">Modificare una festività</span><span class="sxs-lookup"><span data-stu-id="ae966-123">Change a holiday</span></span>

<span data-ttu-id="ae966-124">Per modificare una festività</span><span class="sxs-lookup"><span data-stu-id="ae966-124">To change a holiday</span></span>

1. <span data-ttu-id="ae966-125">Nell'interfaccia di amministrazione di Microsoft teams, vai a vacanze **impostazioni a livello di organizzazione**  >  **Holidays**.</span><span class="sxs-lookup"><span data-stu-id="ae966-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="ae966-126">Selezionare la festività nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ae966-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="ae966-127">In **ora inizio** selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="ae966-128">Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="ae966-129">In **fine ora** selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="ae966-130">Usare l'elenco a discesa per selezionare un'ora di fine per la festività.</span><span class="sxs-lookup"><span data-stu-id="ae966-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="ae966-131">L' **ora di fine** deve essere successiva all' **ora di inizio**.</span><span class="sxs-lookup"><span data-stu-id="ae966-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="ae966-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae966-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae966-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ae966-133">Related topics</span></span>

<span data-ttu-id="ae966-134">[Pianificare gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md)?</span><span class="sxs-lookup"><span data-stu-id="ae966-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
