---
title: Impostare i telefoni delle aree comuni
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
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
- Strat_SB_PSTN
ms.openlocfilehash: 12ed7d5c24649903f7cd3020d66ee4e9fcb77b6f
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="9edca-103">Impostare i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="9edca-103">Set up Common Area Phones</span></span>

<span data-ttu-id="9edca-104">Un telefono di area comune o maiuscola, è in genere in un'area condivisa e non associato a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="9edca-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="9edca-105">Ad esempio, un telefono di area di ricezione, porta telefono o sale riunioni telefono, estremità sono impostati come dispositivi piuttosto che gli utenti ed eseguito automaticamente l'accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="9edca-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="9edca-106">Nella procedura seguente è sarà consentono di configurare un account per il sistema telefonico Microsoft con la chiamata dei piani e quindi distribuire un Capolettera.</span><span class="sxs-lookup"><span data-stu-id="9edca-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="9edca-107">Prerequisiti per i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="9edca-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="9edca-108">Verificare di disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9edca-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="9edca-109">Acquistato Common Area Phone SKU</span><span class="sxs-lookup"><span data-stu-id="9edca-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="9edca-110">Firmware aggiornato (vedere supportati Firmware nell'argomentohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="9edca-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="9edca-111">Telefoni approvati (consente di visualizzare l'elenco nellahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="9edca-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 

## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="9edca-112">Verificare il firmware per il telefono</span><span class="sxs-lookup"><span data-stu-id="9edca-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="9edca-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="9edca-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="9edca-114">i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.</span><span class="sxs-lookup"><span data-stu-id="9edca-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="9edca-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="9edca-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="9edca-116">I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="9edca-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="9edca-117">Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="9edca-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="9edca-118">Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9edca-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="9edca-119">A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata.</span><span class="sxs-lookup"><span data-stu-id="9edca-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="9edca-120">È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e l'impostazione del parametro _EnableDeviceUpdate_ `false`.</span><span class="sxs-lookup"><span data-stu-id="9edca-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="9edca-121">Creare remoto</span><span class="sxs-lookup"><span data-stu-id="9edca-121">Create CAP</span></span>
<span data-ttu-id="9edca-122">Per creare la Terminazione, configurare le impostazioni prima di impostare l'apparecchio telefonico.</span><span class="sxs-lookup"><span data-stu-id="9edca-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="9edca-123">Il telefono Area comune SKU di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9edca-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="9edca-124">Impostare il telefono area comune<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="9edca-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="9edca-125">**Creare utente**</span><span class="sxs-lookup"><span data-stu-id="9edca-125">**Create user**</span></span> 
1. <span data-ttu-id="9edca-126">Assegnare Common Area Phone SKU</span><span class="sxs-lookup"><span data-stu-id="9edca-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="9edca-127">Assegnare la chiamata a pianificare (se si utilizza Microsoft Phone System con la chiamata dei piani).</span><span class="sxs-lookup"><span data-stu-id="9edca-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="9edca-128">Assegna un numero di telefono disponibili in Skype per Business Admin Center o richiedere un nuovo numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9edca-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="9edca-129">**Crea nuovo utente**</span><span class="sxs-lookup"><span data-stu-id="9edca-129">**Create New User**</span></span>

1. <span data-ttu-id="9edca-130">Nel riquadro di provisioning si ha la possibilità di immettere un nome e cognome (ad esempio, ricezione principale).</span><span class="sxs-lookup"><span data-stu-id="9edca-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="9edca-131">Immettere un nome visualizzato (obbligatorio), ad esempio, "ricezione Main".</span><span class="sxs-lookup"><span data-stu-id="9edca-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="9edca-132">Immettere un nome utente (obbligatorio), ad esempio "MainReception" @"domain" (nome della società o dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="9edca-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="9edca-133">Immettere il percorso (paese).</span><span class="sxs-lookup"><span data-stu-id="9edca-133">Enter Location (country).</span></span>

<span data-ttu-id="9edca-134">**Assegnare Common Area Phone SKU** Nell'interfaccia di amministrazione di Office 365 andare a **fatturazione > servizi di acquisto** e aggiungere **Telefono di Area comune**</span><span class="sxs-lookup"><span data-stu-id="9edca-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="9edca-135">**Assegnare Plan chiamate nelle SKU CAP**</span><span class="sxs-lookup"><span data-stu-id="9edca-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="9edca-136">Selezionare una chiamata prevede di abilitare il telefono.</span><span class="sxs-lookup"><span data-stu-id="9edca-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="9edca-137">Aggiungere la Terminazione per abilitare il sistema telefonico e Skype per Business Online piano 2 in SKU Capolettera.</span><span class="sxs-lookup"><span data-stu-id="9edca-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="9edca-138">**Assegnare un numero di telefono**</span><span class="sxs-lookup"><span data-stu-id="9edca-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="9edca-139">Controllare i numeri di telefono disponibili in **vocali > numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="9edca-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="9edca-140">Selezionare un numero dall'elenco disponibile i numeri del numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9edca-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="9edca-141">Conferma selezioni selezionando **vocali** e **I numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="9edca-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="9edca-142">[Nota] Gli utenti vocali vengono visualizzate solo se dispongono della licenza di sistema telefonico applicata, anche se anche dopo aver applicato, potrebbe richiedere tempo per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="9edca-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="9edca-143">Talvolta riapertura Skype per Business Admin center consente.</span><span class="sxs-lookup"><span data-stu-id="9edca-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="9edca-144">Configurare telefono</span><span class="sxs-lookup"><span data-stu-id="9edca-144">Configure Phone</span></span>

<span data-ttu-id="9edca-145">**Preparare i telefoni fisici**</span><span class="sxs-lookup"><span data-stu-id="9edca-145">**Prepare the physical phones**</span></span>

<span data-ttu-id="9edca-146">Il telefono scelto deve avere la modalità di telefono di Area comune.</span><span class="sxs-lookup"><span data-stu-id="9edca-146">Your chosen phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="9edca-147">***Telefono Polycom VVX di esempio***</span><span class="sxs-lookup"><span data-stu-id="9edca-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="9edca-148">Abilitare Common Area Phone modalità per VVX Polycom eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9edca-148">Enable Common Area Phone Mode for the Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="9edca-149">Nel browser, utilizzare l'interfaccia web per attivare la modalità di limitare il VVX</span><span class="sxs-lookup"><span data-stu-id="9edca-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="9edca-150">Passare **all'impostazione** e Skype per l'opzione Impostazioni Business, selezionare **Telefono di Area comune**.</span><span class="sxs-lookup"><span data-stu-id="9edca-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="9edca-151">Fare clic su **Sì** per salvare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9edca-151">Click **Yes** to save your configuration settings.</span></span>

<span data-ttu-id="9edca-152">Ora che la modalità telefonica CAP è attivata, impostare il telefono con display del telefono.</span><span class="sxs-lookup"><span data-stu-id="9edca-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="9edca-153">La visualizzazione dovrebbe visualizzare "CaAP abilitato".</span><span class="sxs-lookup"><span data-stu-id="9edca-153">The display should show "CaAP is enabled."</span></span>

1. <span data-ttu-id="9edca-154">Fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="9edca-154">Click **Settings**.</span></span>
2. <span data-ttu-id="9edca-155">Selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="9edca-155">Select **Advanced**.</span></span>
3. <span data-ttu-id="9edca-156">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="9edca-156">Enter the password.</span></span>
4. <span data-ttu-id="9edca-157">Nella sezione Impostazioni di amministrazione, selezionare **Impostazioni del telefono Area comune**.</span><span class="sxs-lookup"><span data-stu-id="9edca-157">In Administration settings, select **Common Area Phone Settings**.</span></span>
5. <span data-ttu-id="9edca-158">Abilitare la **modalità di amministrazione CAP**e **semplice** .</span><span class="sxs-lookup"><span data-stu-id="9edca-158">Enable **CAP** and **CAP Admin Mode**.</span></span>
6. <span data-ttu-id="9edca-159">Fare clic su **Salva file Config**.</span><span class="sxs-lookup"><span data-stu-id="9edca-159">Click **Save Config**.</span></span>

<span data-ttu-id="9edca-160">Il telefono è pronto per essere eseguito il provisioning, che verranno eseguite quando si accede nella schermata principale.</span><span class="sxs-lookup"><span data-stu-id="9edca-160">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="9edca-161">Accedere selezionando **Impostazioni** > **funzionalità** > **Skype per le aziende.**</span><span class="sxs-lookup"><span data-stu-id="9edca-161">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
2. <span data-ttu-id="9edca-162">Selezionare **Le credenziali dell'utente**, quindi selezionare **sign-in web (CAP)** per generare un codice a..</span><span class="sxs-lookup"><span data-stu-id="9edca-162">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="9edca-163">Accedere al portale di provisioning di tipo in http://aka.ms/skypecaped eseguire l'accesso come **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9edca-163">Go to the provisioning portal at http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="9edca-164">Immettere il nome visualizzato (ad esempio Main ricezione) per visualizzare il Capolettera.</span><span class="sxs-lookup"><span data-stu-id="9edca-164">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="9edca-165">[Nota] Se "Cercare solo i telefoni delle aree comuni" è selezionata, deselezionare la casella di controllo e ripetere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9edca-165">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="9edca-166">Nella finestra codice abbinamento, immettere il codice visualizzato sul telefono e fare clic su **per il provisioning**.</span><span class="sxs-lookup"><span data-stu-id="9edca-166">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="9edca-167">In seguito quest'ultimo passaggio, il telefono deve accedere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9edca-167">Following this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="9edca-168">Ulteriori informazioni sui telefoni disponibili in [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="9edca-168">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


