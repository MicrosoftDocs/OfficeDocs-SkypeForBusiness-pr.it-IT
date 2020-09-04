---
title: Risolvere i problemi relativi alla distribuzione di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Risoluzione dei problemi relativi alla distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359332"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="41a01-103">Risolvere i problemi relativi alla distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="41a01-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="41a01-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="41a01-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="41a01-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="41a01-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="41a01-106">Risoluzione dei problemi relativi alla distribuzione di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="41a01-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="41a01-107">In questo argomento vengono descritte le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="41a01-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="41a01-108">Se si verificano problemi con le chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile indagare seguendo le soluzioni descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="41a01-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="41a01-109">Il connettore Cloud fornisce meccanismi incorporati per la risoluzione automatica di alcuni problemi.</span><span class="sxs-lookup"><span data-stu-id="41a01-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="41a01-110">Un processo di rilevamento automatico consente di individuare eventuali problemi con gli apparecchi dei connettori cloud e, se possibile, di eseguire azioni correttive per risolvere tali problemi senza l'intervento dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="41a01-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="41a01-111">Il processo di rilevamento funziona come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a01-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="41a01-112">**Sequenza di rilevamento:** Il servizio di gestione Cloud Connector esegue un processo ogni 60 secondi per rilevare se un dispositivo è inattivo.</span><span class="sxs-lookup"><span data-stu-id="41a01-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="41a01-113">In Cloud Connector versione 2,0 e versioni successive, il processo di rilevamento utilizza l'opzione Corpnet di Skype for business per rendere le connessioni di PowerShell ai computer dei connettori cloud; per le versioni precedenti a 2,0, il processo di rilevamento utilizza l'opzione di gestione dei connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="41a01-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41a01-114">Affinché il ripristino automatico abbia esito positivo, è necessario che vi sia connettività di rete tra l'host e le macchine virtuali tramite l'opzione di rete host.</span><span class="sxs-lookup"><span data-stu-id="41a01-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="41a01-115">Assicurarsi di controllare la connettività di rete per garantire che il rilevamento automatico e il ripristino possano avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="41a01-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="41a01-116">**Monitoraggio:** I servizi seguenti sono monitorati in Cloud Connector versione 2,0 e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="41a01-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="41a01-117">Le macchine virtuali non sono connesse ai commutatori virtuali Corporate o Internet del connettore Cloud</span><span class="sxs-lookup"><span data-stu-id="41a01-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="41a01-118">Le macchine virtuali si trovano in uno stato salvato o interrotto</span><span class="sxs-lookup"><span data-stu-id="41a01-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="41a01-119">Servizi server di gestione centrale: REPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="41a01-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="41a01-120">Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="41a01-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="41a01-121">Servizi server perimetrali: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="41a01-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="41a01-122">Le regole del firewall in ingresso sono disattivate per CS RTCSRV sul server perimetrale, CS RTCMEDSRV su Mediation Server</span><span class="sxs-lookup"><span data-stu-id="41a01-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="41a01-123">In Cloud Connector versione 1.4.2 sono monitorati solo i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="41a01-124">Servizi Mediation Server: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="41a01-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="41a01-125">Servizio server perimetrale: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="41a01-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="41a01-126">**Processo di ripristino:** Se i servizi monitorati sono indesiderati, un dispositivo è segnato verso il basso e i servizi vengono interrotti e contrassegnati manualmente fino a quando non è possibile risolvere tutti i problemi.</span><span class="sxs-lookup"><span data-stu-id="41a01-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="41a01-127">In questo modo si eviteranno le chiamate dal routing a un dispositivo che potrebbe causare errori di chiamata.</span><span class="sxs-lookup"><span data-stu-id="41a01-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="41a01-128">Il servizio di gestione Cloud Connector ritenterà il ripristino automatico come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="41a01-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="41a01-129">L'intervallo di tentativi iniziale è ogni dieci secondi con un intervallo di tempo massimo di un'ora.</span><span class="sxs-lookup"><span data-stu-id="41a01-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="41a01-130">Per i primi tre tentativi di ripristino, l'intervallo di tempo è di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="41a01-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="41a01-131">A partire dal quarto tentativo, il tempo di intervallo aumenta di due volte l'intervallo di tempo precedente.</span><span class="sxs-lookup"><span data-stu-id="41a01-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="41a01-132">Ad esempio, il quarto Riprova si verificherà tra 20 secondi, il quinto in 40 secondi e così via.</span><span class="sxs-lookup"><span data-stu-id="41a01-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="41a01-133">Quando il tempo massimo di intervallo di un'ora viene raggiunto, i tentativi continueranno una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="41a01-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="41a01-134">Quando il ripristino ha esito positivo, i conteggi dell'intervallo e dei tentativi sono impostati sui valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="41a01-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="41a01-135">Se il servizio di gestione viene riavviato, i conteggi dell'intervallo e dei tentativi vengono reimpostati sui valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="41a01-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="41a01-136">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="41a01-136">Troubleshooting</span></span>

