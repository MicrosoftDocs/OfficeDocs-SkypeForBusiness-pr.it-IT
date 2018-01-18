---
title: Impostare le tariffe di chiamate
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: 'Informazioni su come ottenere i numeri di telefono in Office 365, la chiamata piano (chiamata PSTN plan) acquistare e configurare le licenze, aggiungere e assegnare posizioni di emergenza e numeri di telefono per gli utenti e chiedere agli utenti ai nuovi numeri di telefono. '
ms.openlocfilehash: a84a38aca60c196ac320b7c00a03a0f8f7fbaf36
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-calling-plans"></a><span data-ttu-id="23764-103">Impostare le tariffe di chiamate</span><span class="sxs-lookup"><span data-stu-id="23764-103">Set up Calling Plans</span></span>

<span data-ttu-id="23764-104">Le chiamate a altri Skype per gli utenti aziendali libero, ma se si desidera che gli utenti siano in grado di chiamare telefoni all'esterno dell'azienda, ottenere una nazionale chiamata pianificare oppure un International la chiamata in Office 365.</span><span class="sxs-lookup"><span data-stu-id="23764-104">Calls to other Skype for Business users are free, but if you want your users to be able to call phones outside of your business, get a Domestic Calling Plan or an International Calling Plan in Office 365.</span></span> <span data-ttu-id="23764-105">È facile per configurarla per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="23764-105">It's easy to set this up for your business.</span></span> 
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="23764-106">Passaggio 1: Acquistare e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="23764-106">Step 1: Buy and assign licenses</span></span>

