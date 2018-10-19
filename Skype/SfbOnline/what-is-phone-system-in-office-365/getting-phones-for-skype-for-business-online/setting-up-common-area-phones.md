---
title: Configurare i telefoni di aree comuni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.openlocfilehash: b92cef4234823c53faf6193d2e9e90fe3e5b60f0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678167"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="068b9-103">Configurare i telefoni di aree comuni</span><span class="sxs-lookup"><span data-stu-id="068b9-103">Set up common area phones</span></span>
<span data-ttu-id="068b9-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="068b9-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="068b9-107">Prerequisiti per i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="068b9-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="068b9-108">La prima cosa che devi fare è confermare di aver fatto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="068b9-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="068b9-109">Acquistato la licenza per telefono di area comune e un piano tariffario.</span><span class="sxs-lookup"><span data-stu-id="068b9-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="068b9-110">Cercato e acquistato telefoni approvati (visualizza l'elenco [Qui](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="068b9-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="068b9-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="068b9-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="068b9-113">**I telefoni Polycom VVX**: passare a **Impostazioni** > **stato** > **piattaforma** > **applicazione** > **principale**.</span><span class="sxs-lookup"><span data-stu-id="068b9-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="068b9-114">**Telefoni Yealink**: passare allo **stato** sullo schermo del telefono principale.</span><span class="sxs-lookup"><span data-stu-id="068b9-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="068b9-115">**Telefoni AudioCodes**: passare al **Menu** > **Stato dispositivo** > **versione del Firmware** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="068b9-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="068b9-116">**Telefoni Lync Phone Edition (LPE)**: passare al **Menu** > **System Information** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="068b9-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="068b9-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="068b9-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="068b9-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="068b9-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="068b9-121">Impostazione di un telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="068b9-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="068b9-122">Dovrai seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="068b9-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="068b9-123">Passaggio 1: acquista le licenze</span><span class="sxs-lookup"><span data-stu-id="068b9-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="068b9-124">Nel centro di amministrazione di Office 365, vai a **Fatturazione** > **Servizi di acquisto**, e aggiungi **Altri piani**.</span><span class="sxs-lookup"><span data-stu-id="068b9-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="068b9-126">Clicca su **Telefono di area comune** > **Acquista ora** > sulla pagina di **Check-out** clicca su **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="068b9-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="068b9-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="068b9-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="068b9-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="068b9-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="068b9-131">Per maggiori informazioni sulle licenze, vedi [Licenze aggiuntive per Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="068b9-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="068b9-132">Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze</span><span class="sxs-lookup"><span data-stu-id="068b9-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="068b9-133">Nel centro di amministrazione di Office 365, vai a **Utenti** > **Utenti attivi** > **Aggiungi un utente**.</span><span class="sxs-lookup"><span data-stu-id="068b9-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="068b9-134">Inserisci come **Nome utente** "Reception" per il nome e "Principale" per il cognome.</span><span class="sxs-lookup"><span data-stu-id="068b9-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="068b9-135">Inserisci un **Nome da visualizzare** se non si genera automaticamente uno come "Reception Principale".</span><span class="sxs-lookup"><span data-stu-id="068b9-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="068b9-136">Inserisci un **Nome utente** come "ReceptionPrincipale" o "IngressoPrincipale".</span><span class="sxs-lookup"><span data-stu-id="068b9-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="068b9-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="068b9-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="068b9-139">Se sei ancora lì, assegna le licenze a questo utente.</span><span class="sxs-lookup"><span data-stu-id="068b9-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="068b9-140">Nella stessa pagina, fai clic per espandere **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="068b9-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="068b9-141">Abilita quanto segue:</span><span class="sxs-lookup"><span data-stu-id="068b9-141">Turn on the following:</span></span>
   - <span data-ttu-id="068b9-142">Telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="068b9-142">Common Area Phone</span></span>
   - <span data-ttu-id="068b9-143">Quindi devi scegliere un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.</span><span class="sxs-lookup"><span data-stu-id="068b9-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="068b9-144">L'assegnazione delle licenze apparirà così:</span><span class="sxs-lookup"><span data-stu-id="068b9-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="068b9-146">Per tua informazione, il piano 2 di Skype for Business è incluso con la licenza per il **Telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="068b9-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="068b9-147">Per maggiori dettagli, vedi [Aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="068b9-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="068b9-148">Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="068b9-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="068b9-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assegna un numero di telefono all'utente utilizzando il **Centro di amministrazione Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="068b9-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="068b9-150">Nell'interfaccia di amministrazione di Office 365 > **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="068b9-150">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="068b9-151">Nell' **Interfaccia di amministrazione Skype for Business** >  **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="068b9-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="068b9-152">Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.</span><span class="sxs-lookup"><span data-stu-id="068b9-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="068b9-153">Sulla pagina relativa all'**Assegnazione**, nella casella **Utente vocale** immetti il nome dell'utente che viene utilizzato per il telefono, quindi seleziona l'utente nel menù a tendina **Seleziona un utente vocale**.</span><span class="sxs-lookup"><span data-stu-id="068b9-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="068b9-154">Mentre sei lì, dovrai aggiungere un indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="068b9-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="068b9-155">Una volta effettuata la ricerca, controlla **Seleziona l'indirizzo di emergenza** e scegli quello giusto per te.</span><span class="sxs-lookup"><span data-stu-id="068b9-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="068b9-156">Clicca su **Salvare** e il tuo utente dovrebbe apparire così:</span><span class="sxs-lookup"><span data-stu-id="068b9-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="068b9-158">Gli utenti verranno visualizzati solo se vi è stata applicata una licenza di **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="068b9-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="068b9-159">Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="068b9-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="068b9-160">Per ulteriori informazioni, vedi [Ottenere numeri di telefono per i tuoi utenti](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="068b9-160">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="068b9-161">Nel cado te lo stessi chiedendo, puoi anche prendere il tuo numero di telefono che hai con un altro operatore e "*portarlo*"o trasferirlo su Office 365.</span><span class="sxs-lookup"><span data-stu-id="068b9-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="068b9-162">Vedere, [trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="068b9-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="068b9-163">Passaggio 4: configurazione del telefono</span><span class="sxs-lookup"><span data-stu-id="068b9-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="068b9-164">**Impostazione della modalità su un telefono**</span><span class="sxs-lookup"><span data-stu-id="068b9-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="068b9-165">Il telefono o i telefoni in dotazione devono avere la modalità **Telefono di area comune** attiva.</span><span class="sxs-lookup"><span data-stu-id="068b9-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="068b9-166">Si prega di controllare per assicurarsi che sia attiva.</span><span class="sxs-lookup"><span data-stu-id="068b9-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="068b9-167">**Ecco un esempio su come configurare un telefono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="068b9-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="068b9-168">Abilita la modalità Telefono di area comune per Polycom VVX seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="068b9-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="068b9-169">Nel browser, collegati all'interfaccia web in modo da poter abilitare la modalità CAP.</span><span class="sxs-lookup"><span data-stu-id="068b9-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="068b9-170">Quindi vai a **Impostazioni** e nell'opzione **Impostazioni Skype for Business**, seleziona **Telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="068b9-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="068b9-171">Clicca su **OK** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="068b9-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="068b9-172">Ora che la modalità CAP è abilitata, configura il telefono utilizzando il suo schermo.</span><span class="sxs-lookup"><span data-stu-id="068b9-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="068b9-173">Lo schermo dovrebbe visualizzare **CaAP è abilitato**.</span><span class="sxs-lookup"><span data-stu-id="068b9-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="068b9-174">Procedi nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="068b9-174">Then do the following:</span></span>

    1. <span data-ttu-id="068b9-175">Clicca su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="068b9-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="068b9-176">Seleziona **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="068b9-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="068b9-177">Inserisci la password.</span><span class="sxs-lookup"><span data-stu-id="068b9-177">Enter the password.</span></span>
    4. <span data-ttu-id="068b9-178">Su **Impostazioni di amministrazione**seleziona **Impostazioni del telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="068b9-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="068b9-179">Abilita **CAP** e **Modalità di amministrazione CAP**.</span><span class="sxs-lookup"><span data-stu-id="068b9-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="068b9-180">Clicca su **Salva config**.</span><span class="sxs-lookup"><span data-stu-id="068b9-180">Click **Save Config**.</span></span>