<span data-ttu-id="41a01-137">Di seguito sono riportate le soluzioni ai problemi comunemente riscontrati:</span><span class="sxs-lookup"><span data-stu-id="41a01-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="41a01-138">**Problema: la distribuzione ha esito negativo o si blocca durante l'esecuzione degli script di distribuzione. Dopo aver eseguito l'accesso a ogni VM, l'indirizzo IP è mancante o non corretto per la scheda di gestione/interno/esterno.**</span><span class="sxs-lookup"><span data-stu-id="41a01-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="41a01-139">**Soluzione:** Questo problema non può essere risolto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="41a01-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="41a01-140">Le schede NIC non possono essere aggiunte alle macchine virtuali mentre sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="41a01-141">Chiudere e rimuovere le macchine virtuali in gestione Hyper-v, quindi eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="41a01-142">**Problema: dopo l'installazione del server e della foresta di Active Directory, il server CMS e/o il Mediation Server non hanno partecipato correttamente al dominio.**</span><span class="sxs-lookup"><span data-stu-id="41a01-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="41a01-143">**Soluzione:** Per risolvere il problema, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="41a01-144">Accedere al server Active Directory e verificare che il dominio sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="41a01-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="41a01-145">Accedere a CMS/Mediation Server e verificare che nella scheda NIC di corpnet sia assegnato un indirizzo IP valido e che l'indirizzo IP e il DNS statici validi siano configurati come indirizzi IP del server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41a01-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="41a01-146">Accedere a CMS/Mediation Server e aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="41a01-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="41a01-147">Verificare che sia possibile eseguire il ping del nome di dominio completo e dell'indirizzo IP del server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41a01-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="41a01-148">Se non è possibile, potrebbe essere presente un conflitto di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="41a01-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="41a01-149">Provare a assegnare un nuovo IP per Active Directory e aggiornare il DNS su CMS/Mediation Server di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="41a01-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="41a01-150">**Problema: viene visualizzato il messaggio di errore "Remove-VMSwitch: failed durante la rimozione dello switch Ethernet virtuale. Lo switch virtuale ' switch di gestione dei connettori cloud ' non può essere eliminato perché viene utilizzato eseguendo macchine virtuali o assegnato ai pool di bambini.**</span><span class="sxs-lookup"><span data-stu-id="41a01-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="41a01-151">**Soluzione:** L'opzione "gestione dei connettori cloud" non è stata eliminata dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="41a01-152">Se si preme questo errore, visitare il sito di gestione di Hyper-v e verificare che non vi sia ancora una macchina virtuale ancora connessa.</span><span class="sxs-lookup"><span data-stu-id="41a01-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="41a01-153">Se sono ancora connesse macchine virtuali, disconnetterle ed eliminare l'opzione di gestione.</span><span class="sxs-lookup"><span data-stu-id="41a01-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="41a01-154">Se non è ancora possibile eliminare l'opzione di gestione, riavviare il server host e riprovare.</span><span class="sxs-lookup"><span data-stu-id="41a01-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="41a01-155">**Problema: viene visualizzato il messaggio di errore "Service RTCMRAUTH non è stato avviato. Verificare che il servizio non sia disabilitato. "**</span><span class="sxs-lookup"><span data-stu-id="41a01-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41a01-156">Questo problema si applica solo alle versioni dei connettori cloud precedenti a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="41a01-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="41a01-157">L'errore di avvio potrebbe anche essere dovuto al fatto che in precedenza questo server front-end non è stato eseguito correttamente (utilizzando il failover del computer).</span><span class="sxs-lookup"><span data-stu-id="41a01-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="41a01-158">In questo caso, è consigliabile richiamare il failback (con il failback del computer).</span><span class="sxs-lookup"><span data-stu-id="41a01-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="41a01-159">**Soluzione:** Questo problema si verifica su un server perimetrale quando il certificato CA radice o il certificato CA intermedio non è considerato attendibile dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41a01-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="41a01-160">Anche se il certificato esterno può essere importato, ma la catena di certificati è interrotta.</span><span class="sxs-lookup"><span data-stu-id="41a01-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="41a01-161">In questa condizione, il servizio RTCMRAUTH e/o RTCSRV non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="41a01-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="41a01-162">Importare manualmente il certificato della CA radice e tutti i certificati di CA intermedi del certificato esterno nel server perimetrale e quindi riavviare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41a01-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="41a01-163">Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:</span><span class="sxs-lookup"><span data-stu-id="41a01-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="41a01-164">**Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate servite dal server sono in errore.**</span><span class="sxs-lookup"><span data-stu-id="41a01-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="41a01-165">**Soluzione:** Se è stato distribuito un ambiente a disponibilità elevata, Microsoft fornisce un cmdlet che consente di spostare un computer host (istanza di distribuzione) all'interno o all'esterno della topologia corrente quando si controlla e si installa Windows Update manualmente.</span><span class="sxs-lookup"><span data-stu-id="41a01-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="41a01-166">Per ottenere questo risultato, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="41a01-167">Nel server host avviare una console di PowerShell come amministratore e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="41a01-168">Controllare se sono disponibili aggiornamenti e installarli.</span><span class="sxs-lookup"><span data-stu-id="41a01-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="41a01-169">Nella console PowerShell, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="41a01-170">**Problema: quando viene effettuata una chiamata da un client Skype for business utilizzando un numero PSTN, la chiamata non può essere inoltrata a una conferenza invitando un altro numero PSTN.**</span><span class="sxs-lookup"><span data-stu-id="41a01-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="41a01-171">**Soluzione:** Per risolvere il problema, vedere [Configure online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="41a01-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="41a01-172">**Problema: viene visualizzato un messaggio di avviso relativo all'installazione di Windows Update quando si installa Active Directory Server-"l'aggiornamento automatico di Windows non è abilitato. Per assicurarsi che il ruolo o la caratteristica appena installata venga aggiornata automaticamente, attiva Windows Update. "**</span><span class="sxs-lookup"><span data-stu-id="41a01-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="41a01-173">**Soluzione:** Avviare una sessione di PowerShell remote tenant con le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per controllare la configurazione di _EnableAutoUpdate_ del sito:</span><span class="sxs-lookup"><span data-stu-id="41a01-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="41a01-174">Se  _EnableAutoUpdate_ è impostato su **true**, è possibile ignorare il messaggio di avviso in modo sicuro perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali sia per il server host.</span><span class="sxs-lookup"><span data-stu-id="41a01-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="41a01-175">Se  _EnableAutoUpdate_ è impostato su **false**, eseguire il cmdlet seguente per impostarlo su **true**.</span><span class="sxs-lookup"><span data-stu-id="41a01-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="41a01-176">In alternativa, è possibile cercare e installare manualmente gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="41a01-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="41a01-177">Vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="41a01-177">See the next section.</span></span>
    
