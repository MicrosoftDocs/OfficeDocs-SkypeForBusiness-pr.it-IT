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
description: Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094824"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="e6d98-103">Risolvere i problemi relativi alla distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e6d98-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="e6d98-104">Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="e6d98-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="e6d98-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="e6d98-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="e6d98-106">Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e6d98-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="e6d98-107">In questo argomento vengono descritte le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e6d98-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="e6d98-108">Se si verificano problemi con le chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile analizzare seguendo le soluzioni descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e6d98-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="e6d98-109">Cloud Connector fornisce meccanismi incorporati per la risoluzione automatica di alcuni problemi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="e6d98-110">Un processo di rilevamento automatico cerca potenziali problemi con le appliance cloud Connector e, se possibile, adotta azioni correttive per risolvere tali problemi senza l'intervento dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e6d98-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="e6d98-111">Il processo di rilevamento funziona come segue:</span><span class="sxs-lookup"><span data-stu-id="e6d98-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="e6d98-112">**Sequenza di rilevamento:** Il servizio di gestione dei connettori cloud esegue un processo ogni 60 secondi per rilevare se un'appliance è in stato di inossamento.</span><span class="sxs-lookup"><span data-stu-id="e6d98-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="e6d98-113">In Cloud Connector versione 2.0 e successive, il processo di rilevamento usa l'opzione Skype for Business Corpnet per effettuare connessioni PowerShell ai computer Cloud Connector; per le versioni precedenti alla 2.0, il processo di rilevamento utilizza l'opzione di gestione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6d98-114">Per il ripristino automatico, è necessario che sia presente una connettività di rete tra l'host e le macchine virtuali tramite il commutatore di rete host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="e6d98-115">Verificare la connettività di rete per assicurarsi che il rilevamento e il ripristino automatici possano avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e6d98-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="e6d98-116">**Monitoraggio:** I servizi seguenti vengono monitorati in Cloud Connector versione 2.0 e successive:</span><span class="sxs-lookup"><span data-stu-id="e6d98-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="e6d98-117">Le macchine virtuali non sono connesse ai commutatori virtuali Corporate o Internet del connettore cloud</span><span class="sxs-lookup"><span data-stu-id="e6d98-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="e6d98-118">Le macchine virtuali sono in stato salvato o arrestato</span><span class="sxs-lookup"><span data-stu-id="e6d98-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="e6d98-119">Servizi del server di gestione centrale: REPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="e6d98-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="e6d98-120">Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e6d98-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e6d98-121">Servizi server perimetrali: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="e6d98-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="e6d98-122">Le regole del firewall in ingresso sono disabilitate per CS RTCSRV nel server perimetrale, CS RTCMEDSRV nel Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e6d98-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="e6d98-123">In Cloud Connector versione 1.4.2 vengono monitorati solo i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d98-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="e6d98-124">Servizi Mediation Server: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e6d98-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e6d98-125">Servizio Server perimetrale: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="e6d98-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="e6d98-126">**Processo di ripristino:** Se i servizi monitorati non sono disponibili, un'appliance viene contrassegnata e i servizi vengono arrestati e contrassegnati come manuali fino a quando non è possibile risolvere tutti i problemi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="e6d98-127">In questo modo si impedirà il routing delle chiamate a un'appliance che potrebbe causare errori di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6d98-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="e6d98-128">Il servizio di gestione del connettore cloud ritenterà il ripristino automatico come indicato di seguito</span><span class="sxs-lookup"><span data-stu-id="e6d98-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="e6d98-129">L'intervallo tra tentativi iniziale è ogni dieci secondi con un intervallo massimo di un'ora.</span><span class="sxs-lookup"><span data-stu-id="e6d98-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="e6d98-130">Per i primi tre tentativi di ripristino, l'intervallo è di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="e6d98-131">A partire dal quarto tentativo, l'intervallo aumenta di due volte l'intervallo precedente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="e6d98-132">Ad esempio, il quarto tentativo si verificherà in 20 secondi, il quinto in 40 secondi e così via.</span><span class="sxs-lookup"><span data-stu-id="e6d98-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="e6d98-133">Quando viene raggiunto l'intervallo massimo di un'ora, i tentativi continueranno una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="e6d98-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="e6d98-134">Quando il ripristino ha esito positivo, i conteggi degli intervalli e dei tentativi vengono impostati sui valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="e6d98-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="e6d98-135">Se il servizio di gestione viene riavviato, l'intervallo e i tentativi vengono reimpostati sui valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="e6d98-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="e6d98-136">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e6d98-136">Troubleshooting</span></span>

