---
title: Gestibilità e strumenti di Skype Room System
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
description: Leggi questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805796"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="ec252-103">Gestibilità e strumenti di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="ec252-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="ec252-104">Leggi questo argomento per informazioni sugli strumenti di gestione per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="ec252-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="ec252-105">Portale amministrativo</span><span class="sxs-lookup"><span data-stu-id="ec252-105">Administrative Portal</span></span>

<span data-ttu-id="ec252-106">Per le distribuzioni locali di Skype for Business Server, è possibile utilizzare il portale amministrativo di Skype Room System per gestire e monitorare attivamente le distribuzioni di Skype Room System all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec252-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="ec252-107">Per ulteriori informazioni, vedere l'articolo seguente:</span><span class="sxs-lookup"><span data-stu-id="ec252-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="ec252-108">Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ec252-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="ec252-109">Elenco di controllo di Exchange</span><span class="sxs-lookup"><span data-stu-id="ec252-109">Exchange Checklist</span></span>

- <span data-ttu-id="ec252-110">Verificare che l'individuazione automatica sia impostata e che sia disponibile un RECORD A/CNAME DNS interno per autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="ec252-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="ec252-111">Individuazione automatica ping (ad esempio, ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ec252-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="ec252-112">Testare il servizio di individuazione automatica con Microsoft Connectivity Analyzer Tool.</span><span class="sxs-lookup"><span data-stu-id="ec252-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="ec252-113">Scegliere il primo test, "Non è possibile accedere con Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="ec252-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="ec252-114">Se la sala riunioni dispone già di una cassetta postale per le risorse, estendere questo account per Skype Room System (script di esempio nella parte inferiore della pagina).</span><span class="sxs-lookup"><span data-stu-id="ec252-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="ec252-115">Elenco di controllo di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ec252-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="ec252-116">Eseguire gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec252-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="ec252-117">Skype for Business Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="ec252-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="ec252-118">Strumento di analisi dell'integrità di Skype for Business (Excel)</span><span class="sxs-lookup"><span data-stu-id="ec252-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="ec252-119">Skype for Business Connectivity Analyzer a 32 bit o a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ec252-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="ec252-120">Rivedere [i nuovi strumenti utili per la risoluzione dei problemi e l'analisi di Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)</span><span class="sxs-lookup"><span data-stu-id="ec252-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="ec252-121">Verificare di disporre di un pool Skype for Business e di un server Office Web Apps e di poter condividere una presentazione di PowerPoint utilizzando il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="ec252-122">Se la sala riunioni dispone già di una cassetta postale per le risorse, abilitarla per Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="ec252-123">Se necessario, richiedere un DID (numero di telefono) per il sistema sala riunioni e aggiornare il campo Telefono generale nello strumento Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec252-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="ec252-124">Rete</span><span class="sxs-lookup"><span data-stu-id="ec252-124">Network</span></span>

- <span data-ttu-id="ec252-125">Assicurati di disporre di una connessione di rete cablata per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="ec252-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="ec252-126">Leggere la Guida alla pianificazione della rete per Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="ec252-127">Richiedere una valutazione di rete Skype for Business da un partner Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="ec252-128">Leggere i dati sulle prestazioni acquisiti nello strumento di analisi dell'integrità di Skype for Business (Excel).</span><span class="sxs-lookup"><span data-stu-id="ec252-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="ec252-129">Eseguire lo strumento di analisi della rete.</span><span class="sxs-lookup"><span data-stu-id="ec252-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="ec252-130">Eseguire lo strumento di diagnostica pre-chiamata.</span><span class="sxs-lookup"><span data-stu-id="ec252-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="ec252-131">Sicurezza del sistema skype room</span><span class="sxs-lookup"><span data-stu-id="ec252-131">Skype Room System Security</span></span>

<span data-ttu-id="ec252-132">Skype Room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, usando il modello di sicurezza, la gestione dei diritti e gli strumenti di gestione di Skype for Business come SCOM.</span><span class="sxs-lookup"><span data-stu-id="ec252-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="ec252-133">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="ec252-133">Features include:</span></span>
  