- <span data-ttu-id="41a01-178">**Problema: viene visualizzato un messaggio di errore: non è possibile registrare l'accessorio perché l'input/configurazione corrente o o o i \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> conflitti con gli apparecchi esistenti. Rimuovere un dispositivo di conflitto o aggiornare le informazioni di input/configurazione e quindi registrarsi di nuovo. ' quando si esegue Register-CcAppliance per registrare l'accessorio corrente in linea.**</span><span class="sxs-lookup"><span data-stu-id="41a01-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="41a01-179">**Soluzione:** Valori per l' \<ApplianceName\> \<Mediation Server FQDN\> e \<Mediation Server IP Address\> deve essere univoco e utilizzato solo per la registrazione di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="41a01-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="41a01-180">Per impostazione predefinita, \<ApplianceName\> deriva dal nome host.</span><span class="sxs-lookup"><span data-stu-id="41a01-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="41a01-181">\<Mediation Server FQDN\> e \<Mediation Server IP Address\> definito nel file ini di configurazione.</span><span class="sxs-lookup"><span data-stu-id="41a01-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="41a01-182">Ad esempio, utilizzando (Appliancename = MyserverNew, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10) per la registrazione a sitename = sito, ma se è presente un dispositivo registrato (Appliancename = MyServer, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10), si avrà il conflitto.</span><span class="sxs-lookup"><span data-stu-id="41a01-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="41a01-183">Per prima cosa, controllare il file CloudConnector.ini nella sezione Directory di ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="41a01-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="41a01-184">Otterrete \<SiteName\> \<Mediation Server FQDN\> e \<Mediation Server IP Address\> i valori nel file.</span><span class="sxs-lookup"><span data-stu-id="41a01-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="41a01-185">\<ApplianceName\> è il nome del server host.</span><span class="sxs-lookup"><span data-stu-id="41a01-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="41a01-186">In secondo luogo, avviare tenant Remote PowerShell usando le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per controllare gli apparecchi registrati.</span><span class="sxs-lookup"><span data-stu-id="41a01-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="41a01-187">Dopo aver identificato i conflitti, è possibile aggiornare il file di CloudConnector.ini con le informazioni corrispondenti all'apparecchio registrato oppure annullare la registrazione dell'accessorio esistente per risolvere i conflitti.</span><span class="sxs-lookup"><span data-stu-id="41a01-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="41a01-188">**Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se è in esecuzione un dispositivo distribuito nell'host.**</span><span class="sxs-lookup"><span data-stu-id="41a01-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="41a01-189">**Soluzione:** Ciò può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="41a01-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="41a01-190">Dopo aver installato la versione 1.4.1 con il. msi, è necessario eseguire `Register-CcAppliance` prima di eseguire qualsiasi altro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41a01-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="41a01-191">`Register-CcAppliance` eseguirà la migrazione del file module.ini da%UserProfile%\CloudConnector a%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="41a01-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="41a01-192">In caso di mancato recapito, verrà creata una nuova module.ini nella cartella%ProgramData%\CloudConnector e verranno sostituite le informazioni sulla versione di esecuzione/backup per 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="41a01-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="41a01-193">Confrontare i file module.ini nella cartella%UserProfile%\CloudConnector e%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="41a01-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="41a01-194">Se sono presenti differenze, eliminare il file module.ini in%ProgramData%\CloudConnector e rieseguire  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="41a01-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="41a01-195">È inoltre possibile modificare manualmente il file nella versione di backup e esecuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="41a01-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="41a01-196">**Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione dello script corrente, non è disponibile alcun supporto per la disponibilità elevata per questa versione precedente.**</span><span class="sxs-lookup"><span data-stu-id="41a01-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="41a01-197">**Soluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="41a01-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="41a01-198">La versione corrente dello script, che può essere determinata dall'esecuzione `Get-CcVersion` , e la versione in esecuzione, che può essere determinata eseguendo,  `Get-CcRunningVersion` sono entrambe 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="41a01-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="41a01-199">In questo momento, se si esegue `Switch-CcVersion` per cambiare la versione in esecuzione di nuovo a 1.4.1, quindi non vi sarà alcun supporto per la disponibilità elevata per questa versione precedente.</span><span class="sxs-lookup"><span data-stu-id="41a01-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="41a01-200">Per ottenere un supporto completo per la disponibilità elevata, tornare a 1.4.2, quindi la versione in esecuzione e la versione script sono uguali.</span><span class="sxs-lookup"><span data-stu-id="41a01-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="41a01-201">Se si verificano problemi con la distribuzione di 1.4.2, disinstallare e reinstallare il più presto possibile.</span><span class="sxs-lookup"><span data-stu-id="41a01-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="41a01-202">**Problema: i certificati dell'autorità di certificazione o i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono quasi scaduti o sono compromessi.**</span><span class="sxs-lookup"><span data-stu-id="41a01-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="41a01-203">**Soluzione:** I certificati dell'autorità di certificazione Skype for business sono validi per cinque anni.</span><span class="sxs-lookup"><span data-stu-id="41a01-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="41a01-204">I certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni.</span><span class="sxs-lookup"><span data-stu-id="41a01-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41a01-205">In Cloud Connector versione 2,0 e versioni successive, il cmdlet Renew-CcServerCertificate è stato modificato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è stato modificato in Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="41a01-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="41a01-206">Se i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono vicini alla scadenza o sono compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="41a01-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="41a01-207">Se i certificati dell'autorità di certificazione sono vicini alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="41a01-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="41a01-208">**Se i certificati dell'autorità di certificazione sono compromessi ed è presente un solo dispositivo nel sito,** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="41a01-209">Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire l'accessorio in modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="41a01-210">Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:</span><span class="sxs-lookup"><span data-stu-id="41a01-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="41a01-211">Per i rilasci dei connettori cloud prima 2,0:</span><span class="sxs-lookup"><span data-stu-id="41a01-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="41a01-212">O per il connettore Cloud Release 2,0 e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="41a01-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="41a01-213">Se si utilizza TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate dall'accessorio e quindi installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="41a01-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="41a01-214">È inoltre possibile che venga richiesto di riemettere il certificato nel gateway.</span><span class="sxs-lookup"><span data-stu-id="41a01-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="41a01-215">Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="41a01-216">**Se i certificati dell'autorità di certificazione sono compromessi e sono presenti più dispositivi nel sito,** eseguire i passaggi sequenziali seguenti in ogni accessorio del sito.</span><span class="sxs-lookup"><span data-stu-id="41a01-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="41a01-217">Microsoft consiglia di eseguire questi passaggi durante i periodi di utilizzo non di picco.</span><span class="sxs-lookup"><span data-stu-id="41a01-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="41a01-218">Sul primo dispositivo, eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella \<SiteRoot\> Directory.</span><span class="sxs-lookup"><span data-stu-id="41a01-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="41a01-219">Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire ogni dispositivo in modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="41a01-220">Sul primo dispositivo, eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:</span><span class="sxs-lookup"><span data-stu-id="41a01-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="41a01-221">Per i rilasci dei connettori cloud prima 2,0:</span><span class="sxs-lookup"><span data-stu-id="41a01-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="41a01-222">O per il connettore Cloud Release 2,0 e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="41a01-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="41a01-223">Sul primo dispositivo, eseguire il seguente cmdlet per eseguire il backup dei file della CA nella \<SiteRoot\> cartella.</span><span class="sxs-lookup"><span data-stu-id="41a01-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="41a01-224">In tutti gli altri dispositivi nello stesso sito, eseguire i seguenti comandi per utilizzare i file di backup della CA, in modo che tutti gli elettrodomestici utilizzino lo stesso certificato radice e quindi richiedere nuovi certificati.</span><span class="sxs-lookup"><span data-stu-id="41a01-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="41a01-225">Se si utilizza TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate da qualsiasi accessorio del sito e quindi installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="41a01-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="41a01-226">È inoltre possibile che venga richiesto di riemettere il certificato nel gateway.</span><span class="sxs-lookup"><span data-stu-id="41a01-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="41a01-227">Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="41a01-228">**Problema: viene visualizzato il messaggio di errore seguente nel registro del servizio di gestione Cloud Connector, "C:\Program Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: Unexpected exception when Reporting status to online: System. Management. Automation. CmdletInvocationException: logon failed for the user \<Global Tenant Admin\> . Creare un nuovo oggetto Credential, assicurandosi di aver utilizzato il nome utente e la password corretti. ---\>**</span><span class="sxs-lookup"><span data-stu-id="41a01-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="41a01-229">**Soluzione:** Le credenziali di amministratore del tenant globale di Microsoft 365 o Office 365 sono state modificate dopo la registrazione dell'accessorio Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="41a01-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="41a01-230">Per aggiornare le credenziali memorizzate localmente nell'accessorio Cloud Connector, eseguire le operazioni seguenti dall'amministratore PowerShell nell'accessorio host:</span><span class="sxs-lookup"><span data-stu-id="41a01-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="41a01-231">**Problema: dopo aver modificato la password per l'account del server host utilizzato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString: Key non valido per l'utilizzo nello stato specificato." in%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="41a01-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="41a01-232">**Soluzione:** Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="41a01-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="41a01-233">Quando la password sul server host cambia, sarà necessario aggiornare le credenziali memorizzate localmente.</span><span class="sxs-lookup"><span data-stu-id="41a01-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="41a01-234">**Se si esegue il Cloud Connector versione 1.4.2,** rigenerare tutte le password dei connettori cloud attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="41a01-235">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="41a01-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="41a01-236">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="41a01-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="41a01-237">Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="41a01-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="41a01-238">Immettere le stesse password immesse prima per la distribuzione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="41a01-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="41a01-239">**Se si esegue il Cloud Connector versione 2,0 o successiva,** rigenerare tutte le password dei connettori cloud attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="41a01-240">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="41a01-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="41a01-241">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="41a01-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="41a01-242">Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="41a01-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="41a01-243">Se il file della password memorizzato nella cache è stato generato con Cloud Connector versione 1.4.2, utilizzare la password di VMAdmin per la password di CceService quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="41a01-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="41a01-244">Immettere la stessa password immessa prima per la distribuzione del connettore Cloud per tutti gli altri account.</span><span class="sxs-lookup"><span data-stu-id="41a01-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="41a01-245">Se il file della password memorizzato nella cache è stato generato con il connettore Cloud versione 1.4.2 e le password di DomainAdmin e VMAdmin sono diverse, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="41a01-246">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a01-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="41a01-247">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="41a01-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="41a01-248">Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di DomainAdmin utilizzata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41a01-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="41a01-249">Se il file della password memorizzato nella cache è stato generato con il connettore Cloud versione 2,0 o successiva, per impostazione predefinita VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="41a01-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="41a01-250">Se sono state modificate le password di DomainAdmin e VMAdmin, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="41a01-251">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a01-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="41a01-252">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService</span><span class="sxs-lookup"><span data-stu-id="41a01-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="41a01-253">Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di DomainAdmin utilizzata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41a01-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="41a01-254">Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a01-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="41a01-255">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService</span><span class="sxs-lookup"><span data-stu-id="41a01-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="41a01-256">Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di VmAdmin utilizzata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41a01-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="41a01-257">**Problema: con il connettore Cloud versione 2,1 e versioni successive, quando si esegue Register-CcAppliance o altri cmdlet sull'accessorio, viene visualizzato un messaggio di errore, ad esempio: "per ogni oggetto: la proprietà' Common ' non può essere trovata su questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="41a01-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="41a01-258">**Soluzione:** Il connettore Cloud 2,1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="41a01-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="41a01-259">Aggiornare .NET Framework nell'accessorio alla versione 4.6.1 o successive ed eseguire di nuovo i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41a01-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="41a01-260">**Problema: con Cloud Connector Edition 2,1, durante l'esecuzione di install-CcAppliance, viene visualizzato un messaggio di errore, ad esempio: "Impossibile installare una nuova istanza con errore: Impossibile impostare" stato "perché solo le stringhe possono essere utilizzate come valori per impostare le Proprietà XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="41a01-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="41a01-261">**Soluzione:** In Cloudconnector.ini, nella sezione [Common], aggiungere il file di configurazione "state" come indicato di seguito: CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="41a01-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="41a01-262">Non è obbligatorio che la riga "state" abbia valore, ma la riga "state" non può essere rimossa dal file Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="41a01-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="41a01-263">**Problema: viene visualizzato il seguente messaggio di errore "Dismount-WindowsImage: Dismount-WindowsImage failed. Codice di errore = 0xc1550115 "durante l'installazione o l'aggiornamento di Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="41a01-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="41a01-264">**Soluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM-Cleanup-Wim '".</span><span class="sxs-lookup"><span data-stu-id="41a01-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="41a01-265">In questo modo vengono ripulite tutte le immagini problematiche.</span><span class="sxs-lookup"><span data-stu-id="41a01-265">This will clean up all troubled images.</span></span> <span data-ttu-id="41a01-266">Eseguire di nuovo install-CcAppliance oppure attendere l'aggiornamento automatico dei bit.</span><span class="sxs-lookup"><span data-stu-id="41a01-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="41a01-267">**Problema: la distribuzione del primo accessorio Cloud Connector in un ambiente HA HA esito negativo**</span><span class="sxs-lookup"><span data-stu-id="41a01-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="41a01-268">**Soluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non ha avuto esito positivo:</span><span class="sxs-lookup"><span data-stu-id="41a01-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="41a01-269">Se il primo accessorio Cloud Connector ha esito negativo e non è possibile determinare il motivo dell'errore, è necessario installarlo di nuovo finché la distribuzione non ha esito positivo e quindi installare gli altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="41a01-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="41a01-270">Se il primo accessorio Cloud Connector ha esito negativo con un problema secondario, ad esempio un problema di certificato esterno, potrebbe essere possibile risolvere il problema senza reinstallare l'accessorio.</span><span class="sxs-lookup"><span data-stu-id="41a01-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="41a01-271">È quindi possibile utilizzare PowerShell remote tenant per contrassegnare la distribuzione con esito positivo come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="41a01-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="41a01-272">È inoltre possibile utilizzare la procedura seguente se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, il connettore Cloud non riesce a segnalare la distribuzione come esito positivo.</span><span class="sxs-lookup"><span data-stu-id="41a01-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="41a01-273">Per ottenere l'identità (GUID) del primo accessorio Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="41a01-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="41a01-274">Per contrassegnare l'accessorio come distribuito correttamente, eseguire il set-CsCceApplianceDeploymentStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a01-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="41a01-275">**Problema: è necessario controllare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**</span><span class="sxs-lookup"><span data-stu-id="41a01-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="41a01-276">**Soluzione:** Si consiglia di usufruire degli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="41a01-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="41a01-277">Dopo che un dispositivo è stato registrato per la gestione online e l'aggiornamento automatico del sistema operativo è abilitato, il server host e le macchine virtuali controlleranno e installeranno automaticamente gli aggiornamenti di Windows in base alle impostazioni delle finestre di tempo di aggiornamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="41a01-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="41a01-278">Se è necessario controllare e installare manualmente gli aggiornamenti di Windows, seguire la procedura descritta in questa sezione che si applicano al tipo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a01-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="41a01-279">È consigliabile pianificare l'aggiornamento del server host e delle macchine virtuali in esecuzione contemporaneamente per ridurre al minimo la quantità di tempo di inattività necessaria per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="41a01-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="41a01-280">Se si preferisce, è possibile utilizzare un server Windows Server Update Services (WSUS) per fornire gli aggiornamenti ai server dei connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="41a01-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="41a01-281">Basta essere sicuri di configurare Windows Update per **non** installare automaticamente.</span><span class="sxs-lookup"><span data-stu-id="41a01-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="41a01-282">Per informazioni su come aggiornare manualmente la distribuzione del connettore Cloud, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="41a01-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="41a01-283">**Problema: quando il connettore Cloud viene aggiornato a una nuova generazione, i cmdlet del connettore Cloud non vengono aggiornati.**</span><span class="sxs-lookup"><span data-stu-id="41a01-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="41a01-284">Questo accade talvolta se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="41a01-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="41a01-285">**Soluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="41a01-286">Chiudere PowerShell sull'accessorio Cloud Connector e quindi riaprire PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41a01-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="41a01-287">In alternativa, è possibile eseguire Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="41a01-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="41a01-288">**Problema: "il termine ' Stop-CsWindowsService ' non è riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma eseguibile." quando si tenta di eseguire il cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="41a01-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="41a01-289">**Soluzione:** Eliminare il file $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="41a01-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="41a01-290">PowerShell crea questo file come una cache di cmdlet dai moduli individuati in modo che non sia necessario analizzare di nuovo tutti i moduli ogni volta che renderebbe le cose davvero lente.</span><span class="sxs-lookup"><span data-stu-id="41a01-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="41a01-291">È probabile che si sia verificato un danneggiamento dei file che ha fornito risultati contestabili a PowerShell durante la lettura di nuovo da tale cache.</span><span class="sxs-lookup"><span data-stu-id="41a01-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="41a01-292">**Problema: "Import-Module CloudConnector" genera un errore "Import-Module: il modulo specificato" CloudConnector "non è stato caricato perché non è stato trovato alcun file di modulo valido in nessuna directory del modulo"**</span><span class="sxs-lookup"><span data-stu-id="41a01-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="41a01-293">**Risoluzione:**</span><span class="sxs-lookup"><span data-stu-id="41a01-293">**Resolution:**</span></span>
    - <span data-ttu-id="41a01-294">Verificare che esista effettivamente il modulo CloudConnector in c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="41a01-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="41a01-295">Dopo aver convalidato che il modulo CloudConnector esiste in questo percorso, è possibile modificare la variabile di ambiente PSModulePath archiviando il percorso delle posizioni dei moduli:</span><span class="sxs-lookup"><span data-stu-id="41a01-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="41a01-296">a.</span><span class="sxs-lookup"><span data-stu-id="41a01-296">a.</span></span> <span data-ttu-id="41a01-297">Modifica temporanea: avviare PowerShell come amministratore ed eseguire il comando seguente: $env:P SModulePath = $env:P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="41a01-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="41a01-298">b.</span><span class="sxs-lookup"><span data-stu-id="41a01-298">b.</span></span> <span data-ttu-id="41a01-299">Per le modifiche permanenti, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno per uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," computer ")</span><span class="sxs-lookup"><span data-stu-id="41a01-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="41a01-300">Installare manualmente gli aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="41a01-300">Install Windows updates manually</span></span>