<span data-ttu-id="e6d98-137">Di seguito sono riportate le soluzioni ai problemi più comuni:</span><span class="sxs-lookup"><span data-stu-id="e6d98-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="e6d98-138">**Problema: la distribuzione non riesce o smette di rispondere durante l'esecuzione degli script di distribuzione. Dopo l'accesso a ogni macchina virtuale, l'indirizzo IP è mancante o non corretto per la scheda di interfaccia di rete gestione/interna/esterna.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="e6d98-139">**Risoluzione:** Questo problema non può essere risolto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="e6d98-140">Le schede di interfaccia di rete non possono essere aggiunte alle macchine virtuali mentre sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="e6d98-141">Arrestare e rimuovere queste macchine virtuali nella gestione di hyper-v, quindi eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d98-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="e6d98-142">**Problema: dopo l'installazione del server Active Directory e della foresta, il server CMS e/o il Mediation Server non sono stati uniti correttamente al dominio.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="e6d98-143">**Risoluzione:** Per risolvere questo problema, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="e6d98-144">Accedere al server Active Directory e verificare che il dominio sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="e6d98-145">Accedere a CMS/Mediation Server e verificare che nella scheda NIC corpnet sia assegnato un indirizzo IP valido e che l'IP statico e il DNS validi siano configurati come indirizzo IP del server AD.</span><span class="sxs-lookup"><span data-stu-id="e6d98-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="e6d98-146">Accedere a CMS/Mediation Server e aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="e6d98-147">Assicurarsi di poter eseguire il ping dell'FQDN e dell'indirizzo IP del server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e6d98-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="e6d98-148">Se non è possibile, potrebbe verificarsi un conflitto di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="e6d98-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="e6d98-149">Provare ad assegnare un nuovo INDIRIZZO IP per Active Directory e aggiornare il DNS nel server CMS/Mediation Server di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e6d98-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="e6d98-150">**Problema: viene visualizzato il seguente messaggio di errore, "Remove-VMSwitch : Operazione non riuscita durante la rimozione del commutatore Ethernet virtuale. Il commutatore virtuale 'Cloud Connector Management Switch' non può essere eliminato perché viene utilizzato da macchine virtuali in esecuzione o assegnato a pool figlio."**</span><span class="sxs-lookup"><span data-stu-id="e6d98-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="e6d98-151">**Risoluzione:** Il "Cloud Connector Management Switch" non è stato eliminato dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="e6d98-152">Se si verifica questo errore, passare alla console di gestione di Hyper-v e verificare che non vi sia ancora una macchina virtuale ancora connessa.</span><span class="sxs-lookup"><span data-stu-id="e6d98-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="e6d98-153">Se sono ancora connesse macchine virtuali, disconnetterle ed eliminare il commutatore di gestione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="e6d98-154">Se non è ancora possibile eliminare l'opzione di gestione, riavviare il server host e riprovare.</span><span class="sxs-lookup"><span data-stu-id="e6d98-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="e6d98-155">**Problema: viene visualizzato il messaggio di errore seguente, "Avvio del servizio RTCMRAUTH non riuscito. Verificare che il servizio non sia disabilitato."**</span><span class="sxs-lookup"><span data-stu-id="e6d98-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6d98-156">Questo problema si applica solo alle versioni di Cloud Connector precedenti alla 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e6d98-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="e6d98-157">L'errore di avvio potrebbe anche essere dovuto al fatto che in precedenza è stato eseguito il failover del server Front End (utilizzando il failover del computer).</span><span class="sxs-lookup"><span data-stu-id="e6d98-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="e6d98-158">In questo caso, richiamare il fail back (utilizzando il fail back del computer).</span><span class="sxs-lookup"><span data-stu-id="e6d98-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="e6d98-159">**Risoluzione:** Questo problema si verifica in un server perimetrale quando il certificato CA radice o il certificato CA intermedio non è considerato attendibile dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e6d98-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="e6d98-160">Anche se il certificato esterno può essere importato ma la catena di certificati è interrotta.</span><span class="sxs-lookup"><span data-stu-id="e6d98-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="e6d98-161">In questa condizione, non è possibile avviare il servizio RTCMRAUTH e/o RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="e6d98-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="e6d98-162">Importare manualmente il certificato della CA radice e tutti i certificati CA intermedi del certificato esterno nel server perimetrale e quindi riavviare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e6d98-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="e6d98-163">Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:</span><span class="sxs-lookup"><span data-stu-id="e6d98-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="e6d98-164">**Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate effettuate dal server hanno esito negativo.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="e6d98-165">**Risoluzione:** Se è stato distribuito un ambiente a disponibilità elevata, Microsoft fornisce un cmdlet che consente di spostare un computer host (istanza di distribuzione) all'interno o all'esterno della topologia corrente quando si archivia e si installa windows update manualmente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="e6d98-166">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="e6d98-167">Nel server host, avviare una console di PowerShell come amministratore, quindi eseguire:</span><span class="sxs-lookup"><span data-stu-id="e6d98-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="e6d98-168">Verificare la disponibilità di aggiornamenti e installare gli eventuali aggiornamenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="e6d98-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="e6d98-169">Nella console di PowerShell eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="e6d98-170">**Problema: quando viene effettuata una chiamata da un client Skype for Business utilizzando un numero PSTN, non è possibile inoltrare la chiamata a una conferenza invitando un altro numero PSTN.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="e6d98-171">**Risoluzione:** Per risolvere questo problema, vedere [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="e6d98-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="e6d98-172">**Problema: viene visualizzato un messaggio di avviso relativo a Windows Update durante l'installazione del server Active Directory: "L'aggiornamento automatico di Windows non è abilitato. Per assicurarti che il ruolo o la funzionalità appena installata sia aggiornata automaticamente, attiva Windows Update."**</span><span class="sxs-lookup"><span data-stu-id="e6d98-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="e6d98-173">**Risoluzione:** Avviare una sessione di PowerShell remoto tenant utilizzando le credenziali di amministratore tenant di Skype for Business, quindi eseguire il cmdlet seguente per controllare la configurazione _EnableAutoUpdate_ del sito:</span><span class="sxs-lookup"><span data-stu-id="e6d98-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="e6d98-174">Se  _EnableAutoUpdate_ è impostato su **True,** è possibile ignorare questo messaggio di avviso perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali che per il server host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="e6d98-175">Se _EnableAutoUpdate_ è impostato su **False,** eseguire il cmdlet seguente per impostarlo su **True.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="e6d98-176">In alternativa, è possibile controllare e installare manualmente gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e6d98-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="e6d98-177">Vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="e6d98-177">See the next section.</span></span>
    
