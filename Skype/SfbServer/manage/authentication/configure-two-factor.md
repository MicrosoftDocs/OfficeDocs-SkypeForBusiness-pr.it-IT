---
title: Configurare l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: "Riepilogo: configurare l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189689"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="5cff2-103">Configurare l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cff2-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="5cff2-104">**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5cff2-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="5cff2-105">Nelle sezioni seguenti vengono illustrati i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cff2-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="5cff2-106">Per altre informazioni sull'autenticazione a due fattori, vedere [abilitare l'autenticazione a più fattori di Office 365 per gli amministratori online-Grid User post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="5cff2-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="5cff2-107">Configurare un'autorità di certificazione radice aziendale per supportare l'autenticazione tramite smart card</span><span class="sxs-lookup"><span data-stu-id="5cff2-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="5cff2-108">La procedura seguente descrive come configurare una CA radice aziendale per supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="5cff2-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="5cff2-109">Per informazioni su come installare una CA radice aziendale, vedere [installare un'autorità di certificazione radice aziendale](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="5cff2-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="5cff2-110">Accedere al computer della CA aziendale usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="5cff2-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="5cff2-111">Avviare System Manager e verificare che sia installato il ruolo di registrazione Web Authority Certificate.</span><span class="sxs-lookup"><span data-stu-id="5cff2-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="5cff2-112">Nel menu **strumenti di amministrazione** aprire la console di gestione **autorità di certificazione** .</span><span class="sxs-lookup"><span data-stu-id="5cff2-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="5cff2-113">Nel riquadro di spostamento espandere **autorità di certificazione**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="5cff2-114">Fare clic con il pulsante destro del mouse sui **modelli di certificato**, scegliere **nuovo**e quindi **modello certificato da emettere**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="5cff2-115">Selezionare **agente di registrazione**, **utente smartcard**e accesso tramite **smartcard**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="5cff2-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-116">Click **OK**.</span></span>

8. <span data-ttu-id="5cff2-117">Fare clic con il pulsante destro sul **modello di certificato**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="5cff2-118">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-118">Select **Manage**.</span></span>

10. <span data-ttu-id="5cff2-119">Aprire le proprietà del modello utente smartcard.</span><span class="sxs-lookup"><span data-stu-id="5cff2-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="5cff2-120">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="5cff2-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="5cff2-121">Modificare le autorizzazioni nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="5cff2-122">Aggiungere singoli account di annunci utente con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="5cff2-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="5cff2-123">Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="5cff2-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="5cff2-124">Aggiungere il gruppo Domain Users con le autorizzazioni di lettura/registrazione (Consenti)</span><span class="sxs-lookup"><span data-stu-id="5cff2-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="5cff2-125">Configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="5cff2-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="5cff2-126">Un fattore da tenere in considerazione quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo di implementazione.</span><span class="sxs-lookup"><span data-stu-id="5cff2-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="5cff2-127">Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove caratteristiche più interessanti è il supporto per le smart card virtuali.</span><span class="sxs-lookup"><span data-stu-id="5cff2-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="5cff2-128">Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza apportare ulteriori investimenti nell'hardware.</span><span class="sxs-lookup"><span data-stu-id="5cff2-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="5cff2-129">Per altre informazioni, vedere [uso di smart card virtuali con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="5cff2-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="5cff2-130">Per configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="5cff2-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="5cff2-131">Accedere al computer con Windows 8 usando le credenziali di un utente abilitato per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5cff2-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="5cff2-132">Nella schermata Start di Windows 8 Posizionare il cursore nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="5cff2-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="5cff2-133">Selezionare l'opzione di **ricerca** e quindi Cerca in forCommand prompt.</span><span class="sxs-lookup"><span data-stu-id="5cff2-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="5cff2-134">Fare clic con il pulsante destro del mouse sul **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="5cff2-135">Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="5cff2-136">Nella console di gestione TPM verificare che la versione specifica del TPM sia di almeno 1,2</span><span class="sxs-lookup"><span data-stu-id="5cff2-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cff2-137">Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un modulo TPM (compatible Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.</span><span class="sxs-lookup"><span data-stu-id="5cff2-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="5cff2-138">Chiudere la console di gestione TPM</span><span class="sxs-lookup"><span data-stu-id="5cff2-138">Close the TPM management console</span></span>

