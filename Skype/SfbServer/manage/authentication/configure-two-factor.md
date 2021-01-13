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
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814416"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="c9ed3-103">Configurare l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9ed3-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="c9ed3-104">**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="c9ed3-105">Nelle sezioni seguenti vengono descritti i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="c9ed3-106">Per ulteriori informazioni sull'autenticazione a due fattori, vedere [Abilitazione di Office 365 multi-factor authentication for online Administrators-Grid User post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="c9ed3-107">Configurare un'autorità di certificazione radice dell'organizzazione per il supporto dell'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="c9ed3-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="c9ed3-108">Nella procedura seguente viene descritto come configurare una CA radice dell'organizzazione per il supporto dell'autenticazione con smart card:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="c9ed3-109">Per informazioni su come installare una CA radice dell'organizzazione, vedere [Install a Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="c9ed3-110">Accedere al computer della CA dell'organizzazione utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="c9ed3-111">Avviare System Manager e verificare che sia installato il ruolo di registrazione Web dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="c9ed3-112">Dal menu **strumenti di amministrazione** , aprire la console di gestione **autorità di certificazione** .</span><span class="sxs-lookup"><span data-stu-id="c9ed3-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="c9ed3-113">Nel riquadro di spostamento espandere **autorità di certificazione**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="c9ed3-114">Fare clic con il pulsante destro del mouse su **modelli di certificato**, selezionare **nuovo** e quindi selezionare **modello di certificato da emettere**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="c9ed3-115">Selezionare **l'agente di registrazione, l'** **utente smartcard** e l' **accesso smartcard**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="c9ed3-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-116">Click **OK**.</span></span>

8. <span data-ttu-id="c9ed3-117">Fare clic con il pulsante destro su **modelli di certificato**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="c9ed3-118">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-118">Select **Manage**.</span></span>