<span data-ttu-id="41a01-301">Se non si desidera utilizzare gli aggiornamenti automatici nell'ambiente in uso, eseguire la procedura seguente per controllare e applicare manualmente gli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="41a01-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="41a01-302">Per il controllo e l'installazione degli aggiornamenti di Windows potrebbe essere necessario un riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="41a01-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="41a01-303">Quando un server host viene riavviato, gli utenti non saranno in grado di utilizzare il connettore Cloud per effettuare o ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="41a01-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="41a01-304">È possibile controllare e installare manualmente gli aggiornamenti per controllare quando si verificano gli aggiornamenti e quindi riavviare i computer in base alle esigenze nei periodi in cui si sceglie di evitare interruzioni dei servizi.</span><span class="sxs-lookup"><span data-stu-id="41a01-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="41a01-305">Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="41a01-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="41a01-306">Selezionare **sistema e sicurezza \> Windows Update**, quindi gestire gli aggiornamenti e i riavvii del server in base alle proprie esigenze per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="41a01-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="41a01-307">Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="41a01-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="41a01-308">Selezionare **sistema e sicurezza \> Windows Update**, quindi configurare gli aggiornamenti e i riavvii del server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="41a01-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="41a01-309">Se nel sito sono presenti più dispositivi, l'istanza che si sta aggiornando e riavviata non può essere letta dagli utenti durante gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="41a01-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="41a01-310">Gli utenti si connetteranno ad altre istanze della distribuzione finché tutte le macchine virtuali e tutti i servizi Skype for business non avranno inizio nelle macchine virtuali dopo il completamento degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="41a01-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="41a01-311">Per evitare possibili interruzioni del servizio, è possibile rimuovere l'istanza da HA quando si applicano gli aggiornamenti e quindi ripristinarli al termine.</span><span class="sxs-lookup"><span data-stu-id="41a01-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="41a01-312">A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="41a01-312">To do so:</span></span>
    
