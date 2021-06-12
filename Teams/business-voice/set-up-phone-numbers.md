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
ms.openlocfilehash: 89cb3764e30fa0bf4fcfa9d6a18d29ca69786cef
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910038"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="05c3d-103">Passaggio 2: Configurare i numeri di telefono di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="05c3d-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="05c3d-104">Prima di configurare utenti o operatori automatici nell'organizzazione, è necessario ottenere i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="05c3d-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="05c3d-105">Esistono diversi tipi di numeri di telefono, tuttavia i due tipi di numeri da aggiungere in questo passaggio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="05c3d-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="05c3d-106">**Numeri di servizio** Questi numeri vengono usati per operatori automatici, audioconferenze e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="05c3d-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="05c3d-107">Possono essere numeri a pagamento o a pagamento e possono gestire grandi quantità di chiamate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="05c3d-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="05c3d-108">Il numero di telefono dell'azienda deve essere un numero di servizio perché verrà assegnato a un operatore automatico in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="05c3d-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="05c3d-109">**Numeri di abbonato** Questi numeri vengono usati per gli utenti normali in modo che possano effettuare e ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="05c3d-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05c3d-110">Anche se si vogliono usare i numeri di telefono esistenti, è necessario creare e assegnare numeri di telefono temporanei alla linea telefonica principale dell'azienda e agli utenti.</span><span class="sxs-lookup"><span data-stu-id="05c3d-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="05c3d-111">Sarà possibile sostituire questi numeri temporanei con i numeri di telefono esistenti in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="05c3d-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="05c3d-112">Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="05c3d-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

<span data-ttu-id="05c3d-113">Il video seguente mostra come completare questi passaggi nell'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="05c3d-113">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWENzQ]

## <a name="set-up-a-service-number"></a><span data-ttu-id="05c3d-114">Configurare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="05c3d-114">Set up a service number</span></span>

<span data-ttu-id="05c3d-115">Il numero di servizio configurato ora verrà usato in un passaggio successivo per il numero di telefono principale dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="05c3d-115">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="05c3d-116">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="05c3d-116">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="05c3d-117">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-117">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="05c3d-118">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="05c3d-118">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="05c3d-119">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05c3d-119">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="05c3d-120">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="05c3d-120">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="05c3d-121">In **Tipo di numero** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05c3d-121">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="05c3d-122">**Operatore automatico (pedaggio)** Numero di telefono normale, senza numero verde.</span><span class="sxs-lookup"><span data-stu-id="05c3d-122">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="05c3d-123">Le tariffe interurbane vengono addebitate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="05c3d-123">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="05c3d-124">**Operatore automatico (numero verde)** Numero verde (Stati Uniti e Canada) o numero verde (Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="05c3d-124">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="05c3d-125">Le tariffe per le lunghe distanze vengono addebitate all'azienda.</span><span class="sxs-lookup"><span data-stu-id="05c3d-125">Long distances fees are charged to your company.</span></span> <span data-ttu-id="05c3d-126">Prima di selezionare questa opzione, è necessario acquistare Crediti comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="05c3d-126">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="05c3d-127">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="05c3d-127">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="05c3d-128">In **Quantità** selezionare **1.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-128">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="05c3d-129">Se viene visualizzato il messaggio Non si hanno licenze **sufficienti** per richiedere più numeri di questo tipo, assicurarsi di aver acquistato le licenze di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="05c3d-129">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="05c3d-130">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="05c3d-130">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="05c3d-131">Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.</span><span class="sxs-lookup"><span data-stu-id="05c3d-131">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="05c3d-132">Se si seleziona **Posizione**:</span><span class="sxs-lookup"><span data-stu-id="05c3d-132">If you select **Location**:</span></span>

        1. <span data-ttu-id="05c3d-133">Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-133">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="05c3d-134">In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="05c3d-134">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="05c3d-135">Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="05c3d-135">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="05c3d-136">Selezionare il numero desiderato.</span><span class="sxs-lookup"><span data-stu-id="05c3d-136">Select the number you want.</span></span> <span data-ttu-id="05c3d-137">Hai 10 minuti per selezionare il tuo numero di telefono e inserire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="05c3d-137">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="05c3d-138">Se si prendono più di 10 minuti, il numero di telefono verrà restituito al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="05c3d-138">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="05c3d-139">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine**</span><span class="sxs-lookup"><span data-stu-id="05c3d-139">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="05c3d-140">Configurare i numeri di telefono per gli utenti</span><span class="sxs-lookup"><span data-stu-id="05c3d-140">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="05c3d-141">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="05c3d-141">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="05c3d-142">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-142">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="05c3d-143">Immettere un nome per l'ordine e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="05c3d-143">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="05c3d-144">Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05c3d-144">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="05c3d-145">In **Paese o area geografica** selezionare un paese o un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="05c3d-145">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="05c3d-146">In **Tipo di numero** selezionare Utente **(abbonato)**.</span><span class="sxs-lookup"><span data-stu-id="05c3d-146">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="05c3d-147">In **Quantità** immettere il numero di numeri desiderato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05c3d-147">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="05c3d-148">Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.</span><span class="sxs-lookup"><span data-stu-id="05c3d-148">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="05c3d-149">Se si seleziona **Posizione**:</span><span class="sxs-lookup"><span data-stu-id="05c3d-149">If you select **Location**:</span></span>

        1. <span data-ttu-id="05c3d-150">Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-150">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="05c3d-151">In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="05c3d-151">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="05c3d-152">Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.</span><span class="sxs-lookup"><span data-stu-id="05c3d-152">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="05c3d-153">Selezionare i numeri desiderati.</span><span class="sxs-lookup"><span data-stu-id="05c3d-153">Select the numbers you want.</span></span> <span data-ttu-id="05c3d-154">Hai 10 minuti per selezionare i numeri di telefono e eseguire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="05c3d-154">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="05c3d-155">Se si prendono più di 10 minuti, i numeri di telefono verranno restituiti al pool di numeri.</span><span class="sxs-lookup"><span data-stu-id="05c3d-155">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="05c3d-156">Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="05c3d-156">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05c3d-157">Passaggio successivo: Assegnare licenze agli Teams utenti</span><span class="sxs-lookup"><span data-stu-id="05c3d-157">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
