---
title: Gestibilità e strumenti per Skype room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805796"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="ac71c-103">Gestibilità e strumenti per Skype room System</span><span class="sxs-lookup"><span data-stu-id="ac71c-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="ac71c-104">Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.</span><span class="sxs-lookup"><span data-stu-id="ac71c-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="ac71c-105">Portale amministrativo</span><span class="sxs-lookup"><span data-stu-id="ac71c-105">Administrative Portal</span></span>

<span data-ttu-id="ac71c-106">Per le distribuzioni locali di Skype for Business Server, è possibile utilizzare il portale di amministrazione di Skype room System per gestire e monitorare attivamente le distribuzioni del sistema room Skype all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac71c-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="ac71c-107">Per ulteriori informazioni, vedere l'articolo seguente:</span><span class="sxs-lookup"><span data-stu-id="ac71c-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="ac71c-108">Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ac71c-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="ac71c-109">Elenco di controllo di Exchange</span><span class="sxs-lookup"><span data-stu-id="ac71c-109">Exchange Checklist</span></span>

- <span data-ttu-id="ac71c-110">Verificare che l'individuazione automatica sia configurata e che sia disponibile un RECORD A/CNAME DNS interno per autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="ac71c-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="ac71c-111">Individuazione automatica ping (ad esempio, ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ac71c-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="ac71c-112">Testare il servizio di individuazione automatica con lo strumento Analizzatore connettività Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac71c-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="ac71c-113">Scegliere il primo test, "non è possibile accedere con Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="ac71c-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="ac71c-114">Se nella sala riunioni è già presente una cassetta postale per le risorse, estendere questo account per il sistema della sala Skype (script di esempio nella parte inferiore della pagina).</span><span class="sxs-lookup"><span data-stu-id="ac71c-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="ac71c-115">Elenco di controllo di Skype for business</span><span class="sxs-lookup"><span data-stu-id="ac71c-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="ac71c-116">Eseguire gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac71c-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="ac71c-117">Skype for Business Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="ac71c-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="ac71c-118">Strumento di analisi integrità di Skype for business (Excel)</span><span class="sxs-lookup"><span data-stu-id="ac71c-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="ac71c-119">Analizzatore della connettività di Skype for Business 32 bit o 64 bit</span><span class="sxs-lookup"><span data-stu-id="ac71c-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="ac71c-120">Esaminare [i nuovi strumenti di analisi e risoluzione dei problemi utili per Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="ac71c-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="ac71c-121">Conferma di disporre di un pool Skype for business e di un server Office Web Apps e può condividere un deck di PowerPoint utilizzando il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="ac71c-122">Se nella sala riunioni è già presente una cassetta postale per le risorse, abilitarla per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="ac71c-123">Se necessario, richiedere un DID (numero di telefono) per il sistema sala riunioni e aggiornare il campo telefono generale nello strumento Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac71c-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="ac71c-124">Rete</span><span class="sxs-lookup"><span data-stu-id="ac71c-124">Network</span></span>

- <span data-ttu-id="ac71c-125">Assicurarsi di disporre di una connessione di rete cablata per il sistema di chat in Skype room.</span><span class="sxs-lookup"><span data-stu-id="ac71c-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="ac71c-126">Leggere la guida alla pianificazione della rete per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="ac71c-127">Richiedere una valutazione della rete Skype for business da un partner di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="ac71c-128">Leggere i dati sulle prestazioni acquisiti nello strumento di analisi dell'integrità di Skype for business (Excel).</span><span class="sxs-lookup"><span data-stu-id="ac71c-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="ac71c-129">Eseguire lo strumento di analisi della rete.</span><span class="sxs-lookup"><span data-stu-id="ac71c-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="ac71c-130">Eseguire lo strumento di diagnostica prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac71c-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="ac71c-131">Sicurezza del sistema delle chat room Skype</span><span class="sxs-lookup"><span data-stu-id="ac71c-131">Skype Room System Security</span></span>

<span data-ttu-id="ac71c-132">Skype room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, usando il modello di sicurezza di Skype for business, la gestione dei diritti e gli strumenti di gestione, ad esempio SCOM.</span><span class="sxs-lookup"><span data-stu-id="ac71c-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="ac71c-133">Le caratteristiche includono:</span><span class="sxs-lookup"><span data-stu-id="ac71c-133">Features include:</span></span>
  