1. <span data-ttu-id="41a01-313">In ogni server host, aprire una console di PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="41a01-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="41a01-314">Rimuovere l'istanza da HA con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="41a01-315">Seguire la procedura per una singola istanza per applicare manualmente gli aggiornamenti e riavviare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="41a01-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="41a01-316">Impostare di nuovo l'istanza su HA con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41a01-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="41a01-317">Per le distribuzioni multisito, eseguire i passaggi per un singolo sito per ogni sito nella distribuzione, applicando gli aggiornamenti a un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="41a01-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="41a01-318">Suggerimenti per l'installazione del software antivirus nel computer host del connettore Cloud</span><span class="sxs-lookup"><span data-stu-id="41a01-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="41a01-319">Se è necessario installare il software antivirus nel computer host del connettore Cloud, è necessario aggiungere le esclusioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a01-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="41a01-320">Directory degli apparecchi locali su ogni computer.</span><span class="sxs-lookup"><span data-stu-id="41a01-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="41a01-321">Directory del sito remota su ogni computer.</span><span class="sxs-lookup"><span data-stu-id="41a01-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="41a01-322">La directory del sito locale nel computer ospita la cartella radice del sito condiviso.</span><span class="sxs-lookup"><span data-stu-id="41a01-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="41a01-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="41a01-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="41a01-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="41a01-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="41a01-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="41a01-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="41a01-326">Microsoft.Rtc.CCE.ManagementService.exe di processo.</span><span class="sxs-lookup"><span data-stu-id="41a01-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