- <span data-ttu-id="e6d98-178">**Problema: viene visualizzato un messaggio di errore: Impossibile registrare l'appliance perché l'input/configurazione corrente o \<SiteName\> o è in conflitto con le appliance \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> esistenti. Rimuovi l'appliance in conflitto o aggiorna le informazioni di input/configurazione e quindi registra di nuovo. ' quando viene eseguito Register-CcAppliance per registrare l'appliance corrente online.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="e6d98-179">**Risoluzione:** I valori per \<ApplianceName\> e \<Mediation Server FQDN\> devono essere \<Mediation Server IP Address\> univoci e utilizzati solo per la registrazione di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6d98-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="e6d98-180">Per impostazione predefinita, \<ApplianceName\> proviene dal nome host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="e6d98-181">\<Mediation Server FQDN\> e \<Mediation Server IP Address\> definito nel file ini di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="e6d98-182">Ad esempio, utilizzando (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) per eseguire la registrazione in SiteName=MySite, ma se è presente un'appliance registrata (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), si avrà il conflitto.</span><span class="sxs-lookup"><span data-stu-id="e6d98-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="e6d98-183">Prima di tutto, controllare il file CloudConnector.ini nella sezione Directory ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="e6d98-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="e6d98-184">Si otterrà \<SiteName\> e i valori nel \<Mediation Server FQDN\> \<Mediation Server IP Address\> file.</span><span class="sxs-lookup"><span data-stu-id="e6d98-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="e6d98-185">\<ApplianceName\> è il nome del server host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="e6d98-186">In secondo momento, avvia Remote PowerShell tenant usando le credenziali di amministratore tenant di Skype for Business, quindi esegui il cmdlet seguente per controllare gli appliance registrati.</span><span class="sxs-lookup"><span data-stu-id="e6d98-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="e6d98-187">Dopo aver identificato eventuali conflitti, è possibile aggiornare il file CloudConnector.ini con le informazioni corrispondenti all'appliance registrata oppure annullare la registrazione dell'appliance esistente per risolvere i conflitti.</span><span class="sxs-lookup"><span data-stu-id="e6d98-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="e6d98-188">**Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se nell'host è in esecuzione un'appliance distribuita.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="e6d98-189">**Risoluzione:** Ciò può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="e6d98-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="e6d98-190">Dopo aver installato la versione 1.4.1 con il file msi, è necessario eseguire `Register-CcAppliance` prima di eseguire qualsiasi altro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6d98-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="e6d98-191">`Register-CcAppliance` eseguirà la migrazione module.ini file da %UserProfile%\CloudConnector a %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="e6d98-192">Se si è perso, verrà creato un nuovo module.ini nella cartella %ProgramData%\CloudConnector e verranno sostituite le informazioni sulla versione di esecuzione/backup per 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="e6d98-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="e6d98-193">Confronta module.ini file nella cartella %UserProfile%\CloudConnector e %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="e6d98-194">In caso di differenze, eliminare il file module.ini in %ProgramData%\CloudConnector ed eseguire di nuovo  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="e6d98-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="e6d98-195">È inoltre possibile modificare manualmente il file con la versione di esecuzione e di backup corretta.</span><span class="sxs-lookup"><span data-stu-id="e6d98-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="e6d98-196">**Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione corrente dello script, non è disponibile alcun supporto disponibilità elevata per questa versione precedente.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="e6d98-197">**Risoluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e6d98-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="e6d98-198">La versione corrente dello script, che può essere determinata dall'esecuzione, e la versione in esecuzione, che può essere determinata dall'esecuzione, sono `Get-CcVersion`  `Get-CcRunningVersion` entrambe 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e6d98-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="e6d98-199">Al momento, se si esegue per tornare alla versione in esecuzione alla versione 1.4.1, non sarà disponibile alcun supporto per la `Switch-CcVersion` disponibilità elevata per questa versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="e6d98-200">Per ottenere il supporto completo della disponibilità elevata, tornare alla versione 1.4.2, in modo che la versione in esecuzione e la versione dello script siano uguali.</span><span class="sxs-lookup"><span data-stu-id="e6d98-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="e6d98-201">Se si verificano problemi con la distribuzione 1.4.2, disinstallarla e reinstallarla il prima possibile.</span><span class="sxs-lookup"><span data-stu-id="e6d98-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="e6d98-202">**Problema: i certificati dell'autorità di certificazione o i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono prossimi alla scadenza o sono compromessi.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="e6d98-203">**Risoluzione:** I certificati dell'Autorità di certificazione di Skype for Business sono validi per cinque anni.</span><span class="sxs-lookup"><span data-stu-id="e6d98-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="e6d98-204">I certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni.</span><span class="sxs-lookup"><span data-stu-id="e6d98-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6d98-205">In Cloud Connector versione 2.0 e successive, il cmdlet Renew-CcServerCertificate è cambiato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è cambiato in Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="e6d98-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="e6d98-206">Se i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono quasi scaduti o compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="e6d98-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e6d98-207">Se i certificati dell'Autorità di certificazione sono prossimi alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="e6d98-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e6d98-208">**Se i certificati dell'Autorità** di certificazione vengono compromessi e nel sito è presente un solo dispositivo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="e6d98-209">Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e mettere l'appliance in modalità manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="e6d98-210">Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:</span><span class="sxs-lookup"><span data-stu-id="e6d98-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="e6d98-211">Per i rilasci del connettore cloud prima della 2.0:</span><span class="sxs-lookup"><span data-stu-id="e6d98-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="e6d98-212">Oppure per Cloud Connector versione 2.0 e successive:</span><span class="sxs-lookup"><span data-stu-id="e6d98-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="e6d98-213">Se viene utilizzato TLS tra il gateway e Mediation Server, eseguire il cmdlet Export-CcRootCertificate dall'appliance e quindi installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6d98-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e6d98-214">Potrebbe anche essere necessario riemettere il certificato nel gateway.</span><span class="sxs-lookup"><span data-stu-id="e6d98-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="e6d98-215">Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="e6d98-216">**Se i certificati dell'Autorità** di certificazione sono compromessi e nel sito sono presenti più appliance, eseguire i passaggi sequenziali seguenti in ogni appliance del sito.</span><span class="sxs-lookup"><span data-stu-id="e6d98-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="e6d98-217">Microsoft consiglia di eseguire questi passaggi durante i periodi di utilizzo non di punta.</span><span class="sxs-lookup"><span data-stu-id="e6d98-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="e6d98-218">Nel primo appliance, eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella \<SiteRoot\> directory.</span><span class="sxs-lookup"><span data-stu-id="e6d98-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="e6d98-219">Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e mettere ogni appliance in modalità manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="e6d98-220">Nella prima appliance, eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'Autorità di certificazione e tutti i certificati del server interni:</span><span class="sxs-lookup"><span data-stu-id="e6d98-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="e6d98-221">Per i rilasci del connettore cloud prima della 2.0:</span><span class="sxs-lookup"><span data-stu-id="e6d98-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="e6d98-222">Oppure per Cloud Connector versione 2.0 e successive:</span><span class="sxs-lookup"><span data-stu-id="e6d98-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="e6d98-223">Nel primo dispositivo, eseguire il cmdlet seguente per eseguire il backup dei file dell'autorità di certificazione nella \<SiteRoot\> cartella.</span><span class="sxs-lookup"><span data-stu-id="e6d98-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="e6d98-224">In tutti gli altri dispositivi nello stesso sito, eseguire i comandi seguenti per utilizzare i file di backup della CA, in modo che tutti gli appliance utilizzino lo stesso certificato radice e quindi richiedere nuovi certificati.</span><span class="sxs-lookup"><span data-stu-id="e6d98-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="e6d98-225">Se viene utilizzato TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate da qualsiasi appliance del sito e quindi installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6d98-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e6d98-226">Potrebbe anche essere necessario riemettere il certificato nel gateway.</span><span class="sxs-lookup"><span data-stu-id="e6d98-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="e6d98-227">Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="e6d98-228">**Problema: viene visualizzato il seguente messaggio di errore nel registro del servizio di gestione del connettore cloud, "C:\Programmi\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": Errore CceService: 0 : Eccezione imprevista durante la segnalazione dello stato online: System.Management.Automation.CmdletInvocationException: Accesso non riuscito per l'utente \<Global Tenant Admin\> . Creare un nuovo oggetto credenziali, verificando di aver utilizzato il nome utente e la password corretti. ---\>**</span><span class="sxs-lookup"><span data-stu-id="e6d98-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="e6d98-229">**Risoluzione:** Le credenziali di amministratore del tenant globale di Microsoft 365 o Office 365 sono state modificate dopo la registrazione dell'appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="e6d98-230">Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, eseguire le operazioni seguenti da PowerShell di amministratore nell'appliance host:</span><span class="sxs-lookup"><span data-stu-id="e6d98-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="e6d98-231">**Problema: dopo aver modificato la password per l'account del server host utilizzato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString : Chiave non valida per l'utilizzo nello stato specificato." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="e6d98-232">**Risoluzione:** Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="e6d98-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e6d98-233">Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="e6d98-234">**Se si esegue Cloud Connector versione 1.4.2,** rigenerare tutte le password del connettore cloud eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="e6d98-235">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="e6d98-236">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="e6d98-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="e6d98-237">Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e6d98-238">Immettere le stesse password immesse in precedenza per la distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="e6d98-239">**Se si esegue Cloud Connector versione 2.0 o successiva,** rigenerare tutte le password del connettore cloud eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="e6d98-240">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="e6d98-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="e6d98-241">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .</span><span class="sxs-lookup"><span data-stu-id="e6d98-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="e6d98-242">Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="e6d98-243">Se il file della password memorizzata nella cache è stato generato con Cloud Connector versione 1.4.2, utilizzare la password VMAdmin per la password CceService quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="e6d98-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="e6d98-244">Immettere la stessa password immessa prima per la distribuzione di Cloud Connector per tutti gli altri account.</span><span class="sxs-lookup"><span data-stu-id="e6d98-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="e6d98-245">Se il file delle password memorizzate nella cache è stato generato con Cloud Connector versione 1.4.2 e le password DomainAdmin e VMAdmin sono diverse, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="e6d98-246">Eseguire Set-CcCredential -AccountType DomainAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="e6d98-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="e6d98-247">Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="e6d98-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="e6d98-248">Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6d98-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="e6d98-249">Se il file della password memorizzata nella cache è stato generato con Cloud Connector versione 2.0 o successiva, per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="e6d98-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="e6d98-250">Se sono state modificate le password DomainAdmin e VMAdmin, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="e6d98-251">Eseguire Set-CcCredential -AccountType DomainAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="e6d98-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e6d98-252">Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService</span><span class="sxs-lookup"><span data-stu-id="e6d98-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e6d98-253">Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6d98-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="e6d98-254">Eseguire Set-CcCredential -AccountType VmAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="e6d98-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e6d98-255">Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService</span><span class="sxs-lookup"><span data-stu-id="e6d98-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e6d98-256">Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password VmAdmin usata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6d98-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="e6d98-257">**Problema: con Cloud Connector versione 2.1 e successive, quando si esegue Register-CcAppliance o altri cmdlet nell'appliance, viene visualizzato un messaggio di errore del tipo: "Per Each-Object : Impossibile trovare la proprietà 'Common' su questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="e6d98-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="e6d98-258">**Risoluzione:** Cloud Connector 2.1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e6d98-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="e6d98-259">Aggiornare il .NET Framework nell'appliance alla versione 4.6.1 o successiva ed eseguire di nuovo i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6d98-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="e6d98-260">**Problema: con Cloud Connector Edition 2.1, quando si esegue Install-CcAppliance, viene visualizzato un messaggio di errore simile al seguente: "Impossibile installare una nuova istanza con errore: Impossibile impostare "State" perché solo le stringhe possono essere utilizzate come valori per impostare le proprietà XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="e6d98-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="e6d98-261">**Risoluzione:** In Cloudconnector.ini, nella sezione [Common], aggiungi la configurazione "State" come segue: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="e6d98-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="e6d98-262">Non è obbligatorio che la riga "State" abbia valore, tuttavia la riga "State" non può essere rimossa dal file Cloudconnector.ini file.</span><span class="sxs-lookup"><span data-stu-id="e6d98-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="e6d98-263">**Problema: viene visualizzato il seguente messaggio di errore "Dismount-WindowsImage : Dismount-WindowsImage non riuscito. Codice di errore = 0xc1550115" durante l'installazione o l'aggiornamento di Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="e6d98-264">**Risoluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM -Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="e6d98-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="e6d98-265">In questo modo verranno ripulite tutte le immagini con problemi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-265">This will clean up all troubled images.</span></span> <span data-ttu-id="e6d98-266">Eseguire Install-CcAppliance o attendere l'aggiornamento automatico dei bit.</span><span class="sxs-lookup"><span data-stu-id="e6d98-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="e6d98-267">**Problema: la distribuzione della prima appliance Cloud Connector in un ambiente ha esito negativo**</span><span class="sxs-lookup"><span data-stu-id="e6d98-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="e6d98-268">**Risoluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non è riuscita:</span><span class="sxs-lookup"><span data-stu-id="e6d98-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="e6d98-269">Se il primo dispositivo Cloud Connector non riesce e non è possibile determinare il motivo dell'errore, è necessario installare di nuovo l'appliance fino a quando la distribuzione non riesce e quindi installare le altre appliance.</span><span class="sxs-lookup"><span data-stu-id="e6d98-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="e6d98-270">Se il primo dispositivo Cloud Connector ha esito negativo con un problema secondario, ad esempio un problema di certificato esterno, potrebbe essere possibile risolvere il problema senza installare di nuovo l'appliance.</span><span class="sxs-lookup"><span data-stu-id="e6d98-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="e6d98-271">È quindi possibile utilizzare PowerShell remoto tenant per contrassegnare la distribuzione come completata come segue.</span><span class="sxs-lookup"><span data-stu-id="e6d98-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="e6d98-272">È inoltre possibile eseguire la procedura seguente se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, Cloud Connector non riesce a segnalare la distribuzione come completata.</span><span class="sxs-lookup"><span data-stu-id="e6d98-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="e6d98-273">Per ottenere l'identità (GUID) della prima appliance Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance cloud.</span><span class="sxs-lookup"><span data-stu-id="e6d98-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="e6d98-274">Per contrassegnare l'appliance come distribuito correttamente, eseguire il Set-CsCceApplianceDeploymentStatus come segue:</span><span class="sxs-lookup"><span data-stu-id="e6d98-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="e6d98-275">**Problema: è necessario verificare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="e6d98-276">**Risoluzione:** Ti consigliamo di sfruttare gli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e6d98-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="e6d98-277">Dopo la registrazione di un'appliance per la gestione online e l'aggiornamento automatico del sistema operativo è abilitato, il server host e le macchine virtuali controllano e installano automaticamente gli aggiornamenti di Windows in base alle impostazioni dell'intervallo di tempo di aggiornamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e6d98-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="e6d98-278">Se devi controllare e installare manualmente gli aggiornamenti di Windows, segui i passaggi di questa sezione che si applicano al tipo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e6d98-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="e6d98-279">È consigliabile pianificare l'aggiornamento contemporaneamente sia del server host che delle macchine virtuali in esecuzione su di esso per ridurre al minimo la quantità di tempo di in down time necessario per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e6d98-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="e6d98-280">Se si preferisce, è possibile utilizzare un server Windows Server Update Services (WSUS) per fornire aggiornamenti ai server Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e6d98-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="e6d98-281">Assicurati di configurare Windows Update in modo che **non si installi** automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="e6d98-282">Per informazioni su come aggiornare manualmente la distribuzione di Cloud Connector, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="e6d98-283">**Problema: quando Cloud Connector si aggiorna a una nuova build, i cmdlet di Cloud Connector non vengono aggiornati.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="e6d98-284">Ciò accade a volte se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="e6d98-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="e6d98-285">**Risoluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d98-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="e6d98-286">Chiudere PowerShell nell'appliance Cloud Connector e quindi riaprire PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6d98-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="e6d98-287">In caso contrario, puoi eseguire Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="e6d98-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="e6d98-288">**Problema: "Il termine "Stop-CsWindowsService" non viene riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma funzionante." quando si tenta di eseguire un cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="e6d98-289">**Risoluzione:** Elimina il file $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="e6d98-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="e6d98-290">PowerShell crea questo file come cache di cmdlet dai moduli trovati in modo che non sia necessario analizzare di nuovo tutti i moduli ogni volta perché ciò renderebbe le cose molto lente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="e6d98-291">Molto probabilmente, c'è stato un danneggiamento dei file che ha fornito risultati fuorvianti a PowerShell durante la lettura dalla cache.</span><span class="sxs-lookup"><span data-stu-id="e6d98-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="e6d98-292">**Problema: "Import-Module CloudConnector" genera l'errore "Import-Module: Il modulo specificato "CloudConnector" non è stato caricato perché non è stato trovato alcun file di modulo valido in alcuna directory dei moduli"**</span><span class="sxs-lookup"><span data-stu-id="e6d98-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="e6d98-293">**Risoluzione:**</span><span class="sxs-lookup"><span data-stu-id="e6d98-293">**Resolution:**</span></span>
    - <span data-ttu-id="e6d98-294">Verificare che il modulo CloudConnector esista effettivamente in c:\Programmi\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="e6d98-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="e6d98-295">Dopo aver convalidato l'esistenza del modulo CloudConnector in questo percorso, è possibile modificare la variabile di ambiente PSModulePath che archivia il percorso dei percorsi dei moduli:</span><span class="sxs-lookup"><span data-stu-id="e6d98-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="e6d98-296">a.</span><span class="sxs-lookup"><span data-stu-id="e6d98-296">a.</span></span> <span data-ttu-id="e6d98-297">Modifica temporanea: avviare Powershell come amministratore ed eseguire il comando seguente: $env:PSModulePath = $env:PSModulePath + "; C:\Programmi\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="e6d98-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="e6d98-298">b.</span><span class="sxs-lookup"><span data-stu-id="e6d98-298">b.</span></span> <span data-ttu-id="e6d98-299">Per la modifica persistente, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno alla volta: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Programmi\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="e6d98-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="e6d98-300">Installare manualmente gli aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="e6d98-300">Install Windows updates manually</span></span>