8. <span data-ttu-id="5cff2-139">Dal prompt dei comandi creare una nuova smart card virtuale usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="5cff2-140">Per specificare un valore PIN personalizzato durante la creazione della smart card virtuale, usare invece il prompt di/pin.</span><span class="sxs-lookup"><span data-stu-id="5cff2-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="5cff2-141">Dal prompt dei comandi aprire la console di gestione computer eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="5cff2-142">Nella console di gestione computer selezionare **Gestione dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="5cff2-143">Espandi **lettori di smart card**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="5cff2-144">Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cff2-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="5cff2-145">Registrare gli utenti per l'autenticazione tramite smart card</span><span class="sxs-lookup"><span data-stu-id="5cff2-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="5cff2-146">Sono in genere disponibili due metodi per l'iscrizione degli utenti per l'autenticazione tramite smart card.</span><span class="sxs-lookup"><span data-stu-id="5cff2-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="5cff2-147">Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card usando la registrazione Web, mentre il metodo più complesso prevede l'uso di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5cff2-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="5cff2-148">Questo argomento riguarda l'autoregistrazione per i certificati smartcard.</span><span class="sxs-lookup"><span data-stu-id="5cff2-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="5cff2-149">Per altre informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere [registrare i certificati per conto di altri utenti](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="5cff2-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="5cff2-150">Per registrare gli utenti per l'autenticazione tramite smart card</span><span class="sxs-lookup"><span data-stu-id="5cff2-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="5cff2-151">Accedere alla workstation Windows 8 usando le credenziali di un utente abilitato per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5cff2-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="5cff2-152">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5cff2-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="5cff2-153">Passare alla pagina di **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="5cff2-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cff2-154">Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5cff2-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="5cff2-155">Nella pagina di **benvenuto** selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="5cff2-156">Selezionare quindi **Advanced request**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="5cff2-157">Selezionare **Crea e invia una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="5cff2-158">Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cff2-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="5cff2-159">Le **Opzioni principali** confermano le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cff2-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="5cff2-160">Selezionare il pulsante di opzione **Crea nuovo set di tasti**</span><span class="sxs-lookup"><span data-stu-id="5cff2-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="5cff2-161">Per **CSP**selezionare **provider di crittografia Smart Card Microsoft base**</span><span class="sxs-lookup"><span data-stu-id="5cff2-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="5cff2-162">Per l' **utilizzo delle chiavi**, selezionare **Exchange** (questa è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="5cff2-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="5cff2-163">Per le **dimensioni della chiave**, immettere 2048</span><span class="sxs-lookup"><span data-stu-id="5cff2-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="5cff2-164">Verificare che il **nome del contenitore di tasti automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="5cff2-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="5cff2-165">Abbandonare le altre caselle deselezionate.</span><span class="sxs-lookup"><span data-stu-id="5cff2-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="5cff2-166">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cff2-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="5cff2-167">Per il **formato di richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="5cff2-168">Per l' **algoritmo hash** selezionare **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="5cff2-169">Per **nome** descrittivo enterSmardcard certificato.</span><span class="sxs-lookup"><span data-stu-id="5cff2-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="5cff2-170">Se si usa un lettore di smartcard fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5cff2-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="5cff2-171">Fare clic su **Invia** per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="5cff2-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="5cff2-172">Quando richiesto, immettere il PIN usato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="5cff2-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cff2-173">Il valore PIN della smart card virtuale predefinito è "12345678".</span><span class="sxs-lookup"><span data-stu-id="5cff2-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="5cff2-174">Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5cff2-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="5cff2-175">Se la richiesta di certificato non riesce con l'errore "questo Web browser non supporta la generazione di richieste di certificato," Esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="5cff2-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="5cff2-176">Configurare Active Directory Federation Services (AD FS 2,0)</span><span class="sxs-lookup"><span data-stu-id="5cff2-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="5cff2-177">La sezione seguente descrive come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="5cff2-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="5cff2-178">Per informazioni su come installare ADFS 2,0, vedere [istruzioni dettagliate su adfs 2,0 e come eseguire una guida](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="5cff2-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="5cff2-179">Quando si installa ADFS 2,0, non usare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="5cff2-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="5cff2-180">Scaricare e installare invece il [pacchetto-RTW di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="5cff2-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="5cff2-181">Per configurare ADFS per l'autenticazione a due fattori</span><span class="sxs-lookup"><span data-stu-id="5cff2-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="5cff2-182">Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="5cff2-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="5cff2-183">Avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cff2-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="5cff2-184">Nella riga di comando di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="5cff2-185">Stabilire una partnership con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="5cff2-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="5cff2-186">Nel menu strumenti di amministrazione avviare la console di gestione di ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="5cff2-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="5cff2-187">Espandere i**trust** **tra le relazioni** > di trust.</span><span class="sxs-lookup"><span data-stu-id="5cff2-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="5cff2-188">Verificare che sia stato creato un nuovo trust per il server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5cff2-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="5cff2-189">Creare e assegnare una regola di autorizzazione del rilascio per l'attendibilità del componente tramite Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cff2-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="5cff2-190">Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente usando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cff2-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="5cff2-191">Nella console di gestione di ADFS 2,0 fare clic con il pulsante destro del mouse sull'attendibilità del componente e scegliere **modifica regole attestazione**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="5cff2-192">Selezionare la scheda **regole di autorizzazione del rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cff2-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="5cff2-193">Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cff2-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="5cff2-194">Configurazione di ADFS 2,0 per supportare l'autenticazione del client</span><span class="sxs-lookup"><span data-stu-id="5cff2-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="5cff2-195">Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire AD FS 2,0 di supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="5cff2-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="5cff2-196">Autenticazione basata su moduli (FBA)</span><span class="sxs-lookup"><span data-stu-id="5cff2-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="5cff2-197">Autenticazione del client di sicurezza dei livelli di trasporto</span><span class="sxs-lookup"><span data-stu-id="5cff2-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="5cff2-198">Usando l'autenticazione basata su moduli, puoi sviluppare una pagina Web che consente agli utenti di autenticarsi usando il loro nome utente/password o usando la loro smart card e il PIN.</span><span class="sxs-lookup"><span data-stu-id="5cff2-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="5cff2-199">Questo argomento illustra come implementare l'autenticazione del client di sicurezza dei livelli di trasporto con ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="5cff2-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="5cff2-200">Per altre informazioni sui tipi di autenticazione di ADFS 2,0, vedere ADFS [2,0: come modificare il tipo di autenticazione locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="5cff2-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="5cff2-201">Per configurare ADFS 2,0 per supportare l'autenticazione del client</span><span class="sxs-lookup"><span data-stu-id="5cff2-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="5cff2-202">Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="5cff2-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="5cff2-203">Avviare Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="5cff2-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="5cff2-204">Passare a C:\Inetpub\Adfs\Ls</span><span class="sxs-lookup"><span data-stu-id="5cff2-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="5cff2-205">Creare una copia di backup del file Web. config esistente.</span><span class="sxs-lookup"><span data-stu-id="5cff2-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="5cff2-206">Aprire il file Web. config esistente tramite il blocco note.</span><span class="sxs-lookup"><span data-stu-id="5cff2-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="5cff2-207">Nella barra dei menu selezionare **modifica** e quindi **trova**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="5cff2-208">Cercare \<localAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="5cff2-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="5cff2-209">Tieni presente che sono presenti quattro tipi di autenticazione, uno per riga.</span><span class="sxs-lookup"><span data-stu-id="5cff2-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="5cff2-210">Posizionare la linea contenente il tipo di autenticazione TLSClient nella parte superiore dell'elenco nella sezione.</span><span class="sxs-lookup"><span data-stu-id="5cff2-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="5cff2-211">Salvare e chiudere il file Web. config.</span><span class="sxs-lookup"><span data-stu-id="5cff2-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="5cff2-212">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="5cff2-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="5cff2-213">Riavviare IIS eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="5cff2-214">Configurazione dell'autenticazione passiva di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cff2-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="5cff2-215">La sezione seguente descrive come configurare Skype for Business Server per supportare l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="5cff2-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="5cff2-216">Una volta abilitati, gli utenti abilitati per l'autenticazione a due fattori saranno tenuti a usare una smart card fisica o virtuale e un PIN valido per accedere con il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5cff2-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="5cff2-217">È consigliabile che i clienti consentano l'autenticazione passiva per il registrar e i servizi Web a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="5cff2-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="5cff2-218">Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, probabilmente si verificheranno errori di autenticazione a livello di organizzazione per gli utenti che non hanno eseguito l'accesso con il client desktop supportato.</span><span class="sxs-lookup"><span data-stu-id="5cff2-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="5cff2-219">Configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="5cff2-219">Web Service Configuration</span></span>

<span data-ttu-id="5cff2-220">I passaggi seguenti descrivono come creare una configurazione di servizio Web personalizzata per direttori, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="5cff2-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="5cff2-221">Per creare una configurazione di un servizio Web personalizzato</span><span class="sxs-lookup"><span data-stu-id="5cff2-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="5cff2-222">Accedere al server front end di Skype for Business Server usando un account di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5cff2-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="5cff2-223">Avviare Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5cff2-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="5cff2-224">Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione di servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="5cff2-225">Il valore per l'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="5cff2-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="5cff2-226">Il valore nome servizio federativo può essere trovato nella console di gestione di ADFS 2,0 facendo clic con il pulsante destro del mouse su **servizio** dal riquadro di spostamento e quindi selezionando **modifica proprietà servizio federativo**.</span><span class="sxs-lookup"><span data-stu-id="5cff2-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="5cff2-227">Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="5cff2-228">Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket.</span><span class="sxs-lookup"><span data-stu-id="5cff2-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="5cff2-229">Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati in servizi web Skype for business eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="5cff2-230">Verificare che tutti gli altri tipi di autenticazione siano stati correttamente disabilitati eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="5cff2-231">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="5cff2-231">Proxy Configuration</span></span>

<span data-ttu-id="5cff2-232">Quando l'autenticazione dei certificati è disabilitata per i servizi web Skype for business, il client Skype for business userà un tipo di autenticazione meno consigliato, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio registrar.</span><span class="sxs-lookup"><span data-stu-id="5cff2-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="5cff2-233">L'autenticazione del certificato è ancora necessaria per consentire al client di recuperare un ticket, ma Kerberos e NTLM devono essere disabilitati per il servizio registrar.</span><span class="sxs-lookup"><span data-stu-id="5cff2-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="5cff2-234">I passaggi seguenti descrivono come creare una configurazione proxy personalizzata per i pool di Edge, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="5cff2-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="5cff2-235">Per creare una configurazione proxy personalizzata</span><span class="sxs-lookup"><span data-stu-id="5cff2-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="5cff2-236">Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione proxy per ogni server Edge di Skype for Business Server, pool Enterprise e Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo le operazioni seguenti comandi</span><span class="sxs-lookup"><span data-stu-id="5cff2-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="5cff2-237">Verificare che tutti gli altri tipi di autenticazione proxy siano stati correttamente disabilitati eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5cff2-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="5cff2-238">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cff2-238">See also</span></span>

[<span data-ttu-id="5cff2-239">Gestire l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cff2-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="5cff2-240">Usare l'autenticazione a due fattori con client Skype for business e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cff2-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
