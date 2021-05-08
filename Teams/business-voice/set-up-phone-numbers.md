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
ms.openlocfilehash: 7dcf582593cf09977f4992d6b78035a9726c12b8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282543"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="c91a2-103">Passaggio 2: Configurare i numeri di telefono di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="c91a2-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="c91a2-104">Prima di configurare utenti o operatori automatici nell'organizzazione, è necessario ottenere i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="c91a2-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="c91a2-105">Esistono diversi tipi di numeri di telefono, tuttavia i due tipi di numeri da aggiungere in questo passaggio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c91a2-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="c91a2-106">**Numeri di servizio** Questi numeri vengono usati per operatori automatici, audioconferenze e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c91a2-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="c91a2-107">Possono essere numeri a pagamento o a pagamento e possono gestire grandi quantità di chiamate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c91a2-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="c91a2-108">Il numero di telefono dell'azienda deve essere un numero di servizio perché verrà assegnato a un operatore automatico in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c91a2-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="c91a2-109">**Numeri di abbonato** Questi numeri vengono usati per gli utenti normali in modo che possano effettuare e ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="c91a2-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c91a2-110">Anche se si vogliono usare i numeri di telefono esistenti, è necessario creare e assegnare numeri di telefono temporanei alla linea telefonica principale dell'azienda e agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c91a2-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="c91a2-111">Sarà possibile sostituire questi numeri temporanei con i numeri di telefono esistenti in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c91a2-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="c91a2-112">Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="c91a2-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="c91a2-113">Configurare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="c91a2-113">Set up a service number</span></span>

<span data-ttu-id="c91a2-114">Il numero di servizio configurato ora verrà usato in un passaggio successivo per il numero di telefono principale dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="c91a2-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="c91a2-115">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="c91a2-115">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="c91a2-116">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-116">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="c91a2-117">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="c91a2-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="c91a2-118">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c91a2-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="c91a2-119">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="c91a2-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="c91a2-120">In **Tipo di numero** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c91a2-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="c91a2-121">**Operatore automatico (pedaggio)** Numero di telefono normale, senza numero verde.</span><span class="sxs-lookup"><span data-stu-id="c91a2-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="c91a2-122">Le tariffe interurbane vengono addebitate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="c91a2-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="c91a2-123">**Operatore automatico (numero verde)** Numero verde (Stati Uniti e Canada) o numero verde (Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="c91a2-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="c91a2-124">Le tariffe per le lunghe distanze vengono addebitate all'azienda.</span><span class="sxs-lookup"><span data-stu-id="c91a2-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="c91a2-125">Prima di selezionare questa opzione, è necessario acquistare Crediti comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="c91a2-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="c91a2-126">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="c91a2-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="c91a2-127">In **Quantità** selezionare **1.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="c91a2-128">Se viene visualizzato il messaggio Non si hanno licenze **sufficienti** per richiedere più numeri di questo tipo, assicurarsi di aver acquistato le licenze di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c91a2-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="c91a2-129">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="c91a2-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="c91a2-130">Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.</span><span class="sxs-lookup"><span data-stu-id="c91a2-130">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="c91a2-131">Se si seleziona **Posizione**:</span><span class="sxs-lookup"><span data-stu-id="c91a2-131">If you select **Location**:</span></span>

        1. <span data-ttu-id="c91a2-132">Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-132">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="c91a2-133">In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="c91a2-133">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="c91a2-134">Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="c91a2-134">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="c91a2-135">Selezionare il numero desiderato.</span><span class="sxs-lookup"><span data-stu-id="c91a2-135">Select the number you want.</span></span> <span data-ttu-id="c91a2-136">Hai 10 minuti per selezionare il tuo numero di telefono e inserire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="c91a2-136">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="c91a2-137">Se si prendono più di 10 minuti, il numero di telefono verrà restituito al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="c91a2-137">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="c91a2-138">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine**</span><span class="sxs-lookup"><span data-stu-id="c91a2-138">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="c91a2-139">Configurare i numeri di telefono per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c91a2-139">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="c91a2-140">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="c91a2-140">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="c91a2-141">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-141">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="c91a2-142">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="c91a2-142">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="c91a2-143">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c91a2-143">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="c91a2-144">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="c91a2-144">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="c91a2-145">In **Tipo di numero** selezionare Utente **(abbonato)**.</span><span class="sxs-lookup"><span data-stu-id="c91a2-145">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="c91a2-146">In **Quantità** immettere il numero di numeri desiderato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c91a2-146">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="c91a2-147">Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.</span><span class="sxs-lookup"><span data-stu-id="c91a2-147">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="c91a2-148">Se si seleziona **Posizione**:</span><span class="sxs-lookup"><span data-stu-id="c91a2-148">If you select **Location**:</span></span>

        1. <span data-ttu-id="c91a2-149">Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-149">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="c91a2-150">In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="c91a2-150">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="c91a2-151">Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="c91a2-151">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="c91a2-152">Selezionare i numeri desiderati.</span><span class="sxs-lookup"><span data-stu-id="c91a2-152">Select the numbers you want.</span></span> <span data-ttu-id="c91a2-153">Hai 10 minuti per selezionare i numeri di telefono e eseguire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="c91a2-153">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="c91a2-154">Se si prendono più di 10 minuti, i numeri di telefono verranno restituiti al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="c91a2-154">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="c91a2-155">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="c91a2-155">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c91a2-156">Passaggio successivo: Assegnare licenze agli Teams utenti</span><span class="sxs-lookup"><span data-stu-id="c91a2-156">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