1. <span data-ttu-id="23764-107">Se il sistema telefonico in funzionalità di Office 365 non è incluso nel piano di, potrebbe essere necessario acquistare licenze di componente aggiuntivo di **Sistema telefonico** .</span><span class="sxs-lookup"><span data-stu-id="23764-107">If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="23764-108">Dopo avere licenze **Sistema telefonico** , acquistare [La chiamata dei piani di Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="23764-108">After you have **Phone System** licenses, purchase [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span></span> <span data-ttu-id="23764-109">Vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e acquistare le licenze e piano.</span><span class="sxs-lookup"><span data-stu-id="23764-109">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="23764-110">**Sistema telefonico in** licenze e la chiamata dei piani di Office 365 accedere contemporaneamente, in modo per verificare la possibilità di acquistare tariffe di chiamate, è necessario innanzitutto avere licenze **Sistema telefonico** .</span><span class="sxs-lookup"><span data-stu-id="23764-110">**Phone System** licenses and Calling Plans in Office 365 go together, so to see the option to purchase Calling Plans, you must first have the **Phone System** licenses.</span></span>
  
2. <span data-ttu-id="23764-111">In primo luogo assegnare le licenze e quindi assegnare un piano di chiamata per gli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23764-111">First assign the licenses, and then assign a Calling Plan to the people in your organization.</span></span> <span data-ttu-id="23764-112">Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="23764-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-get-phone-numbers"></a><span data-ttu-id="23764-113">Passaggio 2: Ottenere i numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="23764-113">Step 2: Get phone numbers</span></span>

<span data-ttu-id="23764-114">Se si è di fuori degli Stati Uniti, l'ordine delle operazioni modifica leggermente.</span><span class="sxs-lookup"><span data-stu-id="23764-114">If you're outside of the United States, the order of steps changes slightly.</span></span> <span data-ttu-id="23764-115">Ciò avviene perché in alcuni paesi, si riceve un indirizzo emergenza con il numero di telefono che ottiene da Office 365 o il numero di telefono che si trasferisce.</span><span class="sxs-lookup"><span data-stu-id="23764-115">This is because in some countries/regions, you get an emergency address with the phone number that you get from Office 365 or the phone number you transfer.</span></span> <span data-ttu-id="23764-116">Pertanto, se si è di fuori degli Stati Uniti, innanzitutto eseguire [passaggio 3: aggiungere gli indirizzi di emergenza e percorsi per l'organizzazione](set-up-calling-plans.md#bkmk_add_addresses)e quindi eseguire **passaggio 2: ottenere i numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="23764-116">So, if you are outside of the United States, first do [Step 3: Add emergency addresses and locations for your organization](set-up-calling-plans.md#bkmk_add_addresses), and then do **Step 2: Get phone numbers**.</span></span>
  
1. <span data-ttu-id="23764-117">Se si utilizza numeri di telefono da Office 365, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="23764-117">If you are using phone numbers from Office 365, follow these steps.</span></span> <span data-ttu-id="23764-118">**Se si desidera trasferire i numeri di telefono esistente da un altro provider di servizi, eseguire la procedura in [numeri di telefono di trasferimento a Office 365](transfer-phone-numbers-to-office-365.md)**.</span><span class="sxs-lookup"><span data-stu-id="23764-118">**If you need to transfer existing phone numbers from another service provider, follow the steps in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md)**.</span></span>
    
2. <span data-ttu-id="23764-119">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="23764-119">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="23764-120">Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende >** **vocale**.</span><span class="sxs-lookup"><span data-stu-id="23764-120">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >** **Voice**.</span></span>

    > [!IMPORTANT] 
    > <span data-ttu-id="23764-121">Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="23764-121">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
   
4. <span data-ttu-id="23764-122">Scegliere **i numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="23764-122">Choose **Phone numbers**.</span></span> <span data-ttu-id="23764-123">Verrà visualizzato il numero di licenze **Sistema telefonico** è necessario avere un'idea come molte per richiedere i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="23764-123">You'll see how many **Phone System** licenses you have, to give you an idea how many phone numbers to request.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="23764-124">È possibile acquisire più numeri di telefono che si dispone di licenza.</span><span class="sxs-lookup"><span data-stu-id="23764-124">You can acquire more phone numbers than you have licenses for.</span></span> <span data-ttu-id="23764-125">Per determinare quanti numeri di telefono, è possibile acquisire, eseguire il numero di licenze, aggiungere il 10% del numero di licenze e quindi aggiungere 10.</span><span class="sxs-lookup"><span data-stu-id="23764-125">To determine how many phone numbers you can acquire, take your number of licenses, add 10 percent of the number of licenses, and then add 10.</span></span> <span data-ttu-id="23764-126">Ad esempio, se è stato acquistato 100 licenze, possono essere numeri di telefono di 120.</span><span class="sxs-lookup"><span data-stu-id="23764-126">For example, if you have purchased 100 licenses, you can acquire 120 phone numbers.</span></span> <span data-ttu-id="23764-127">Vedere [quanti numeri trovare?](how-many-phone-numbers-can-you-get.md)</span><span class="sxs-lookup"><span data-stu-id="23764-127">See [How many numbers can I get?](how-many-phone-numbers-can-you-get.md)</span></span> 
  
5. <span data-ttu-id="23764-128">Scegliere **Aggiungi nuovo numero** > **nuovi numeri utente**, nella pagina **Aggiungi nuovo utente i numeri di** scegliere il paese/area geografica, paese e città che si desidera selezionare numeri compresi tra.</span><span class="sxs-lookup"><span data-stu-id="23764-128">Choose **Add new number** > **New user numbers**, and on the **Add new user numbers** page, choose the country/region, state/region, and city that you want to select numbers from.</span></span>
    
6.  <span data-ttu-id="23764-129">In **quantità**, immettere il numero di numeri di telefono che si desidera utilizzare per l'organizzazione da quest ' area e fare clic su **Aggiungi** per creare un tipo di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="23764-129">Under **Quantity**, enter the number of phone numbers that you want for your organization from this area, and click **Add** to create a reservation.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="23764-130">Si dispone di 10 minuti per selezionare i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="23764-130">You have 10 minutes to select your phone numbers.</span></span> <span data-ttu-id="23764-131">Dopo 10 minuti, i numeri di telefono vengono restituiti al pool dei numeri di telefono in Office 365.</span><span class="sxs-lookup"><span data-stu-id="23764-131">After 10 minutes, the phone numbers are returned to the pool of phone numbers at Office 365.</span></span> 
  
    <span data-ttu-id="23764-132">Nella figura riportata di seguito è evidente che i numeri di telefono sono state aggiunte per due diverse città, con 9 minuti per l'acquisizione di essi.</span><span class="sxs-lookup"><span data-stu-id="23764-132">In the following picture you can see that phone numbers have been added for two different cities, with 9 minutes left to acquire them.</span></span> 
    
     ![Specificare l'area in cui si desidera ottenere i numeri di pagina Aggiungi utente numeri.](../images/f6dc1ef3-0bf2-4b4f-b32c-ca27e69c5553.png)
  
7. <span data-ttu-id="23764-134">È possibile scegliere di **visualizzare i numeri** per visualizzare un elenco completo dei numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="23764-134">You can choose **Show numbers** to see the full list of phone numbers.</span></span> <span data-ttu-id="23764-135">Ciò è utile se non si desidera un numero di telefono specifico nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="23764-135">This is helpful if you don't want a specific phone number in the list.</span></span>
    
8. <span data-ttu-id="23764-136">Selezionare i numeri di telefono desiderato e quindi fare clic su **Acquisisci numeri**.</span><span class="sxs-lookup"><span data-stu-id="23764-136">Select the phone numbers you want, and then choose **Acquire numbers**.</span></span>
    
9. <span data-ttu-id="23764-137">Verrà tornare alla pagina **vocale** su cui verranno visualizzate tutti i numeri acquisito.</span><span class="sxs-lookup"><span data-stu-id="23764-137">You'll return to the **Voice** page, where you'll see all the numbers you acquired.</span></span>
    
    ![Dashboard vocale per visualizzare tutti i numeri di telefono che è stato acquistato.](../images/4a9c681c-13f9-4cdc-a25b-93eb00d06b6c.png)
  
## <a name="step-3-add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="23764-139">Passaggio 3: Aggiungere gli indirizzi di emergenza e percorsi per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="23764-139">Step 3: Add emergency addresses and locations for your organization</span></span>
<span data-ttu-id="23764-140"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="23764-140"></span></span>

1. <span data-ttu-id="23764-141">Nella pagina **Voice** scegliere **percorsi Emergency** > **Aggiungi nuovo indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="23764-141">On the **Voice** page, choose **Emergency locations** > **Add new address**.</span></span>
    
2. <span data-ttu-id="23764-142">Nel riquadro **nuovo indirizzo** immettere un nome per l'indirizzo e quindi completare le caselle rimanenti.</span><span class="sxs-lookup"><span data-stu-id="23764-142">In the **New address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>
    
     ![Quando si immette un nuovo indirizzo di emergenza, la formattazione del nome della via potrebbe causare un errore.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > <span data-ttu-id="23764-144">Per i clienti inglese, se il nome della via è un numero, assicurarsi di includere "standard" o "esima" alla fine, come illustrato nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="23764-144">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span> 
  
3. <span data-ttu-id="23764-145">Scegliere **convalida**.</span><span class="sxs-lookup"><span data-stu-id="23764-145">Choose **Validate**.</span></span>
    
    <span data-ttu-id="23764-146">Se necessario, verrà richiesto di apportare modifiche all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="23764-146">If needed, you'll be prompted to make corrections to the address.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="23764-147">Convalida un indirizzo civico o civico comporta assicurandosi che sia valido e formattato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="23764-147">Validating a street or civic address involves making sure that it is legitimate and correctly formatted.</span></span> <span data-ttu-id="23764-148">È possibile che un indirizzo di emergenza parzialmente corretto, ad esempio come se è stato digitato correttamente il nome della città, può superare comunque la convalida.</span><span class="sxs-lookup"><span data-stu-id="23764-148">It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation.</span></span> <span data-ttu-id="23764-149">Anche se è stato digitato correttamente e sono stati convalidati, la combinazione di nome errata di città con le altre parti corrette dell'indirizzo sono le informazioni necessarie per instradare la chiamata al centro di intervento di emergenza appropriato.</span><span class="sxs-lookup"><span data-stu-id="23764-149">Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="23764-150">Se è necessario che l'indirizzo di risposta di emergenza da correggere, verrà visualizzato un banner verde notificato che è stato aggiornato l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="23764-150">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span> 
  
4. <span data-ttu-id="23764-151">Dopo la convalida dell'indirizzo, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="23764-151">After the address is validated, choose **Save**.</span></span>
    
## <a name="step-4-assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="23764-152">Passaggio 4: Assegnare agli utenti i numeri di telefono e gli indirizzi di emergenza</span><span class="sxs-lookup"><span data-stu-id="23764-152">Step 4: Assign phone numbers and emergency addresses to users</span></span>
<span data-ttu-id="23764-153"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="23764-153"></span></span>

> [!TIP]
> <span data-ttu-id="23764-154">Se si aggiungono più persone a destra del business prima di eseguire questo passaggio, potrebbe richiedere **diverse ore** per essere visualizzate nella pagina **utenti VoIP** .</span><span class="sxs-lookup"><span data-stu-id="23764-154">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page.</span></span> <span data-ttu-id="23764-155">Esiste una latenza.</span><span class="sxs-lookup"><span data-stu-id="23764-155">There's a latency.</span></span>
  
1. <span data-ttu-id="23764-156">Nella pagina **utenti dei servizi vocali** , selezionare gli utenti che si desidera assegnare un numero di telefono e l'indirizzo di emergenza a.</span><span class="sxs-lookup"><span data-stu-id="23764-156">On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.</span></span>
    
2. <span data-ttu-id="23764-157">Nel riquadro azioni fare clic su **Assegna numero**.</span><span class="sxs-lookup"><span data-stu-id="23764-157">In the Action pane, click **Assign number**.</span></span>
    
3. <span data-ttu-id="23764-158">Nella pagina **assegnazione numero** nell'elenco **selezionare numero da assegnare** , selezionare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="23764-158">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>
    
4. <span data-ttu-id="23764-159">Per selezionare un indirizzo di emergenza, immettere nome della città nella casella e quindi scegliere **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="23764-159">To select an emergency address, enter name of the city in the box and choose **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="23764-160">Se si è fuori degli Stati Uniti, i numeri dispongono già di un indirizzo di emergenza, ma è possibile modificare questo punto.</span><span class="sxs-lookup"><span data-stu-id="23764-160">If you are outside the United States, your numbers already have an emergency address, but you can change it now.</span></span> <span data-ttu-id="23764-161">Vedere [assegnare o modificare un indirizzo di emergenza per un utente](assign-or-change-an-emergency-address-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="23764-161">See [Assign or change an emergency address for a user](assign-or-change-an-emergency-address-for-a-user.md).</span></span> 
  
5. <span data-ttu-id="23764-162">Dopo aver assegnato il numero di telefono e l'indirizzo di emergenza, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="23764-162">After you assign both the phone number and emergency address, choose **Save**.</span></span>
    
## <a name="step-5-tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="23764-163">Passaggio 5: Informare gli utenti ai nuovi numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="23764-163">Step 5: Tell your users about their new phone numbers</span></span>
<span data-ttu-id="23764-164"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="23764-164"></span></span>

<span data-ttu-id="23764-165">È consigliabile l'invio di posta elettronica o per informare gli utenti ai nuovi numeri di telefono, utilizzare il metodo di comunicazione preferito dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="23764-165">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span> 

<span data-ttu-id="23764-166">Ecco come è possibile visualizzare tale numero di telefono nel proprio app **Skype for Business** :</span><span class="sxs-lookup"><span data-stu-id="23764-166">Here's how they can see that phone number in their **Skype for Business** app:</span></span>
  
1. <span data-ttu-id="23764-167">Accedere a Skype per le aziende sul desktop.</span><span class="sxs-lookup"><span data-stu-id="23764-167">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="23764-168">Fare clic su **Impostazioni** > **Strumenti** > **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="23764-168">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     ![Per visualizzare il numero di telefono, passare a Impostazioni > Strumenti > Opzioni.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="23764-170">Scegliere **telefoni**.</span><span class="sxs-lookup"><span data-stu-id="23764-170">Then choose **Phones**.</span></span> 
    
    ![Possono essere visualizzate al numero di assegnazione in Skype per app Business scegliere Impostazioni > Strumenti > Opzioni > telefono.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="23764-172">In **Team Microsoft che**gli utenti possono visualizzare il numero di telefono fare clic sulle **chiamate** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="23764-172">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation.</span></span> <span data-ttu-id="23764-173">Il numero di telefono viene visualizzato sopra la tastiera.</span><span class="sxs-lookup"><span data-stu-id="23764-173">The phone number is shown above the dial pad.</span></span>

![Un utente può visualizzare il numero di Microsoft Teams facendo clic sulle chiamate nel riquadro di spostamento sinistro.](../images/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a><span data-ttu-id="23764-175">Altre informazioni è necessario conoscere?</span><span class="sxs-lookup"><span data-stu-id="23764-175">What else do you need to know?</span></span>
<span data-ttu-id="23764-176"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="23764-176"></span></span>

- <span data-ttu-id="23764-177">Un indirizzo di emergenza viene spesso come un indirizzo civico, numero civico o un indirizzo fisico.</span><span class="sxs-lookup"><span data-stu-id="23764-177">An emergency address is often referred to as a civic address, street address, or a physical address.</span></span> <span data-ttu-id="23764-178">È l'indirizzo civico o civico di una sede di attività per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23764-178">It is the street or civic address of a place of business for your organization.</span></span>
    
- <span data-ttu-id="23764-179">Solo gli indirizzi per gli interventi di emergenza sono convalidati, non le posizioni.</span><span class="sxs-lookup"><span data-stu-id="23764-179">Emergency locations aren't validated, only emergency addresses are.</span></span>
    
- <span data-ttu-id="23764-180">Se si desidera ottenere maggiori informazioni sugli indirizzi di emergenza, vedere [quali sono posizioni di emergenza, indirizzi e il routing delle chiamate?](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="23764-180">If you want to know more about emergency addresses, see [What are emergency locations, addresses and call routing?](what-are-emergency-locations-addresses-and-call-routing.md)</span></span>
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a><span data-ttu-id="23764-181">Si desidera automatizzare l'assegnazione dei numeri di telefono?</span><span class="sxs-lookup"><span data-stu-id="23764-181">Do you want to automate assigning phone numbers?</span></span>
<span data-ttu-id="23764-182"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="23764-182"></span></span>

<span data-ttu-id="23764-183">Se si è certi di Windows PowerShell, è possibile utilizzare i cmdlet seguenti per automatizzare l'assegnazione dei numeri di telefono per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="23764-183">If you know Windows PowerShell, you can use the following cmdlets to automate assigning phone numbers to your users.</span></span> 
  
- <span data-ttu-id="23764-184">[Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): consente di recuperare i numeri di telefono dalla Directory di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="23764-184">[Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): Retrieves the telephone numbers from the Business Voice Directory.</span></span>
    
- <span data-ttu-id="23764-185">[Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): imposta i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="23764-185">[Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): Sets the telephone numbers.</span></span>
    
<span data-ttu-id="23764-186">Per ulteriori informazioni, vedere [Guida di riferimento rapido: Using Windows PowerShell per eseguire Skype comuni per le attività di gestione in linea aziendale](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="23764-186">To learn more, see [Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).</span></span>
  
    > [!NOTE]
    > If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="23764-187">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="23764-187">Related topics</span></span>
[<span data-ttu-id="23764-188">Trasferimento di domande comuni numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="23764-188">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="23764-189">Diversi tipi di numeri di telefono utilizzati per la chiamata dei piani</span><span class="sxs-lookup"><span data-stu-id="23764-189">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="23764-190">Gestire i numeri di telefono per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="23764-190">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="23764-191">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="23764-191">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="23764-192">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="23764-192">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