- <span data-ttu-id="ec252-134">Un filtro di scrittura per impedire scritture su disco in modalità utente</span><span class="sxs-lookup"><span data-stu-id="ec252-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="ec252-135">App Locker per impedire l'esecuzione di app non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="ec252-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="ec252-136">Tutte le porte USB sono disabilitate in modalità utente.</span><span class="sxs-lookup"><span data-stu-id="ec252-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="ec252-137">Nessuna app o visualizzatore standard si trova nell'hardware di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="ec252-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="ec252-138">Il rendering di tutto il contenuto viene eseguito tramite protocolli HTTP o RDP.</span><span class="sxs-lookup"><span data-stu-id="ec252-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="ec252-139">Il PC dell'applicazione esegue il sistema operativo Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="ec252-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="ec252-140">Tutti i componenti hardware, inclusi i dispositivi, sono forniti dai partner OEM.</span><span class="sxs-lookup"><span data-stu-id="ec252-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="ec252-141">Aggiunta facoltativa al dominio a Servizi di dominio Active Directory, abilitando la gestione e il controllo degli account di sicurezza locali.</span><span class="sxs-lookup"><span data-stu-id="ec252-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="ec252-142">Puoi anche gestire l'account amministratore locale usando l'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="ec252-143">Skype Room System viene aggiornato tramite i processi standard di Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="ec252-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="ec252-144">Skype Room System si connette con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="ec252-145">Skype for Business usa la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione</span><span class="sxs-lookup"><span data-stu-id="ec252-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="ec252-146">Skype Room System supporta gli standard di sicurezza e conformità di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="ec252-147">Per altre informazioni, vedere Pianificare la sicurezza [in Skype for Business Server.](../../plan-your-deployment/security/security.md)</span><span class="sxs-lookup"><span data-stu-id="ec252-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="ec252-148">License</span><span class="sxs-lookup"><span data-stu-id="ec252-148">License</span></span>

<span data-ttu-id="ec252-149">Verificare di utilizzare un servizio di gestione delle chiavi per l'attivazione del software.</span><span class="sxs-lookup"><span data-stu-id="ec252-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="ec252-150">In tal caso, potrebbe essere necessario controllare o aggiungere il codice KMS del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="ec252-151">Se non si usa il servizio di gestione delle chiavi, richiedere il codice "Product Key" per contratti multilicenza per il codice "Product Key" per attivazione attivazione programmi client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="ec252-152">Codici di licenza</span><span class="sxs-lookup"><span data-stu-id="ec252-152">License keys</span></span>

<span data-ttu-id="ec252-153">Skype Room System esegue il client desktop Skype for Business in background.</span><span class="sxs-lookup"><span data-stu-id="ec252-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="ec252-154">Se Skype Room System è un membro del dominio, scoprirà il servizio di gestione delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="ec252-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="ec252-155">(e se ha il codice Product Key del Servizio di gestione delle chiavi per contratti multilicenza, verrà attivato automaticamente).</span><span class="sxs-lookup"><span data-stu-id="ec252-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="ec252-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="ec252-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="ec252-157">È necessario l'accesso a Internet per l'attivazione tramite codice "Product Key" per attivazione attivazione ma non con il servizio di gestione delle chiavi(KMS).</span><span class="sxs-lookup"><span data-stu-id="ec252-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="ec252-158">Per ulteriori informazioni, vedere Volume activation of Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ec252-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="ec252-159">Per immettere il codice "Product Key" per attivazione programmi, passare a OEM Settings \> SRS Licensing Tool.</span><span class="sxs-lookup"><span data-stu-id="ec252-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="ec252-160">Fare clic su Controlla stato.</span><span class="sxs-lookup"><span data-stu-id="ec252-160">Click Check Status.</span></span> <span data-ttu-id="ec252-161">Quando lo stato indica che il prodotto non è attivato, immettere il codice.</span><span class="sxs-lookup"><span data-stu-id="ec252-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="ec252-162">Se durante l'attivazione viene visualizzato un messaggio di errore che indica che il codice Product Key non è valido nel Servizio gestione licenze software, verificare che:</span><span class="sxs-lookup"><span data-stu-id="ec252-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="ec252-163">Il tasto è stato immesso correttamente.</span><span class="sxs-lookup"><span data-stu-id="ec252-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="ec252-164">You entered the Skype for Business MAK key and not another key.</span><span class="sxs-lookup"><span data-stu-id="ec252-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="ec252-165">Il sistema ha accesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="ec252-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="ec252-166">È possibile eseguire l'attivazione tramite telefono, ma è necessario aver prima tentato di eseguire l'attivazione utilizzando lo strumento di gestione delle licenze SRS.</span><span class="sxs-lookup"><span data-stu-id="ec252-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="ec252-167">Per eseguire l'attivazione tramite telefono, avviare una riunione di prova (non una chiamata di prova perché troppo breve).</span><span class="sxs-lookup"><span data-stu-id="ec252-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="ec252-168">Nell'Attivazione guidata di Office selezionare Attivazione telefonica, chiamare Microsoft, digitare il numero lungo e immettere una risposta.</span><span class="sxs-lookup"><span data-stu-id="ec252-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="ec252-169">Autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="ec252-169">Certificate Authority</span></span>

