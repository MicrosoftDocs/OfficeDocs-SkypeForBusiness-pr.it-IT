---
title: Impostare i telefoni delle aree comuni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="97bbf-103">Impostare i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="97bbf-103">Set up common area phones</span></span>
<span data-ttu-id="97bbf-104">Un telefono di area comune (CAP) solito si trova in un'area come una sala di attesa o un'altra area disponibili per molti utenti.</span><span class="sxs-lookup"><span data-stu-id="97bbf-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="97bbf-105">Ad esempio, un telefono di area di ricezione, porta telefono o sale riunioni telefono, estremità sono impostati come dispositivi piuttosto che gli utenti e Accedi automaticamente in una rete.</span><span class="sxs-lookup"><span data-stu-id="97bbf-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="97bbf-106">Nella procedura riportata di seguito, si verrà consentono di configurare un account per il sistema telefonico con la chiamata dei piani in modo che è possibile distribuire i tipi di telefoni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="97bbf-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="97bbf-107">Prerequisiti per i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="97bbf-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="97bbf-108">Come prima cosa che è necessario eseguire consiste nel verificare di disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97bbf-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="97bbf-109">Acquistare licenze di telefono di Area comune e un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="97bbf-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="97bbf-110">Cercare e acquistare telefoni approvati (consente di visualizzare l'elenco [di seguito](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="97bbf-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="97bbf-111">Aggiornare il firmware per i telefoni (vedere supportati del firmware [in questo argomento](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="97bbf-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="97bbf-112">In questo modo è possibile controllare il firmware del telefono:</span><span class="sxs-lookup"><span data-stu-id="97bbf-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="97bbf-113">**I telefoni Polycom VVX**: passare a **Impostazioni** > **stato** > **piattaforma** > **applicazione** > **principale**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="97bbf-114">**Telefoni Yealink**: passare allo **stato** sullo schermo del telefono principale.</span><span class="sxs-lookup"><span data-stu-id="97bbf-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="97bbf-115">**Telefoni AudioCodes**: passare al **Menu** > **Stato dispositivo** > **versione del Firmware** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="97bbf-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="97bbf-116">**Telefoni Lync Phone Edition (LPE)**: passare al **Menu** > **System Information** nella schermata start.</span><span class="sxs-lookup"><span data-stu-id="97bbf-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="97bbf-117">Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="97bbf-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="97bbf-118">Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="97bbf-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="97bbf-119">A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata.</span><span class="sxs-lookup"><span data-stu-id="97bbf-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="97bbf-120">È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e l'impostazione del parametro *EnableDeviceUpdate* `false`.</span><span class="sxs-lookup"><span data-stu-id="97bbf-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="97bbf-121">Impostazione di un telefono di Area comune</span><span class="sxs-lookup"><span data-stu-id="97bbf-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="97bbf-122">È necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="97bbf-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="97bbf-123">Configurazione dell'account utente per il telefono</span><span class="sxs-lookup"><span data-stu-id="97bbf-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="97bbf-124">Passaggio 1 - acquistare le licenze</span><span class="sxs-lookup"><span data-stu-id="97bbf-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="97bbf-125">Nell'interfaccia di amministrazione di Office 365, passare alla **fatturazione** > **servizi di acquisto**e aggiungere **altri piani**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP license.png](../../images/cap-license.png)
2. <span data-ttu-id="97bbf-127">Fare clic sul **Telefono di Area comune** > **Acquista** > al clic pagina **estrazione** su **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="97bbf-128">Fare clic su per espandere **le sottoscrizioni di componente aggiuntivo** e fare clic su acquistare un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="97bbf-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="97bbf-129">Scegliere il metodo **nazionale Plan la chiamata** o **chiamate nazionali e internazionali pianificare**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="97bbf-130">Non è necessario una licenza di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="97bbf-130">You don't need a Phone System license.</span></span> <span data-ttu-id="97bbf-131">Ha incluso con licenza di **Telefono di Area comune** .</span><span class="sxs-lookup"><span data-stu-id="97bbf-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="97bbf-132">Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="97bbf-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="97bbf-133">Passaggio 2: creare un nuovo account utente per il telefono e assegnare le licenze</span><span class="sxs-lookup"><span data-stu-id="97bbf-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="97bbf-134">Nell'interfaccia di amministrazione di Office 365 accedere agli **utenti** > **Utenti attivi** > **Add user**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="97bbf-135">Inserire un **nome utente** , ad esempio "Main" per il nome e "Ricezione" per il secondo nome.</span><span class="sxs-lookup"><span data-stu-id="97bbf-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="97bbf-136">Inserire un **nome visualizzato** in caso contrario genera automaticamente una like "Main ricezione".</span><span class="sxs-lookup"><span data-stu-id="97bbf-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="97bbf-137">Inserire un **nome utente** come "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="97bbf-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="97bbf-138">Per i telefoni delle aree comuni, è possibile impostare manualmente una password o avere la stessa password per tutti i telefoni delle aree comuni è.</span><span class="sxs-lookup"><span data-stu-id="97bbf-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="97bbf-139">Inoltre, si pensi su deselezionando la casella **che l'utente di modificare la password quando accedono prima**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="97bbf-140">ATTENDERE.</span><span class="sxs-lookup"><span data-stu-id="97bbf-140">WAIT!!</span></span> <span data-ttu-id="97bbf-141">Non fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-141">Don't click **Add**!!</span></span> <span data-ttu-id="97bbf-142">Ugh, se è fare clic su **Aggiungi** eseguire questo: interfaccia di amministrazione di Office 365 > **utenti** > **utenti attivi** e individuare l'utente.</span><span class="sxs-lookup"><span data-stu-id="97bbf-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="97bbf-143">Nella pagina proprietà dell'utente, fare clic su **licenze per i prodotti** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="97bbf-144">Nella pagina **licenze per i prodotti** , attivare il **Telefono di Area comune** e selezionare sia una **Chiamata a pianificare le** o nazionali e **Internazionali la chiamata a pianificare**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="97bbf-145">Se si è ancora presente, assegnare le licenze per l'utente.</span><span class="sxs-lookup"><span data-stu-id="97bbf-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="97bbf-146">Nella stessa pagina, fare clic per espandere **le licenze**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="97bbf-147">Attivare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97bbf-147">Turn on the following:</span></span>
    - <span data-ttu-id="97bbf-148">Telefono di Area comune</span><span class="sxs-lookup"><span data-stu-id="97bbf-148">Common Area Phone</span></span>
    - <span data-ttu-id="97bbf-149">È necessario selezionare sia una **Chiamata a pianificare le** o nazionali e **Internazionali la chiamata a pianificare**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="97bbf-150">Assegnazione di licenze sarà simile:</span><span class="sxs-lookup"><span data-stu-id="97bbf-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="97bbf-152">Solo in modo che si è certi, Skype per Business piano 2 è incluso con licenza di **Telefono di Area comune** .</span><span class="sxs-lookup"><span data-stu-id="97bbf-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="97bbf-153">Per ulteriori informazioni, vedere [aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="97bbf-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="97bbf-154">Passaggio 3: assegnare un numero di telefono all'utente</span><span class="sxs-lookup"><span data-stu-id="97bbf-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="97bbf-155">![30x30.png di logo sfb](../../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="97bbf-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="97bbf-156">Nell'interfaccia di amministrazione di Office 365 > **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="97bbf-157">In **Skype per Business admin center** >  **vocale** > **i numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="97bbf-158">Selezionare un numero dall'elenco dei numeri di telefono, quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="97bbf-159">Nella pagina **assegnazione** nella casella **vocale utente** immettere il nome dell'utente utilizzato per il telefono, quindi selezionare l'utente di **Selezionare un utente voce di** menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="97bbf-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="97bbf-160">Ci sarà necessario aggiungere un indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="97bbf-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="97bbf-161">Una volta che la ricerca, cercare nella casella **Selezionare l'indirizzo di emergenza** per selezionare quella corretta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="97bbf-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="97bbf-162">Fare clic su **Salva** e l'utente deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="97bbf-162">Click **Save** and your user should look like this:</span></span>

    ![number.png di utente CAP](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="97bbf-164">Gli utenti verranno visualizzati solo se dispongono di una licenza di **Sistema telefonico** applicata.</span><span class="sxs-lookup"><span data-stu-id="97bbf-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="97bbf-165">Se è stato appena questo, quindi talvolta necessario un po' per l'utente possa essere visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="97bbf-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="97bbf-166">Per ulteriori informazioni, vedere [Getting i numeri di telefono per gli utenti](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="97bbf-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="97bbf-167">Se si desidera sapere per, è possibile eseguire anche il numero di telefono con un altro gestore di telefonia e "*porta*" o trasferiti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="97bbf-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="97bbf-168">Vedere, [trasferire i numeri di telefono a Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="97bbf-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="97bbf-169">Passaggio 4: configurazione del telefono</span><span class="sxs-lookup"><span data-stu-id="97bbf-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="97bbf-170">**Impostazione della modalità di un telefono**</span><span class="sxs-lookup"><span data-stu-id="97bbf-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="97bbf-171">Il telefono o si dispone di telefoni devono disporre attivata la modalità di telefono di Area comune.</span><span class="sxs-lookup"><span data-stu-id="97bbf-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="97bbf-172">È possibile verificare che per assicurarsi che sono analoghi.</span><span class="sxs-lookup"><span data-stu-id="97bbf-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="97bbf-173">**Di seguito è riportato un esempio di come impostare un telefono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="97bbf-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="97bbf-174">Abilitare la modalità di telefono di Area comune per VVX Polycom eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="97bbf-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="97bbf-175">Nel browser, connettersi all'interfaccia web in modo che è possibile abilitare mode Capolettera.</span><span class="sxs-lookup"><span data-stu-id="97bbf-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="97bbf-176">Quindi passare **all'impostazione** e nell'opzione **Skype per impostazione Business** , selezionare **Telefono di Area comune**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="97bbf-177">Fare clic su **Sì** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="97bbf-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="97bbf-178">Ora che la modalità CAP è attivata, impostare il telefono con display del telefono.</span><span class="sxs-lookup"><span data-stu-id="97bbf-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="97bbf-179">La visualizzazione dovrebbe essere visualizzato **CaAP è abilitata**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="97bbf-180">Quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97bbf-180">Then do the following:</span></span>

    1. <span data-ttu-id="97bbf-181">Fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="97bbf-182">Selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="97bbf-183">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="97bbf-183">Enter the password.</span></span>
    4. <span data-ttu-id="97bbf-184">In **impostazioni di amministrazione**, selezionare **Impostazioni del telefono Area comune**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="97bbf-185">Abilitare la **modalità di amministrazione CAP**e **semplice** .</span><span class="sxs-lookup"><span data-stu-id="97bbf-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="97bbf-186">Fare clic su **Salva file Config**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-186">Click **Save Config**.</span></span>

- <span data-ttu-id="97bbf-187">In realtà, il telefono è pronto in modo che è possibile accedere nella schermata principale.</span><span class="sxs-lookup"><span data-stu-id="97bbf-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="97bbf-188">Accedere selezionando **Impostazioni** > **funzionalità** > **Skype per le aziende.**</span><span class="sxs-lookup"><span data-stu-id="97bbf-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="97bbf-189">Selezionare **Le credenziali utente**e selezionare **sign-in web (CAP)** per generare un codice.</span><span class="sxs-lookup"><span data-stu-id="97bbf-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="97bbf-190">Accedere al [portale di provisioning](http://aka.ms/skypecap)e accedere come **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="97bbf-191">Immettere il nome visualizzato (ad esempio, ricezione principale).</span><span class="sxs-lookup"><span data-stu-id="97bbf-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="97bbf-192">Se viene controllato **cercare solo i telefoni delle aree comuni** , deselezionare la casella di controllo e ripetere la ricerca. "</span><span class="sxs-lookup"><span data-stu-id="97bbf-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="97bbf-193">Nella finestra codice abbinamento, immettere il codice visualizzato sul telefono e fare clic su **per il provisioning**.</span><span class="sxs-lookup"><span data-stu-id="97bbf-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="97bbf-194">In seguito quest'ultimo passaggio, il telefono deve accedere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="97bbf-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="97bbf-195">See also</span><span class="sxs-lookup"><span data-stu-id="97bbf-195">Related topics</span></span>

- <span data-ttu-id="97bbf-196">Ulteriori informazioni sui telefoni disponibili nella [Distribuzione Skype per i telefoni aziendali in linea](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="97bbf-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="97bbf-197">Ottenere telefoni per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="97bbf-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


