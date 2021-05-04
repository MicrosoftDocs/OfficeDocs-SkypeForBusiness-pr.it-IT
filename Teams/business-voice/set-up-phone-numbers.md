---
title: Configurare i Microsoft 365 Business Voice di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare i numeri Microsoft 365 Business Voice di telefono per gli utenti e i servizi dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130054"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="084ff-103">Passaggio 2: Configurare i numeri di telefono di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="084ff-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="084ff-104">Prima di configurare utenti o operatori automatici nell'organizzazione, è necessario ottenere i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="084ff-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="084ff-105">Esistono diversi tipi di numeri di telefono, tuttavia i due tipi di numeri da aggiungere in questo passaggio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ff-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="084ff-106">**Numeri di servizio** Questi numeri vengono usati per operatori automatici, audioconferenze e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="084ff-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="084ff-107">Possono essere numeri a pagamento o a pagamento e possono gestire grandi quantità di chiamate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="084ff-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="084ff-108">Il numero di telefono dell'azienda deve essere un numero di servizio perché verrà assegnato a un operatore automatico in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="084ff-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="084ff-109">**Numeri di abbonato** Questi numeri vengono usati per gli utenti normali in modo che possano effettuare e ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="084ff-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="084ff-110">Anche se si vogliono usare i numeri di telefono esistenti, è necessario creare e assegnare numeri di telefono temporanei alla linea telefonica principale dell'azienda e agli utenti.</span><span class="sxs-lookup"><span data-stu-id="084ff-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="084ff-111">Sarà possibile sostituire questi numeri temporanei con i numeri di telefono esistenti in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="084ff-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="084ff-112">Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="084ff-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="084ff-113">Configurare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="084ff-113">Set up a service number</span></span>

<span data-ttu-id="084ff-114">Il numero di servizio configurato ora verrà usato in un passaggio successivo per il numero di telefono principale dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="084ff-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="084ff-115">Passare all'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="084ff-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="084ff-116">Nel riquadro di spostamento sinistro passare a **Numeri**  >  **Telefono** vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="084ff-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="084ff-117">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="084ff-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="084ff-118">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ff-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="084ff-119">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="084ff-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="084ff-120">In **Tipo di numero** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ff-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="084ff-121">**Operatore automatico (pedaggio)** Numero di telefono normale, senza numero verde.</span><span class="sxs-lookup"><span data-stu-id="084ff-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="084ff-122">Le tariffe interurbane vengono addebitate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="084ff-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="084ff-123">**Operatore automatico (numero verde)** Numero verde (Stati Uniti e Canada) o numero verde (Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="084ff-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="084ff-124">Le tariffe per le lunghe distanze vengono addebitate all'azienda.</span><span class="sxs-lookup"><span data-stu-id="084ff-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="084ff-125">Prima di selezionare questa opzione, è necessario acquistare Crediti comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="084ff-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="084ff-126">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="084ff-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="084ff-127">In **Quantità** selezionare **1.**</span><span class="sxs-lookup"><span data-stu-id="084ff-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="084ff-128">Se viene visualizzato il messaggio Non si hanno licenze **sufficienti** per richiedere più numeri di questo tipo, assicurarsi di aver acquistato le licenze di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="084ff-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="084ff-129">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="084ff-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="084ff-130">In **Posizione** digitare il nome della posizione creata nel [passaggio Configurare le posizioni per gli interventi di](set-up-emergency-locations.md) emergenza.</span><span class="sxs-lookup"><span data-stu-id="084ff-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="084ff-131">In **Codice area** selezionare un codice area e quindi fare clic su **Avanti** per selezionare i numeri</span><span class="sxs-lookup"><span data-stu-id="084ff-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="084ff-132">Selezionare il numero desiderato.</span><span class="sxs-lookup"><span data-stu-id="084ff-132">Select the number you want.</span></span> <span data-ttu-id="084ff-133">Hai 10 minuti per selezionare il tuo numero di telefono e inserire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="084ff-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="084ff-134">Se si prendono più di 10 minuti, il numero di telefono verrà restituito al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="084ff-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="084ff-135">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine**</span><span class="sxs-lookup"><span data-stu-id="084ff-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="084ff-136">Configurare i numeri di telefono per gli utenti</span><span class="sxs-lookup"><span data-stu-id="084ff-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="084ff-137">Passare all'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="084ff-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="084ff-138">Nel riquadro di spostamento sinistro passare a **Numeri**  >  **Telefono** vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="084ff-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="084ff-139">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="084ff-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="084ff-140">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ff-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="084ff-141">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="084ff-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="084ff-142">In **Tipo di numero** selezionare Utente **(abbonato)**.</span><span class="sxs-lookup"><span data-stu-id="084ff-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="084ff-143">In **Quantità** immettere il numero di numeri desiderato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="084ff-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="084ff-144">In **Posizione** selezionare una posizione.</span><span class="sxs-lookup"><span data-stu-id="084ff-144">Under **Location**, select a location.</span></span> <span data-ttu-id="084ff-145">È possibile selezionare la posizione per [](set-up-emergency-locations.md) gli interventi di emergenza aggiunta nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un ufficio domestico, fare clic su Aggiungi **una posizione.**</span><span class="sxs-lookup"><span data-stu-id="084ff-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="084ff-146">In **Codice area** selezionare un codice area e quindi fare clic su **Avanti** per selezionare i numeri.</span><span class="sxs-lookup"><span data-stu-id="084ff-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="084ff-147">Selezionare i numeri desiderati.</span><span class="sxs-lookup"><span data-stu-id="084ff-147">Select the numbers you want.</span></span> <span data-ttu-id="084ff-148">Hai 10 minuti per selezionare i numeri di telefono e eseguire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="084ff-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="084ff-149">Se si prendono più di 10 minuti, i numeri di telefono verranno restituiti al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="084ff-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="084ff-150">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="084ff-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="084ff-151">Passaggio successivo: Assegnare licenze agli Teams utenti</span><span class="sxs-lookup"><span data-stu-id="084ff-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