<span data-ttu-id="ec252-170">Verificare che l'autorità di certificazione utilizzata per emettere il certificato di Office Web Apps Server 2013 abbia un percorso HTTP incluso nella proprietà Dell'elenco di revoche di certificati.</span><span class="sxs-lookup"><span data-stu-id="ec252-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="ec252-171">Importare il file di certificato (con estensione crt) nel sistema skype room se si usa Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ec252-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="ec252-172">È facilmente ottenuta dalla condivisione CertEnroll del server CA o nella cartella Radice attendibile di qualsiasi PC aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="ec252-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="ec252-173">Certificati</span><span class="sxs-lookup"><span data-stu-id="ec252-173">Certificates</span></span>

<span data-ttu-id="ec252-174">Verificare che l'autorità di certificazione abbia un percorso http per l'elenco di revoche di certificati.</span><span class="sxs-lookup"><span data-stu-id="ec252-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="ec252-175">In caso contrario, aggiornare l'autorità di certificazione per includerne una.</span><span class="sxs-lookup"><span data-stu-id="ec252-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="ec252-176">Installare i certificati nella configurazione dell'amministratore di Skype Room System in System Settings \> Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="ec252-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="ec252-177">È necessaria la CA radice dell'organizzazione per il certificato interno.</span><span class="sxs-lookup"><span data-stu-id="ec252-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="ec252-178">Un modo per ottenere i certificati necessari è individuare l'autorità di certificazione che ha emesso i certificati.</span><span class="sxs-lookup"><span data-stu-id="ec252-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="ec252-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span><span class="sxs-lookup"><span data-stu-id="ec252-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="ec252-180">Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni.</span><span class="sxs-lookup"><span data-stu-id="ec252-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="ec252-181">Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un report di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ec252-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="ec252-182">Fare clic su Visualizza certificati ed esaminare la proprietà punto di distribuzione CRL.</span><span class="sxs-lookup"><span data-stu-id="ec252-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="ec252-183">Il secondo parametro CN deve essere il nome del server dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="ec252-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="ec252-184">Apri Esplora risorse per l'indirizzo \\ \< CA Server Name \> \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="ec252-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="ec252-185">Copia i due file con estensione crl e crt in un'unità flash e inseriscilo nella parte sinistra della scheda SMART.</span><span class="sxs-lookup"><span data-stu-id="ec252-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="ec252-186">Importare il file con estensione crt in Skype Room System nella cartella Autorità di certificazione chat attendibile.</span><span class="sxs-lookup"><span data-stu-id="ec252-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="ec252-187">Importare i file con estensione crl in Skype Room System nella cartella Autorità di certificazione intermedie.</span><span class="sxs-lookup"><span data-stu-id="ec252-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="ec252-188">È necessario modificare il filtro delle estensioni di file in Gestione certificati in CRL per visualizzare i file.</span><span class="sxs-lookup"><span data-stu-id="ec252-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="ec252-189">Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ec252-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="ec252-190">Se non lo fa, non sarà possibile condividere PowerPoint in una riunione.</span><span class="sxs-lookup"><span data-stu-id="ec252-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="ec252-191">Verificare con l'IT e ottenere i file CRT e CRL dalla condivisione di rete CA CertEnroll, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ec252-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="ec252-192">L'appartenenza al dominio può semplificare alcuni aspetti perché è possibile considerare Skype Room System come un sistema Windows e può fare affidamento su Active Directory per alcuni degli aspetti del certificato.</span><span class="sxs-lookup"><span data-stu-id="ec252-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="ec252-193">Tuttavia, è meglio gestirlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="ec252-193">However, it's best to manually manage this.</span></span>
  