- <span data-ttu-id="ac71c-134">Filtro di scrittura per impedire la scrittura su disco in modalità utente</span><span class="sxs-lookup"><span data-stu-id="ac71c-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="ac71c-135">App Locker per impedire l'esecuzione di app non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="ac71c-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="ac71c-136">Tutte le porte USB sono disattivate in modalità utente.</span><span class="sxs-lookup"><span data-stu-id="ac71c-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="ac71c-137">Nessuna app standard o visualizzatori risiedono nell'hardware del sistema Skype room.</span><span class="sxs-lookup"><span data-stu-id="ac71c-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="ac71c-138">Viene eseguito il rendering di tutti i contenuti tramite protocolli HTTP o RDP.</span><span class="sxs-lookup"><span data-stu-id="ac71c-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="ac71c-139">Il PC del dispositivo esegue il sistema operativo Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="ac71c-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="ac71c-140">Tutto l'hardware, inclusi i dispositivi, è fornito dai partner OEM.</span><span class="sxs-lookup"><span data-stu-id="ac71c-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="ac71c-141">Join di dominio facoltativo a servizi di dominio Active Directory, abilitazione del controllo e gestione degli account di sicurezza locali.</span><span class="sxs-lookup"><span data-stu-id="ac71c-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="ac71c-142">È inoltre possibile gestire l'account amministratore locale utilizzando l'interfaccia di amministrazione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="ac71c-143">Skype room System viene aggiornato tramite i processi di aggiornamento standard di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac71c-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="ac71c-144">Skype for business è connesso al sistema di chat room.</span><span class="sxs-lookup"><span data-stu-id="ac71c-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="ac71c-145">Skype for business utilizza la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione</span><span class="sxs-lookup"><span data-stu-id="ac71c-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="ac71c-146">Skype room System supporta gli standard di sicurezza e conformità di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="ac71c-147">Per ulteriori informazioni, vedere [pianificare la sicurezza in Skype for Business Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="ac71c-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="ac71c-148">License</span><span class="sxs-lookup"><span data-stu-id="ac71c-148">License</span></span>

<span data-ttu-id="ac71c-149">Verificare di utilizzare un servizio di gestione delle chiavi per l'attivazione del software.</span><span class="sxs-lookup"><span data-stu-id="ac71c-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="ac71c-150">In caso affermativo, potrebbe essere necessario controllare o aggiungere la chiave del servizio di gestione delle chiavi del client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="ac71c-151">Se non si utilizza il servizio di gestione delle chiavi, richiedere la chiave per contratti multilicenza per il MAK client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="ac71c-152">Codici di licenza</span><span class="sxs-lookup"><span data-stu-id="ac71c-152">License keys</span></span>

<span data-ttu-id="ac71c-153">Skype room System esegue il client desktop Skype for business in background.</span><span class="sxs-lookup"><span data-stu-id="ac71c-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="ac71c-154">Se Skype room System è un membro del dominio, verrà individuato il servizio di gestione delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="ac71c-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="ac71c-155">Se si dispone del tasto di gestione delle licenze per contratti multilicenza, verrà attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac71c-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="ac71c-156">Contratti multilicenza fornisce anche un codice MAK, che viene immesso come visualizzato come xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="ac71c-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="ac71c-157">(È necessario l'accesso a Internet per l'attivazione tramite MAK ma non il servizio di gestione delle chiavi).</span><span class="sxs-lookup"><span data-stu-id="ac71c-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="ac71c-158">Per ulteriori informazioni, vedere Volume Activation of Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ac71c-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="ac71c-159">Per immettere il codice "MAK key", andare a impostazioni OEM \> SRS Licensing Tool.</span><span class="sxs-lookup"><span data-stu-id="ac71c-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="ac71c-160">Fare clic su Controlla stato.</span><span class="sxs-lookup"><span data-stu-id="ac71c-160">Click Check Status.</span></span> <span data-ttu-id="ac71c-161">Quando lo stato indica che "il prodotto non è attivato", immettere il tasto.</span><span class="sxs-lookup"><span data-stu-id="ac71c-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="ac71c-162">Se durante l'attivazione viene visualizzato un messaggio di errore che indica che "' il servizio di gestione delle licenze software ha riferito che il codice Product Key non è valido", verificare che:</span><span class="sxs-lookup"><span data-stu-id="ac71c-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="ac71c-163">Il tasto è stato immesso correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac71c-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="ac71c-164">È stato immesso il codice MAK di Skype for business e non un altro tasto.</span><span class="sxs-lookup"><span data-stu-id="ac71c-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="ac71c-165">Il sistema dispone di accesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="ac71c-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="ac71c-166">È possibile attivarlo tramite telefono, ma è necessario tentare di attivarlo prima usando lo strumento di gestione delle licenze SRS.</span><span class="sxs-lookup"><span data-stu-id="ac71c-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="ac71c-167">Per attivare tramite telefono, avviare una riunione di prova (non una chiamata di prova che è troppo breve).</span><span class="sxs-lookup"><span data-stu-id="ac71c-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="ac71c-168">Nella procedura guidata di attivazione di Office, selezionare Attivazione telefono, chiamare Microsoft, digitare il numero lungo e immettere una risposta.</span><span class="sxs-lookup"><span data-stu-id="ac71c-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="ac71c-169">Autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="ac71c-169">Certificate Authority</span></span>