<span data-ttu-id="e6d98-301">Se non vuoi usare gli aggiornamenti automatici nel tuo ambiente, segui questi passaggi per cercare e applicare manualmente gli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="e6d98-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="e6d98-302">Il controllo e l'installazione degli aggiornamenti di Windows potrebbero richiedere il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="e6d98-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="e6d98-303">Quando un server host viene riavviato, gli utenti non potranno utilizzare Cloud Connector per effettuare o ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="e6d98-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="e6d98-304">È possibile verificare e installare manualmente gli aggiornamenti per controllare quando vengono evasi gli aggiornamenti e quindi riavviare i computer in base alle esigenze durante i periodi in cui si sceglie di evitare interruzioni dei servizi.</span><span class="sxs-lookup"><span data-stu-id="e6d98-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="e6d98-305">Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="e6d98-306">Selezionare **Sistema e sicurezza di Windows \> Update** e quindi gestire gli aggiornamenti e i riavvii del server in base alle esigenze dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6d98-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="e6d98-307">Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo.**</span><span class="sxs-lookup"><span data-stu-id="e6d98-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="e6d98-308">Selezionare **System and Security Windows \> Update** e quindi configurare gli aggiornamenti e i riavvii del server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e6d98-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="e6d98-309">Se nel sito sono presenti più appliance, gli utenti non potranno accedere all'istanza da aggiornare e riavviare durante gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e6d98-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="e6d98-310">Gli utenti si connetteranno ad altre istanze della distribuzione finché tutte le macchine virtuali e tutti i servizi Skype for Business non vengono avviati nelle macchine virtuali dopo il completamento degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e6d98-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="e6d98-311">Per evitare potenziali interruzioni del servizio, è possibile rimuovere l'istanza dall'ha mentre si applicano gli aggiornamenti e quindi ripristinarla al termine.</span><span class="sxs-lookup"><span data-stu-id="e6d98-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="e6d98-312">A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="e6d98-312">To do so:</span></span>
    
1. <span data-ttu-id="e6d98-313">In ogni server host, aprire una console di PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="e6d98-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="e6d98-314">Rimuovere l'istanza dall'ha con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="e6d98-315">Seguire i passaggi per una singola istanza per applicare manualmente gli aggiornamenti e riavviare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="e6d98-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="e6d98-316">Impostare nuovamente l'istanza su HA con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e6d98-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="e6d98-317">Per le distribuzioni multisnode, seguire la procedura per un singolo sito per ogni sito della distribuzione, applicando gli aggiornamenti a un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="e6d98-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="e6d98-318">Suggerimenti per l'installazione di software antivirus nel computer host cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e6d98-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="e6d98-319">Se è necessario installare software antivirus nel computer host Cloud Connector, è necessario aggiungere le esclusioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d98-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="e6d98-320">Directory appliance locale in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="e6d98-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="e6d98-321">Directory siti remoti in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="e6d98-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="e6d98-322">La directory siti locale nel computer ospita la cartella radice del sito condiviso.</span><span class="sxs-lookup"><span data-stu-id="e6d98-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="e6d98-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e6d98-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="e6d98-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e6d98-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="e6d98-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e6d98-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="e6d98-326">Il processo Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="e6d98-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>