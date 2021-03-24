---
title: Configurare l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: "Riepilogo: configurare l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096822"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="8da6d-103">Configurare l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8da6d-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="8da6d-104">**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8da6d-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="8da6d-105">Nelle sezioni seguenti vengono descritti i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="8da6d-106">Per ulteriori informazioni sull'autenticazione a due fattori, vedere [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="8da6d-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="8da6d-107">Configurare un'autorità di certificazione radice dell'organizzazione per supportare l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="8da6d-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="8da6d-108">La procedura seguente descrive come configurare una CA radice dell'organizzazione per supportare l'autenticazione smart card:</span><span class="sxs-lookup"><span data-stu-id="8da6d-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="8da6d-109">Per informazioni su come installare una CA radice dell'organizzazione, vedere [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="8da6d-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="8da6d-110">Accedere al computer dell'autorità di certificazione dell'organizzazione utilizzando un account Domain Admin.</span><span class="sxs-lookup"><span data-stu-id="8da6d-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="8da6d-111">Avviare Gestore di sistema e verificare che il ruolo Registrazione Web autorità di certificazione sia installato.</span><span class="sxs-lookup"><span data-stu-id="8da6d-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="8da6d-112">Dal menu **Strumenti di amministrazione,** aprire la console **di gestione Autorità** di certificazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="8da6d-113">Nel riquadro di spostamento espandere **Autorità di certificazione.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="8da6d-114">Fai clic con il **pulsante destro del** mouse su Modelli di certificato, seleziona **Nuovo,** quindi **seleziona Modello di certificato da emettere.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="8da6d-115">Selezionare **Agente di registrazione,** **Utente smart card** e Accesso **smart card.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="8da6d-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-116">Click **OK**.</span></span>

8. <span data-ttu-id="8da6d-117">Fare clic con il pulsante destro **del mouse su Modelli di certificato**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="8da6d-118">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-118">Select **Manage**.</span></span>

10. <span data-ttu-id="8da6d-119">Aprire le proprietà del modello Utente smart card.</span><span class="sxs-lookup"><span data-stu-id="8da6d-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="8da6d-120">Fare clic sulla **scheda** Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8da6d-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="8da6d-121">Modificare le autorizzazioni come segue:</span><span class="sxs-lookup"><span data-stu-id="8da6d-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="8da6d-122">Aggiungere singoli account AD utente con autorizzazioni di lettura/registrazione (consenti) o</span><span class="sxs-lookup"><span data-stu-id="8da6d-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="8da6d-123">Aggiungere un gruppo di sicurezza contenente utenti di smart card con autorizzazioni di lettura/registrazione (consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="8da6d-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="8da6d-124">Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (consenti)</span><span class="sxs-lookup"><span data-stu-id="8da6d-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="8da6d-125">Configurare Windows 8 per le smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="8da6d-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="8da6d-126">Un fattore da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia smart card è il costo dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="8da6d-127">Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.</span><span class="sxs-lookup"><span data-stu-id="8da6d-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="8da6d-128">Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1.2, le organizzazioni possono ora ottenere i vantaggi dell'accesso con smart card senza effettuare ulteriori investimenti nell'hardware.</span><span class="sxs-lookup"><span data-stu-id="8da6d-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="8da6d-129">Per altre informazioni, vedi [Uso di smart card virtuali con Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)</span><span class="sxs-lookup"><span data-stu-id="8da6d-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="8da6d-130">Per configurare Windows 8 per le smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="8da6d-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="8da6d-131">Accedi al computer Windows 8 usando le credenziali di un utente abilitato a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8da6d-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="8da6d-132">Nella schermata Start di Windows 8, sposta il cursore nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="8da6d-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="8da6d-133">Selezionare **l'opzione** Cerca e quindi cercare Prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8da6d-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="8da6d-134">Fare clic con il **pulsante destro del mouse** su Prompt dei comandi e quindi scegliere Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="8da6d-135">Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="8da6d-136">Dalla console di gestione TPM, verificare che la versione della specifica TPM sia almeno 1.2</span><span class="sxs-lookup"><span data-stu-id="8da6d-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="8da6d-137">Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un TPM (Compatible Trust Platform Module), verificare che il computer abbia un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.</span><span class="sxs-lookup"><span data-stu-id="8da6d-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="8da6d-138">Chiudere la console di gestione TPM</span><span class="sxs-lookup"><span data-stu-id="8da6d-138">Close the TPM management console</span></span>

8. <span data-ttu-id="8da6d-139">Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="8da6d-140">Per fornire un valore PIN personalizzato durante la creazione della smart card virtuale, usa invece il prompt /pin.</span><span class="sxs-lookup"><span data-stu-id="8da6d-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="8da6d-141">Al prompt dei comandi aprire la console Gestione computer eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="8da6d-142">Nella console Gestione computer seleziona **Gestione dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="8da6d-143">Espandere **Lettori di smart card**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="8da6d-144">Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8da6d-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="8da6d-145">Registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="8da6d-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="8da6d-146">Esistono in genere due metodi per registrare gli utenti per l'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="8da6d-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="8da6d-147">Il metodo più semplice prevede la registrazione diretta degli utenti per l'autenticazione con smart card tramite registrazione Web, mentre il metodo più complesso prevede l'utilizzo di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="8da6d-148">In questo argomento viene illustrata l'autoregistrazione per i certificati smart card.</span><span class="sxs-lookup"><span data-stu-id="8da6d-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="8da6d-149">Per ulteriori informazioni sulla registrazione per conto degli utenti come agente di registrazione, vedere [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="8da6d-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="8da6d-150">Per registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="8da6d-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="8da6d-151">Accedi alla workstation Windows 8 usando le credenziali di un utente abilitato a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8da6d-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="8da6d-152">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8da6d-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="8da6d-153">Passare alla **pagina Registrazione Web Autorità** di certificazione (ad https://MyCA.contoso.com/certsrv) esempio, .</span><span class="sxs-lookup"><span data-stu-id="8da6d-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8da6d-154">Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="8da6d-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="8da6d-155">Nella pagina **di** benvenuto selezionare **Richiedi un certificato.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="8da6d-156">Quindi, selezionare **Richiesta avanzata.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="8da6d-157">Selezionare **Crea e invia una richiesta a questa CA.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="8da6d-158">Selezionare **Utente smart card** nella sezione Modello **di** certificato e completare la richiesta avanzata di certificato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="8da6d-159">**Le opzioni chiave** confermano che le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="8da6d-160">Selezionare il **pulsante di opzione Crea nuovo set di** chiavi</span><span class="sxs-lookup"><span data-stu-id="8da6d-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="8da6d-161">Per **CSP,** selezionare **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="8da6d-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="8da6d-162">Per **Utilizzo chiave,** selezionare **Exchange** (questa è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="8da6d-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="8da6d-163">Per **Dimensioni chiave** immettere 2048</span><span class="sxs-lookup"><span data-stu-id="8da6d-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="8da6d-164">Verificare che **il nome del contenitore di chiavi automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="8da6d-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="8da6d-165">Lasciare deselezionate le altre caselle.</span><span class="sxs-lookup"><span data-stu-id="8da6d-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="8da6d-166">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="8da6d-167">Per **Formato richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="8da6d-168">Per **Algoritmo hash** selezionare **sha1**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="8da6d-169">Per **Nome descrittivo** immettereSmardcard Certificate.</span><span class="sxs-lookup"><span data-stu-id="8da6d-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="8da6d-170">Se si utilizza un lettore di smart card fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da6d-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="8da6d-171">Fare **clic su** Invia per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="8da6d-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="8da6d-172">Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="8da6d-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8da6d-173">Il valore predefinito del PIN della smart card virtuale è "12345678".</span><span class="sxs-lookup"><span data-stu-id="8da6d-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="8da6d-174">Dopo l'emissione del certificato, fare clic **su Installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8da6d-175">Se la richiesta di certificato ha esito negativo con l'errore "Questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="8da6d-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="8da6d-176">Configurare Active Directory Federation Services (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="8da6d-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="8da6d-177">Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2.0) per supportare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="8da6d-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="8da6d-178">Per informazioni su come installare AD FS 2.0, vedere [Ad FS 2.0 Step-by-Step e How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="8da6d-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="8da6d-179">Quando si installa AD FS 2.0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="8da6d-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="8da6d-180">Scaricare e installare invece il [pacchetto Active Directory Federation Services 2.0 RTW.](https://go.microsoft.com/fwlink/p/?LinkId=313375)</span><span class="sxs-lookup"><span data-stu-id="8da6d-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="8da6d-181">Per configurare ADFS per l'autenticazione a due fattori</span><span class="sxs-lookup"><span data-stu-id="8da6d-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="8da6d-182">Accedere al computer AD FS 2.0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="8da6d-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="8da6d-183">Avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8da6d-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="8da6d-184">Dalla riga Windows PowerShell comando, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="8da6d-185">Stabilire una relazione con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico per la distribuzione:</span><span class="sxs-lookup"><span data-stu-id="8da6d-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="8da6d-186">Dal menu Strumenti di amministrazione avvia la console di gestione di AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="8da6d-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="8da6d-187">Espandere **Relazioni di** trust  >  **Trusting Party Trusts**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="8da6d-188">Verificare che sia stata creata una nuova relazione di trust per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8da6d-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="8da6d-189">Creare e assegnare una regola di autorizzazione rilascio per l'attendibilità del relying party Windows PowerShell utilizzando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="8da6d-190">Creare e assegnare una regola di trasformazione rilascio per l'attendibilità del relying party usando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="8da6d-191">Dalla console di gestione di AD FS 2.0 fai clic con il pulsante destro del mouse sull'attendibilità del componente e seleziona **Modifica regole attestazione.**</span><span class="sxs-lookup"><span data-stu-id="8da6d-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="8da6d-192">Selezionare la **scheda Regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8da6d-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="8da6d-193">Selezionare la **scheda Regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8da6d-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="8da6d-194">Configurazione di AD FS 2.0 per supportare l'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="8da6d-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="8da6d-195">Esistono due possibili tipi di autenticazione che possono essere configurati per consentire ad AD FS 2.0 di supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="8da6d-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="8da6d-196">Autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="8da6d-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="8da6d-197">Autenticazione client Transport Layer Security</span><span class="sxs-lookup"><span data-stu-id="8da6d-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="8da6d-198">Utilizzando l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di eseguire l'autenticazione utilizzando il nome utente/password o la smart card e il PIN.</span><span class="sxs-lookup"><span data-stu-id="8da6d-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="8da6d-199">In questo argomento viene illustrato come implementare l'autenticazione client di Transport Layer Security con AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="8da6d-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="8da6d-200">Per ulteriori informazioni sui tipi di autenticazione AD FS 2.0, vedere [AD FS 2.0: Come modificare il tipo di autenticazione locale.](https://go.microsoft.com/fwlink/p/?LinkId=313384)</span><span class="sxs-lookup"><span data-stu-id="8da6d-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="8da6d-201">Per configurare AD FS 2.0 per supportare l'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="8da6d-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="8da6d-202">Accedere al computer AD FS 2.0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="8da6d-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="8da6d-203">Avvia Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="8da6d-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="8da6d-204">Passare a C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="8da6d-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="8da6d-205">Creare una copia di backup del file web.config esistente.</span><span class="sxs-lookup"><span data-stu-id="8da6d-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="8da6d-206">Aprire il file di web.config esistente utilizzando Blocco note.</span><span class="sxs-lookup"><span data-stu-id="8da6d-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="8da6d-207">Nella barra dei menu selezionare **Modifica** e quindi **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="8da6d-208">Cercare \<localAuthenticationTypes\> .</span><span class="sxs-lookup"><span data-stu-id="8da6d-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="8da6d-209">Si noti che sono elencati quattro tipi di autenticazione, uno per riga.</span><span class="sxs-lookup"><span data-stu-id="8da6d-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="8da6d-210">Spostare la riga contenente il tipo di autenticazione TLSClient all'inizio dell'elenco nella sezione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="8da6d-211">Salvare e chiudere il file web.config file.</span><span class="sxs-lookup"><span data-stu-id="8da6d-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="8da6d-212">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="8da6d-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="8da6d-213">Riavviare IIS eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="8da6d-214">Configurazione dell'autenticazione passiva di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8da6d-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="8da6d-215">La sezione seguente descrive come configurare Skype for Business Server per supportare l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="8da6d-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="8da6d-216">Una volta abilitato, gli utenti abilitati per l'autenticazione a due fattori doranno utilizzare una smart card fisica o virtuale e un PIN valido per accedere utilizzando il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8da6d-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="8da6d-217">È consigliabile che i clienti abilitino l'autenticazione passiva per la funzione di registrazione e i servizi Web a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="8da6d-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="8da6d-218">Se l'autenticazione passiva è abilitata per la funzione di registrazione e i servizi Web a livello globale, si verificano probabilmente errori di autenticazione a livello di organizzazione per gli utenti che non amberanno con il client desktop supportato.</span><span class="sxs-lookup"><span data-stu-id="8da6d-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="8da6d-219">Configurazione servizio Web</span><span class="sxs-lookup"><span data-stu-id="8da6d-219">Web Service Configuration</span></span>

<span data-ttu-id="8da6d-220">Nei passaggi seguenti viene descritto come creare una configurazione del servizio Web personalizzata per i server Director, Pool Enterprise e Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="8da6d-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="8da6d-221">Per creare una configurazione del servizio Web personalizzata</span><span class="sxs-lookup"><span data-stu-id="8da6d-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="8da6d-222">Accedere al server Front End di Skype for Business Server con un account amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8da6d-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="8da6d-223">Avviare Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8da6d-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="8da6d-224">Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione del servizio Web per ogni server Director, Pool Enterprise e Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="8da6d-225">Il valore per il nome di dominio completo WsFedPassiveMetadataUri è il nome del servizio federativo del server AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="8da6d-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="8da6d-226">Il valore Nome servizio federativo è disponibile nella console di gestione di AD FS 2.0 facendo clic con il pulsante destro del mouse su **Servizio** nel riquadro di spostamento e quindi scegliendo Modifica proprietà **servizio federativo**.</span><span class="sxs-lookup"><span data-stu-id="8da6d-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="8da6d-227">Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="8da6d-228">Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferito per l'autenticazione webticket.</span><span class="sxs-lookup"><span data-stu-id="8da6d-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="8da6d-229">Per tutti i server Director, Pool Enterprise e Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati in Servizi Web Skype for Business eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="8da6d-230">Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati correttamente eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="8da6d-231">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="8da6d-231">Proxy Configuration</span></span>

<span data-ttu-id="8da6d-232">Quando l'autenticazione del certificato è disabilitata per i servizi Web Skype for Business, il client Skype for Business utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="8da6d-233">L'autenticazione del certificato è ancora necessaria per consentire al client di recuperare un webticket, tuttavia, Kerberos e NTLM devono essere disabilitati per il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8da6d-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="8da6d-234">Nei passaggi seguenti viene descritto come creare una configurazione proxy personalizzata per pool di server perimetrali, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="8da6d-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="8da6d-235">Per creare una configurazione proxy personalizzata</span><span class="sxs-lookup"><span data-stu-id="8da6d-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="8da6d-236">Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione proxy per ogni pool di server perimetrali, pool Enterprise e server Standard Edition di Skype for Business Server che verrà abilitato per l'autenticazione passiva eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da6d-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="8da6d-237">Verificare che tutti gli altri tipi di autenticazione proxy siano stati disabilitati correttamente eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da6d-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="8da6d-238">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8da6d-238">See also</span></span>

[<span data-ttu-id="8da6d-239">Gestire l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8da6d-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="8da6d-240">Usare l'autenticazione a due fattori con il client Skype for Business e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8da6d-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)