<span data-ttu-id="ac71c-170">Confermare che l'autorità di certificazione utilizzata per rilasciare il certificato di Office Web Apps Server 2013 disponga di un percorso HTTP incluso nella proprietà dell'elenco di revoche di certificati.</span><span class="sxs-lookup"><span data-stu-id="ac71c-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="ac71c-171">Importare il file di certificato (con estensione CRT) in Skype room System se si utilizza Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac71c-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="ac71c-172">È facilmente reperibile dalla condivisione CertEnroll del server CA o nella cartella radice attendibile di qualsiasi dominio aggiunto al PC.</span><span class="sxs-lookup"><span data-stu-id="ac71c-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="ac71c-173">Certificati</span><span class="sxs-lookup"><span data-stu-id="ac71c-173">Certificates</span></span>

<span data-ttu-id="ac71c-174">Verificare che l'autorità di certificazione disponga di un percorso http per l'elenco di revoche di certificati.</span><span class="sxs-lookup"><span data-stu-id="ac71c-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="ac71c-175">In caso contrario, aggiornare l'autorità di certificazione per includerne una.</span><span class="sxs-lookup"><span data-stu-id="ac71c-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="ac71c-176">Installare i certificati nel programma di installazione di amministrazione del sistema della sala Skype in Gestione certificati delle impostazioni di sistema \> .</span><span class="sxs-lookup"><span data-stu-id="ac71c-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="ac71c-177">È necessaria la CA radice dell'organizzazione per il certificato interno.</span><span class="sxs-lookup"><span data-stu-id="ac71c-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="ac71c-178">Un modo per ottenere i certificati necessari consiste nell'individuare l'autorità di certificazione che ha emesso i certificati.</span><span class="sxs-lookup"><span data-stu-id="ac71c-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="ac71c-179">Per Skype for Business Server, su un PC in Skype for business, fare clic su impostazioni \> \> conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ac71c-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="ac71c-180">Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni.</span><span class="sxs-lookup"><span data-stu-id="ac71c-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="ac71c-181">Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un rapporto sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ac71c-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="ac71c-182">Fare clic su Visualizza certificati ed esaminare la proprietà del punto di distribuzione CRL.</span><span class="sxs-lookup"><span data-stu-id="ac71c-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="ac71c-183">Il secondo parametro CN deve corrispondere al nome del server dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="ac71c-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="ac71c-184">Ora aprire Esplora risorse per l'indirizzo \\ \< CA Server Name \> \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="ac71c-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="ac71c-185">Copiare i due file con estensione CRL e il file. CRT in un'unità flash e posizionarlo sul lato sinistro della scheda SMART.</span><span class="sxs-lookup"><span data-stu-id="ac71c-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="ac71c-186">Importare il file. CRT in Skype room System sotto la cartella Trusted room Certification Authority.</span><span class="sxs-lookup"><span data-stu-id="ac71c-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="ac71c-187">Importare i file con estensione CRL su Skype room System sotto la cartella autorità di certificazione intermedie.</span><span class="sxs-lookup"><span data-stu-id="ac71c-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="ac71c-188">(È necessario modificare il filtro dell'estensione di file in Gestione certificati in. CRL per visualizzare i file).</span><span class="sxs-lookup"><span data-stu-id="ac71c-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="ac71c-189">Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ac71c-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="ac71c-190">In caso contrario, non sarà possibile condividere PowerPoint in una riunione.</span><span class="sxs-lookup"><span data-stu-id="ac71c-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="ac71c-191">Controllare con esso e ottenere i file CRT e CRL dalla rete di condivisione CertEnroll come spiegato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ac71c-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="ac71c-192">L'appartenenza al dominio è in grado di semplificare alcuni aspetti perché è possibile gestire il sistema delle sale Skype come sistema di Windows e può essere affidato ad Active Directory per alcuni dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="ac71c-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="ac71c-193">Tuttavia, è preferibile gestirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="ac71c-193">However, it's best to manually manage this.</span></span>
  