10. <span data-ttu-id="c9ed3-119">Aprire le proprietà del modello utente smartcard.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="c9ed3-120">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="c9ed3-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="c9ed3-121">Modificare le autorizzazioni come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="c9ed3-122">Aggiungere singoli account di Active Directory con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="c9ed3-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="c9ed3-123">Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="c9ed3-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="c9ed3-124">Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (Consenti)</span><span class="sxs-lookup"><span data-stu-id="c9ed3-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="c9ed3-125">Configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="c9ed3-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="c9ed3-126">Uno dei fattori da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="c9ed3-127">Windows 8 fornisce una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="c9ed3-128">Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza effettuare ulteriori investimenti nell'hardware.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="c9ed3-129">Per ulteriori informazioni, vedere [using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="c9ed3-130">Per configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="c9ed3-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="c9ed3-131">Eseguire l'accesso al computer con Windows 8 utilizzando le credenziali di un utente abilitato per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="c9ed3-132">Nella schermata Start di Windows 8, spostare il cursore nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="c9ed3-133">Selezionare l'opzione di **ricerca** e quindi prompt di ricerca forCommand.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="c9ed3-134">Fare clic con il pulsante destro del mouse su **prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="c9ed3-135">Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="c9ed3-136">Dalla console di gestione TPM, verificare che la versione specifica TPM sia almeno 1,2</span><span class="sxs-lookup"><span data-stu-id="c9ed3-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ed3-137">Se viene visualizzata una finestra di dialogo in cui viene indicato che non è possibile trovare un modulo TPM (Trusted Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS del sistema.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="c9ed3-138">Chiudere la console di gestione TPM</span><span class="sxs-lookup"><span data-stu-id="c9ed3-138">Close the TPM management console</span></span>

8. <span data-ttu-id="c9ed3-139">Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="c9ed3-140">Per fornire un valore PIN personalizzato quando si crea la smart card virtuale, utilizzare invece il prompt di/pin.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="c9ed3-141">Al prompt dei comandi, aprire la console di gestione computer eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="c9ed3-142">Nella console Gestione computer selezionare **Gestione dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="c9ed3-143">Espandere **lettori di smart card**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="c9ed3-144">Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="c9ed3-145">Registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="c9ed3-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="c9ed3-146">Sono in genere disponibili due metodi per la registrazione di utenti per l'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="c9ed3-147">Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card tramite la registrazione Web, mentre il metodo più complesso implica l'utilizzo di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="c9ed3-148">Questo argomento è dedicato alla registrazione automatica dei certificati smartcard.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="c9ed3-149">Per ulteriori informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere [registrazione per i certificati per conto di altri utenti](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="c9ed3-150">Per registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="c9ed3-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="c9ed3-151">Accedere alla workstation Windows 8 utilizzando le credenziali di un utente abilitato per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="c9ed3-152">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="c9ed3-153">Passare alla pagina **registrazione Web Authority Certificate** (ad https://MyCA.contoso.com/certsrv) esempio,.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ed3-154">Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="c9ed3-155">Nella pagina **iniziale** , selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="c9ed3-156">Successivamente, selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="c9ed3-157">Selezionare **Crea e invia una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="c9ed3-158">Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="c9ed3-159">Le **Opzioni principali** confermano le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="c9ed3-160">Selezionare il pulsante di opzione **Crea nuovo set di tasti**</span><span class="sxs-lookup"><span data-stu-id="c9ed3-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="c9ed3-161">Per **CSP**, selezionare **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="c9ed3-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="c9ed3-162">Per l' **utilizzo della chiave**, selezionare **Exchange** (è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="c9ed3-163">Per le **dimensioni della chiave**, immettere 2048</span><span class="sxs-lookup"><span data-stu-id="c9ed3-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="c9ed3-164">Confermare che il **nome del contenitore di chiavi automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="c9ed3-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="c9ed3-165">Lasciare deselezionate le altre caselle.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="c9ed3-166">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="c9ed3-167">Per il **formato di richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="c9ed3-168">Per l' **algoritmo hash** selezionare **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="c9ed3-169">Per il certificato enterSmardcard **nome descrittivo** .</span><span class="sxs-lookup"><span data-stu-id="c9ed3-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="c9ed3-170">Se si utilizza un lettore di smartcard fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="c9ed3-171">Fare clic su **Invia** per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="c9ed3-172">Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ed3-173">Il valore del PIN della smart card virtuale predefinito è' 12345678'.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="c9ed3-174">Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c9ed3-175">Se la richiesta di certificato ha esito negativo con l'errore "questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="c9ed3-176">Configurazione di Active Directory Federation Services (AD FS 2,0)</span><span class="sxs-lookup"><span data-stu-id="c9ed3-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="c9ed3-177">Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="c9ed3-178">Per informazioni su come installare ADFS 2,0, vedere [ad fs 2,0 Step-by-Step e guide](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="c9ed3-179">Quando si installa AD FS 2,0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="c9ed3-180">Scaricare e installare invece il [pacchetto di RTW di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="c9ed3-181">Per configurare AD FS per l'autenticazione a due fattori</span><span class="sxs-lookup"><span data-stu-id="c9ed3-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="c9ed3-182">Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="c9ed3-183">Avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="c9ed3-184">Dalla riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="c9ed3-185">Stabilire una partnership con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="c9ed3-186">Dal menu strumenti di amministrazione, avviare la console di gestione di AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="c9ed3-187">Espandi **relazioni di trust**  >  **relying party trust**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="c9ed3-188">Verificare che sia stata creata una nuova relazione di trust per il server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="c9ed3-189">Creare e assegnare una regola di autorizzazione di rilascio per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="c9ed3-190">Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="c9ed3-191">Dalla console di gestione AD FS 2,0, fare clic con il pulsante destro del mouse sul trust relying party e selezionare **modifica regole attestazione**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="c9ed3-192">Selezionare la scheda **regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="c9ed3-193">Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="c9ed3-194">Configurazione di AD FS 2,0 per il supporto dell'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="c9ed3-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="c9ed3-195">Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire ad FS 2,0 di supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="c9ed3-196">Autenticazione basata su form (moduli)</span><span class="sxs-lookup"><span data-stu-id="c9ed3-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="c9ed3-197">Autenticazione del client di sicurezza layer di trasporto</span><span class="sxs-lookup"><span data-stu-id="c9ed3-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="c9ed3-198">Se si utilizza l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di autenticarsi usando il proprio nome utente/password o utilizzando la smart card e il PIN.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="c9ed3-199">Questo argomento è dedicato all'implementazione dell'autenticazione del client per la sicurezza del layer di trasporto con AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="c9ed3-200">Per ulteriori informazioni sui tipi di autenticazione AD FS 2,0, vedere [ad fs 2,0: come modificare il tipo di autenticazione locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="c9ed3-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="c9ed3-201">Per configurare ad FS 2,0 per il supporto dell'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="c9ed3-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="c9ed3-202">Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="c9ed3-203">Avviare Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="c9ed3-204">Passare a C:\Inetpub\Adfs\Ls</span><span class="sxs-lookup"><span data-stu-id="c9ed3-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="c9ed3-205">Creare una copia di backup del file di web.config esistente.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="c9ed3-206">Aprire il file web.config esistente utilizzando il blocco note.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="c9ed3-207">Dalla barra dei menu, selezionare **modifica** , quindi selezionare **trova**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="c9ed3-208">Cerca \<localAuthenticationTypes\> .</span><span class="sxs-lookup"><span data-stu-id="c9ed3-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="c9ed3-209">Tenere presente che sono presenti quattro tipi di autenticazione, uno per riga.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="c9ed3-210">Spostare la riga contenente il tipo di autenticazione di TLSClient nella parte superiore dell'elenco della sezione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="c9ed3-211">Salvare e chiudere il file web.config.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="c9ed3-212">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="c9ed3-213">Riavviare IIS eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="c9ed3-214">Configurazione dell'autenticazione passiva di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9ed3-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="c9ed3-215">Nella sezione seguente viene descritto come configurare Skype for Business Server per supportare l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="c9ed3-216">Una volta abilitata, gli utenti abilitati per l'autenticazione a due fattori dovranno utilizzare una smart card fisica o virtuale e un PIN valido per accedere utilizzando il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ed3-217">È consigliabile che i clienti consentano l'autenticazione passiva per i servizi di registrazione e Web a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="c9ed3-218">Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, è probabile che si verifichino errori di autenticazione a livello dell'organizzazione per gli utenti che non accedono con il client desktop supportato.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="c9ed3-219">Configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="c9ed3-219">Web Service Configuration</span></span>

<span data-ttu-id="c9ed3-220">Nella procedura seguente viene descritto come creare una configurazione del servizio Web personalizzata per i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="c9ed3-221">Per creare una configurazione del servizio Web personalizzato</span><span class="sxs-lookup"><span data-stu-id="c9ed3-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="c9ed3-222">Accedere al server front end di Skype for Business Server utilizzando un account di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="c9ed3-223">Avviare la shell di gestione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="c9ed3-224">Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione del servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="c9ed3-225">Il valore dell'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="c9ed3-226">Il valore nome servizio federativo può essere trovato nella console di gestione AD FS 2,0 facendo clic con il pulsante destro del mouse su **servizio** dal riquadro di spostamento e quindi selezionando **modifica proprietà servizio federativo**.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="c9ed3-227">Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="c9ed3-228">Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="c9ed3-229">Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disattivati nei servizi Web di Skype for business eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="c9ed3-230">Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="c9ed3-231">Configurazione del proxy</span><span class="sxs-lookup"><span data-stu-id="c9ed3-231">Proxy Configuration</span></span>

<span data-ttu-id="c9ed3-232">Quando l'autenticazione dei certificati è disattivata per i servizi Web di Skype for business, il client Skype for business utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per autenticare il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="c9ed3-233">L'autenticazione dei certificati è ancora necessaria per consentire al client di recuperare un ticket, tuttavia Kerberos e NTLM devono essere disattivati per il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="c9ed3-234">Nella procedura seguente viene descritto come creare una configurazione proxy personalizzata per i pool di server perimetrali, i pool Enterprise e gli Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="c9ed3-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="c9ed3-235">Per creare una configurazione proxy personalizzata</span><span class="sxs-lookup"><span data-stu-id="c9ed3-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="c9ed3-236">Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione proxy per ogni server Edge di Skype for Business Server, pool Enterprise e Standard Edition che verranno abilitati per l'autenticazione passiva tramite l'esecuzione dei seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="c9ed3-237">Verificare che tutti gli altri tipi di autenticazione proxy siano stati disabilitati eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9ed3-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="c9ed3-238">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9ed3-238">See also</span></span>

[<span data-ttu-id="c9ed3-239">Gestire l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9ed3-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="c9ed3-240">Utilizzare l'autenticazione a due fattori con il client Skype for business e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9ed3-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