- <span data-ttu-id="068b9-181">Ok, ora il tuo telefono è pronto per poter accedere alla schermata principale.</span><span class="sxs-lookup"><span data-stu-id="068b9-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="068b9-182">Accedi selezionando **Impostazioni** > **Caratteristiche** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="068b9-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="068b9-183">Seleziona **Credenziali dell'utente**e **accesso Web (CAP)** per generare un codice.</span><span class="sxs-lookup"><span data-stu-id="068b9-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="068b9-184">Vai al [portale di provisioning](https://aka.ms/skypecap)e accedi come **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="068b9-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="068b9-185">Immetti il nome visualizzato (ad esempio, Reception Principale).</span><span class="sxs-lookup"><span data-stu-id="068b9-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="068b9-186">Se **Cerca solo telefoni di area comune** è spuntato, deseleziona la casella di controllo e cerca di nuovo.</span><span class="sxs-lookup"><span data-stu-id="068b9-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="068b9-187">Nella finestra del codice di accoppiamento, inserisci il codice visualizzato sul telefono e clicca su **Fornitura**.</span><span class="sxs-lookup"><span data-stu-id="068b9-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="068b9-188">Dopo questo ultimo passaggio, il telefono dovrebbe accedere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="068b9-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="068b9-189">Il sito di provisioning CAP afferma che ripristinerà la password dell'account CAP ad una password casuale.</span><span class="sxs-lookup"><span data-stu-id="068b9-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="068b9-190">Prendere nota che l'account a cui fa riferimento il CAP è l'account Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="068b9-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="068b9-191">Se hai creato l'account solo in AAD, la procedura è semplice.</span><span class="sxs-lookup"><span data-stu-id="068b9-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="068b9-192">Se si sincronizza un locale in Active Directory per AAD e si utilizza un IDP di terze parti o ADFS, il provisioning di tipo CAP non riesce.</span><span class="sxs-lookup"><span data-stu-id="068b9-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="068b9-193">In questo caso, è necessario utilizzare un Office 365/Azure solo account di Active Directory (ad esempio, un account con dominio **onmicrosoft.com** ) per limitare il provisioning per funzionare.</span><span class="sxs-lookup"><span data-stu-id="068b9-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="068b9-194">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="068b9-194">Related topics</span></span>

- <span data-ttu-id="068b9-195">Trovi ulteriori informazioni sui telefoni disponibili su [Distribuzione di telefoni Skype for Business online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="068b9-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="068b9-196">Ottenere telefoni per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="068b9-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


