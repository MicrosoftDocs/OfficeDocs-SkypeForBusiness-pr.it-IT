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
ms.openlocfilehash: c590620048c92177236a67b1480c19e64ca21e02
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850168"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="55c46-103">Configurare i telefoni di aree comuni</span><span class="sxs-lookup"><span data-stu-id="55c46-103">Set up common area phones</span></span>
<span data-ttu-id="55c46-104">Un telefono di area comune (CAP) è in genere collocato in un'area come un atrio o un'altra area a disposizione di molte persone.</span><span class="sxs-lookup"><span data-stu-id="55c46-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="55c46-105">Ad esempio, un telefono nella reception, un citofono o un telefono per sala riunioni, i CAP vengono configurati come dispositivi anziché come utenti e si collegano automaticamente ad una rete.</span><span class="sxs-lookup"><span data-stu-id="55c46-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="55c46-106">Nei seguenti passaggi, ti aiuteremo a configurare un account per Sistema telefonico con piani tariffari in modo da poter distribuire questi tipi di telefoni nella tua azienda.</span><span class="sxs-lookup"><span data-stu-id="55c46-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="55c46-107">Prerequisiti per i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="55c46-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="55c46-108">La prima cosa che devi fare è confermare di aver fatto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="55c46-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="55c46-109">Acquistato la licenza per telefono di area comune e un piano tariffario.</span><span class="sxs-lookup"><span data-stu-id="55c46-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="55c46-110">Cercato e acquistato telefoni approvati (visualizza l'elenco [Qui](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="55c46-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
 - <span data-ttu-id="55c46-111">Aggiornato il firmware sui tuoi telefoni (vedi firmware supportato [in questo argomento](getting-phones-for-skype-for-business-online.md)).</span><span class="sxs-lookup"><span data-stu-id="55c46-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="55c46-112">Puoi controllare il firmware sul tuo telefono in questo modo:</span><span class="sxs-lookup"><span data-stu-id="55c46-112">You can check the firmware on you phone by doing this:</span></span>
    - <span data-ttu-id="55c46-113">**I telefoni Polycom VVX**: passare a **Impostazioni** > **stato** > **piattaforma** > **applicazione** > **principale**.</span><span class="sxs-lookup"><span data-stu-id="55c46-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="55c46-114">**Telefoni Yealink**: passare allo **stato** sullo schermo del telefono principale.</span><span class="sxs-lookup"><span data-stu-id="55c46-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="55c46-115">**Telefoni AudioCodes**: passare al **Menu** > **Stato dispositivo** > **versione del Firmware** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="55c46-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    - <span data-ttu-id="55c46-116">**Telefoni Lync Phone Edition (LPE)**: passare al **Menu** > **System Information** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="55c46-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="55c46-117">Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="55c46-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="55c46-118">Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="55c46-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="55c46-119">A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata.</span><span class="sxs-lookup"><span data-stu-id="55c46-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="55c46-120">È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e l'impostazione del parametro *EnableDeviceUpdate* `false`.</span><span class="sxs-lookup"><span data-stu-id="55c46-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="55c46-121">Impostazione di un telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="55c46-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="55c46-122">Dovrai seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="55c46-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="55c46-123">Passaggio 1: acquista le licenze</span><span class="sxs-lookup"><span data-stu-id="55c46-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="55c46-124">Nel centro di amministrazione di Office 365, vai a **Fatturazione** > **Servizi di acquisto**, e aggiungi **Altri piani**.</span><span class="sxs-lookup"><span data-stu-id="55c46-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="55c46-126">Clicca su **Telefono di area comune** > **Acquista ora** > sulla pagina di **Check-out** clicca su **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="55c46-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="55c46-127">Clicca per espandere **Abbonamenti aggiuntivi** e quindi clicca per acquistare un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="55c46-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="55c46-128">Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.</span><span class="sxs-lookup"><span data-stu-id="55c46-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="55c46-129">Non hai bisogno di una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="55c46-129">You don't need a Phone System license.</span></span> <span data-ttu-id="55c46-130">È inclusa con la licenza per il **Telefono di area comune.**</span><span class="sxs-lookup"><span data-stu-id="55c46-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="55c46-131">Per maggiori informazioni sulle licenze, vedi [Licenze aggiuntive per Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="55c46-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="55c46-132">Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze</span><span class="sxs-lookup"><span data-stu-id="55c46-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="55c46-133">Nel centro di amministrazione di Office 365, vai a **Utenti** > **Utenti attivi** > **Aggiungi un utente**.</span><span class="sxs-lookup"><span data-stu-id="55c46-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="55c46-134">Inserisci come **Nome utente** "Reception" per il nome e "Principale" per il cognome.</span><span class="sxs-lookup"><span data-stu-id="55c46-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="55c46-135">Inserisci un **Nome da visualizzare** se non si genera automaticamente uno come "Reception Principale".</span><span class="sxs-lookup"><span data-stu-id="55c46-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="55c46-136">Inserisci un **Nome utente** come "ReceptionPrincipale" o "IngressoPrincipale".</span><span class="sxs-lookup"><span data-stu-id="55c46-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="55c46-137">Per i telefoni delle aree comuni, è possibile impostare manualmente una password o avere la stessa password per tutti i telefoni delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="55c46-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="55c46-138">Inoltre, potresti deselezionare **Fai in modo che questo utente modifichi la password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="55c46-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="55c46-139">Aspetta!</span><span class="sxs-lookup"><span data-stu-id="55c46-139">WAIT!!</span></span> <span data-ttu-id="55c46-140">Non cliccare su **Aggiungere**!</span><span class="sxs-lookup"><span data-stu-id="55c46-140">Don't click **Add**!!</span></span> <span data-ttu-id="55c46-141">Ups, se hai cliccato su **Aggiungere** allora fai in questo modo: Centro di amministrazione di Office 365> **Utenti** > **Utenti attivi** e poi trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="55c46-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="55c46-142">Quindi, nella pagina delle proprietà dell'utente, clicca su **Licenze di prodotto** e poi su **Modificare**.</span><span class="sxs-lookup"><span data-stu-id="55c46-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="55c46-143">Sulla pagina delle **Licenze di prodotto**, abilita **Telefono di area comune** e scegli un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.</span><span class="sxs-lookup"><span data-stu-id="55c46-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="55c46-144">Se sei ancora lì, assegna le licenze a questo utente.</span><span class="sxs-lookup"><span data-stu-id="55c46-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="55c46-145">Nella stessa pagina, fai clic per espandere **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="55c46-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="55c46-146">Abilita quanto segue:</span><span class="sxs-lookup"><span data-stu-id="55c46-146">Turn on the following:</span></span>
    - <span data-ttu-id="55c46-147">Telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="55c46-147">Common Area Phone</span></span>
    - <span data-ttu-id="55c46-148">Quindi devi scegliere un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.</span><span class="sxs-lookup"><span data-stu-id="55c46-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

    <span data-ttu-id="55c46-149">L'assegnazione delle licenze apparirà così:</span><span class="sxs-lookup"><span data-stu-id="55c46-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="55c46-151">Per tua informazione, il piano 2 di Skype for Business è incluso con la licenza per il **Telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="55c46-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="55c46-152">Per maggiori dettagli, vedi [Aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="55c46-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="55c46-153">Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="55c46-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="55c46-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assegna un numero di telefono all'utente utilizzando il **Centro di amministrazione Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="55c46-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="55c46-155">Nell'interfaccia di amministrazione di Office 365 > **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="55c46-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="55c46-156">Nell' **Interfaccia di amministrazione Skype for Business** >  **Voce** > **Numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="55c46-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="55c46-157">Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.</span><span class="sxs-lookup"><span data-stu-id="55c46-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="55c46-158">Sulla pagina relativa all'**Assegnazione**, nella casella **Utente vocale** immetti il nome dell'utente che viene utilizzato per il telefono, quindi seleziona l'utente nel menù a tendina **Seleziona un utente vocale**.</span><span class="sxs-lookup"><span data-stu-id="55c46-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="55c46-159">Mentre sei lì, dovrai aggiungere un indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="55c46-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="55c46-160">Una volta effettuata la ricerca, controlla **Seleziona l'indirizzo di emergenza** e scegli quello giusto per te.</span><span class="sxs-lookup"><span data-stu-id="55c46-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="55c46-161">Clicca su **Salvare** e il tuo utente dovrebbe apparire così:</span><span class="sxs-lookup"><span data-stu-id="55c46-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="55c46-163">Gli utenti verranno visualizzati solo se vi è stata applicata una licenza di **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="55c46-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="55c46-164">Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55c46-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="55c46-165">Per ulteriori informazioni, vedi [Ottenere numeri di telefono per i tuoi utenti](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="55c46-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="55c46-166">Nel cado te lo stessi chiedendo, puoi anche prendere il tuo numero di telefono che hai con un altro operatore e "*portarlo*"o trasferirlo su Office 365.</span><span class="sxs-lookup"><span data-stu-id="55c46-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="55c46-167">Vedere, [trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="55c46-167">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="55c46-168">Passaggio 4: configurazione del telefono</span><span class="sxs-lookup"><span data-stu-id="55c46-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="55c46-169">**Impostazione della modalità su un telefono**</span><span class="sxs-lookup"><span data-stu-id="55c46-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="55c46-170">Il telefono o i telefoni in dotazione devono avere la modalità **Telefono di area comune** attiva.</span><span class="sxs-lookup"><span data-stu-id="55c46-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="55c46-171">Si prega di controllare per assicurarsi che sia attiva.</span><span class="sxs-lookup"><span data-stu-id="55c46-171">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="55c46-172">**Ecco un esempio su come configurare un telefono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="55c46-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="55c46-173">Abilita la modalità Telefono di area comune per Polycom VVX seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="55c46-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="55c46-174">Nel browser, collegati all'interfaccia web in modo da poter abilitare la modalità CAP.</span><span class="sxs-lookup"><span data-stu-id="55c46-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="55c46-175">Quindi vai a **Impostazioni** e nell'opzione **Impostazioni Skype for Business**, seleziona **Telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="55c46-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="55c46-176">Clicca su **OK** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="55c46-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="55c46-177">Ora che la modalità CAP è abilitata, configura il telefono utilizzando il suo schermo.</span><span class="sxs-lookup"><span data-stu-id="55c46-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="55c46-178">Lo schermo dovrebbe visualizzare **CaAP è abilitato**.</span><span class="sxs-lookup"><span data-stu-id="55c46-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="55c46-179">Procedi nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="55c46-179">Then do the following:</span></span>

    1. <span data-ttu-id="55c46-180">Clicca su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="55c46-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="55c46-181">Seleziona **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="55c46-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="55c46-182">Inserisci la password.</span><span class="sxs-lookup"><span data-stu-id="55c46-182">Enter the password.</span></span>
    4. <span data-ttu-id="55c46-183">Su **Impostazioni di amministrazione**seleziona **Impostazioni del telefono di area comune**.</span><span class="sxs-lookup"><span data-stu-id="55c46-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="55c46-184">Abilita **CAP** e **Modalità di amministrazione CAP**.</span><span class="sxs-lookup"><span data-stu-id="55c46-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="55c46-185">Clicca su **Salva config**.</span><span class="sxs-lookup"><span data-stu-id="55c46-185">Click **Save Config**.</span></span>

- <span data-ttu-id="55c46-186">Ok, ora il tuo telefono è pronto per poter accedere alla schermata principale.</span><span class="sxs-lookup"><span data-stu-id="55c46-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="55c46-187">Accedi selezionando **Impostazioni** > **Caratteristiche** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="55c46-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="55c46-188">Seleziona **Credenziali dell'utente**e **accesso Web (CAP)** per generare un codice.</span><span class="sxs-lookup"><span data-stu-id="55c46-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="55c46-189">Vai al [portale di provisioning](https://aka.ms/skypecap)e accedi come **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="55c46-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="55c46-190">Immetti il nome visualizzato (ad esempio, Reception Principale).</span><span class="sxs-lookup"><span data-stu-id="55c46-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="55c46-191">Se **Cerca solo telefoni di area comune** è spuntato, deseleziona la casella di controllo e cerca di nuovo.</span><span class="sxs-lookup"><span data-stu-id="55c46-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="55c46-192">Nella finestra del codice di accoppiamento, inserisci il codice visualizzato sul telefono e clicca su **Fornitura**.</span><span class="sxs-lookup"><span data-stu-id="55c46-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="55c46-193">Dopo questo ultimo passaggio, il telefono dovrebbe accedere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55c46-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="55c46-194">Il sito di provisioning CAP afferma che ripristinerà la password dell'account CAP ad una password casuale.</span><span class="sxs-lookup"><span data-stu-id="55c46-194">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="55c46-195">Prendere nota che l'account a cui fa riferimento il CAP è l'account Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="55c46-195">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="55c46-196">Se hai creato l'account solo in AAD, la procedura è semplice.</span><span class="sxs-lookup"><span data-stu-id="55c46-196">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="55c46-197">Se hai sincronizzato un Active Directory locale con AAD, assicurati di prendere nota delle credenziali che stai utilizzando che verranno modificate dal provisioning CAP.</span><span class="sxs-lookup"><span data-stu-id="55c46-197">If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="55c46-198">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="55c46-198">Related topics</span></span>

- <span data-ttu-id="55c46-199">Trovi ulteriori informazioni sui telefoni disponibili su [Distribuzione di telefoni Skype for Business online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="55c46-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="55c46-200">Ottenere telefoni per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="55c46-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


