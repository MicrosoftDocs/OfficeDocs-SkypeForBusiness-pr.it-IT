---
title: Distribuzione dei telefoni per Skype for Business Online
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="c2d3e-103">Telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="c2d3e-103">Common Area Phones</span></span>
<span data-ttu-id="c2d3e-104">Un telefono di area comune o maiuscola, è in genere in un'area condivisa e non associato a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="c2d3e-105">Ad esempio, un telefono di area di ricezione, porta telefono o sale riunioni telefono, estremità sono impostati come dispositivi piuttosto che gli utenti ed eseguito automaticamente l'accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="c2d3e-106">Nella procedura seguente è sarà consentono di configurare un account per il sistema telefonico Microsoft con la chiamata dei piani e quindi distribuire un Capolettera.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="c2d3e-107">Prerequisiti per i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="c2d3e-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="c2d3e-108">Verificare di disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c2d3e-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="c2d3e-109">Acquistato Common Area Phone SKU</span><span class="sxs-lookup"><span data-stu-id="c2d3e-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="c2d3e-110">Firmware aggiornato (vedere supportati Firmware nell'argomentohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="c2d3e-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="c2d3e-111">Telefoni approvati (consente di visualizzare l'elenco nellahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="c2d3e-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="c2d3e-112">Verificare il firmware per il telefono</span><span class="sxs-lookup"><span data-stu-id="c2d3e-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="c2d3e-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="c2d3e-114">i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="c2d3e-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="c2d3e-116">I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="c2d3e-117">Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="c2d3e-118">Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="c2d3e-119">A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="c2d3e-120">È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e l'impostazione del parametro _EnableDeviceUpdate_ `false`.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="c2d3e-121">Creare remoto</span><span class="sxs-lookup"><span data-stu-id="c2d3e-121">Create CAP</span></span>
<span data-ttu-id="c2d3e-122">Per creare la Terminazione, configurare le impostazioni prima di impostare l'apparecchio telefonico.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="c2d3e-123">Il telefono Area comune SKU di acquisto.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="c2d3e-124">Impostare il telefono area comune<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="c2d3e-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="c2d3e-125">**Creare utente**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-125">**Create user**</span></span> 
1. <span data-ttu-id="c2d3e-126">Assegnare Common Area Phone SKU</span><span class="sxs-lookup"><span data-stu-id="c2d3e-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="c2d3e-127">Assegnare la chiamata a pianificare (se si utilizza Microsoft Phone System con la chiamata dei piani).</span><span class="sxs-lookup"><span data-stu-id="c2d3e-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="c2d3e-128">Assegna un numero di telefono disponibili in Skype per Business Admin Center o richiedere un nuovo numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="c2d3e-129">**Crea nuovo utente**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-129">**Create New User**</span></span>

1. <span data-ttu-id="c2d3e-130">Nel riquadro di provisioning si ha la possibilità di immettere un nome e cognome (ad esempio, ricezione principale).</span><span class="sxs-lookup"><span data-stu-id="c2d3e-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="c2d3e-131">Immettere un nome visualizzato (obbligatorio), ad esempio, "ricezione Main".</span><span class="sxs-lookup"><span data-stu-id="c2d3e-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="c2d3e-132">Immettere un nome utente (obbligatorio), ad esempio "MainReception" @"domain" (nome della società o dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="c2d3e-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="c2d3e-133">Immettere il percorso (paese).</span><span class="sxs-lookup"><span data-stu-id="c2d3e-133">Enter Location (country).</span></span>

<span data-ttu-id="c2d3e-134">**Assegnare Common Area Phone SKU** Nell'interfaccia di amministrazione di Office 365 andare a **fatturazione > servizi di acquisto** e aggiungere **Telefono di Area comune**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="c2d3e-135">**Assegnare Plan chiamate nelle SKU CAP**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="c2d3e-136">Selezionare una chiamata prevede di abilitare il telefono.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="c2d3e-137">Aggiungere la Terminazione per abilitare il sistema telefonico e Skype per Business Online piano 2 in SKU Capolettera.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="c2d3e-138">**Assegnare un numero di telefono**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="c2d3e-139">Controllare i numeri di telefono disponibili in **vocali > numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="c2d3e-140">Selezionare un numero dall'elenco disponibile i numeri del numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="c2d3e-141">Conferma selezioni selezionando **vocali** e **I numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="c2d3e-142">[Nota] Gli utenti vocali vengono visualizzate solo se dispongono della licenza di sistema telefonico applicata, anche se anche dopo aver applicato, potrebbe richiedere tempo per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="c2d3e-143">Talvolta riapertura Skype per Business Admin center consente.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="c2d3e-144">Configurare telefono</span><span class="sxs-lookup"><span data-stu-id="c2d3e-144">Configure Phone</span></span>

<span data-ttu-id="c2d3e-145">**Preparare i telefoni fisici**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="c2d3e-146">Il telefono selezionato deve avere la modalità di telefono di Area comune.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="c2d3e-147">***Telefono Polycom VVX di esempio***</span><span class="sxs-lookup"><span data-stu-id="c2d3e-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="c2d3e-148">Attivare la modalità di telefono Area comune in Polycom VVX eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c2d3e-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="c2d3e-149">Nel browser, utilizzare l'interfaccia web per attivare la modalità di limitare il VVX</span><span class="sxs-lookup"><span data-stu-id="c2d3e-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="c2d3e-150">Passare **all'impostazione** e Skype per l'opzione Impostazioni Business, selezionare **Telefono di Area comune**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="c2d3e-151">Fare clic su **Salva** per salvare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="c2d3e-152">Ora che la modalità telefonica CAP è attivata, impostare il telefono con display del telefono.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="c2d3e-153">In impostazioni, selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="c2d3e-154">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-154">Enter password.</span></span>
3. <span data-ttu-id="c2d3e-155">Nella sezione Impostazioni di amministrazione, selezionare **Impostazioni del telefono Area comune**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="c2d3e-156">Abilitare Common Area Phone and Admin CAP</span><span class="sxs-lookup"><span data-stu-id="c2d3e-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="c2d3e-157">Selezionare **Salva file Config**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-157">Select **Save Config**.</span></span>

<span data-ttu-id="c2d3e-158">Il telefono è pronto per essere eseguito il provisioning, che verranno eseguite quando si accede nella schermata principale.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="c2d3e-159">Eseguire l'accesso tramite la selezione di **Impostazioni > funzionalità > Skype per le aziende.**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="c2d3e-160">Selezionare le credenziali dell'utente, quindi selezionare selezionare **sign-in web (CAP)** per generare un codice di..</span><span class="sxs-lookup"><span data-stu-id="c2d3e-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="c2d3e-161">Accedere al portale di provisioning http://aka.ms/skypecaped eseguire l'accesso come **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="c2d3e-162">Immettere il nome visualizzato (ad esempio Main ricezione) per visualizzare il Capolettera.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="c2d3e-163">[Nota] Se "Cercare solo i telefoni delle aree comuni" è selezionata, deselezionare la casella di controllo e ripetere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="c2d3e-164">Nella finestra codice abbinamento, immettere il codice visualizzato sul telefono e fare clic su **per il provisioning**.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="c2d3e-165">WHT quest'ultimo passaggio, il telefono deve accedere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="c2d3e-166">Ulteriori informazioni sui telefoni disponibili in [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="c2d3e-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


