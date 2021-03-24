---
title: Distribuire il gestore delle statistiche per Skype for Business Server
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire Gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: 406f4188347d32111bea4952815237b7f1015574
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105382"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="fd978-103">Distribuire il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd978-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="fd978-104">**Riepilogo:** Leggere questo argomento per informazioni su come distribuire Gestione statistiche per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd978-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="fd978-105">Gestione statistiche per Skype for Business Server è un potente strumento che consente di visualizzare i dati sulle prestazioni e sull'integrità di Skype for Business Server in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="fd978-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="fd978-106">È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web Gestione statistiche.</span><span class="sxs-lookup"><span data-stu-id="fd978-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="fd978-107">Prima di tentare di installare Gestione statistiche, assicurarsi di avere familiarità con i requisiti software, di rete e hardware.</span><span class="sxs-lookup"><span data-stu-id="fd978-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="fd978-108">Per ulteriori informazioni, vedere [Plan for Statistics Manager for Skype for Business Server.](plan.md)</span><span class="sxs-lookup"><span data-stu-id="fd978-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd978-109">Se si esegue l'aggiornamento da una versione precedente di Gestione statistiche, vedere [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="fd978-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fd978-110">Il sito Web Gestione statistiche è stato testato e funziona correttamente in Internet Explorer 11+, Edge 20.10240+ e Chrome 46+ (versione sempreverde corrente).</span><span class="sxs-lookup"><span data-stu-id="fd978-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="fd978-111">È possibile trovare Gestione statistiche scaricabile all'indirizzo [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) .</span><span class="sxs-lookup"><span data-stu-id="fd978-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="fd978-112">In questa sezione sono contenute le seguenti sezioni:</span><span class="sxs-lookup"><span data-stu-id="fd978-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="fd978-113">Distribuire Gestione statistiche</span><span class="sxs-lookup"><span data-stu-id="fd978-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="fd978-114">Risolvere i problemi relativi alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="fd978-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="fd978-115">Creare un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="fd978-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="fd978-116">Distribuire Gestione statistiche</span><span class="sxs-lookup"><span data-stu-id="fd978-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="fd978-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="fd978-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="fd978-118">Per distribuire Gestione statistiche, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="fd978-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="fd978-119">Preparare il computer host Listener installando il sistema di memorizzazione nella cache redis in memoria e verificando di aver installato i certificati appropriati.</span><span class="sxs-lookup"><span data-stu-id="fd978-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="fd978-120">Installare il servizio Listener nel computer host.</span><span class="sxs-lookup"><span data-stu-id="fd978-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="fd978-121">Installare il sito Web nel computer host.</span><span class="sxs-lookup"><span data-stu-id="fd978-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="fd978-122">Installare un agente in ogni computer Skype for Business Server che si desidera monitorare.</span><span class="sxs-lookup"><span data-stu-id="fd978-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="fd978-123">Importare la topologia per i server da monitorare.</span><span class="sxs-lookup"><span data-stu-id="fd978-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fd978-124">Redis, il servizio Listener e il sito Web devono essere tutti installati nello stesso computer host.</span><span class="sxs-lookup"><span data-stu-id="fd978-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="fd978-125">Assicurati che nel computer host non sia installato Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd978-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="fd978-126">Preparare il computer host listener</span><span class="sxs-lookup"><span data-stu-id="fd978-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="fd978-127">Per preparare il computer host, è necessario installare il sistema di memorizzazione nella cache redis in memoria e verificare che nel computer sia presente un certificato valido.</span><span class="sxs-lookup"><span data-stu-id="fd978-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="fd978-128">Microsoft consiglia di installare la build stabile più recente di Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="fd978-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="fd978-129">Statistics Manager versione 2.0 è stato testato con Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="fd978-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="fd978-130">Scaricare Redis dal sito seguente: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) .</span><span class="sxs-lookup"><span data-stu-id="fd978-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="fd978-131">I programmi di installazione non firmati possono essere scaricati da [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="fd978-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="fd978-132">Se necessario, i file binari firmati sono disponibili tramite i gestori di pacchetti più diffusi: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey.](https://chocolatey.org/packages/redis-64)</span><span class="sxs-lookup"><span data-stu-id="fd978-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="fd978-133">Eseguire il file msi fornito e seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="fd978-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="fd978-134">Non selezionare la casella per aggiungere una regola del firewall.</span><span class="sxs-lookup"><span data-stu-id="fd978-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="fd978-135">Il servizio Listener richiede un certificato.</span><span class="sxs-lookup"><span data-stu-id="fd978-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="fd978-136">Microsoft consiglia vivamente di disporre di un certificato firmato da un'autorità di certificazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="fd978-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="fd978-137">Se si desidera utilizzare un certificato autofirmato, ad esempio a scopo di test in un laboratorio, vedere [Creare un certificato autofirmato.](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="fd978-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="fd978-138">Si noti che l'agente usa la verifica dell'identificazione personale del certificato (anziché la verifica della catena).</span><span class="sxs-lookup"><span data-stu-id="fd978-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="fd978-139">Non verrà eseguita la convalida completa del certificato perché è possibile utilizzare certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="fd978-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="fd978-140">Installare il servizio Listener</span><span class="sxs-lookup"><span data-stu-id="fd978-140">Install the Listener service</span></span>

<span data-ttu-id="fd978-141">Installare il servizio Listener nel computer host eseguendo il StatsManPerfAgentListener.msi e specificando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="fd978-142">Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="fd978-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="fd978-143">Nella pagina successiva specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd978-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="fd978-144">**Password servizio:** Questa è la password che gli agenti remoti utilizzeranno per eseguire l'autenticazione nel servizio Listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="fd978-145">**Porta servizio:** Questo è il numero di porta HTTPS che il listener utilizzerà per comunicare con gli agenti.</span><span class="sxs-lookup"><span data-stu-id="fd978-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="fd978-146">Durante l'installazione, questa porta verrà consentita attraverso il firewall locale, verrà creato un elenco di controllo di accesso URL e verrà associato un certificato SSL a questa porta.</span><span class="sxs-lookup"><span data-stu-id="fd978-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="fd978-147">Il valore predefinito è 8443.</span><span class="sxs-lookup"><span data-stu-id="fd978-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="fd978-148">**Identificazione personale certificato:** Si tratta dell'identificazione personale del certificato che verrà utilizzata dal listener per crittografare il protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd978-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="fd978-149">Il servizio di rete deve disporre dell'accesso in lettura alla chiave privata.</span><span class="sxs-lookup"><span data-stu-id="fd978-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="fd978-150">Fare clic **sul pulsante Seleziona...** per scegliere l'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="fd978-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="fd978-151">È possibile trovare l'identificazione personale del certificato utilizzando Gestione certificati o il comando di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="fd978-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="fd978-152">**Installa Dir:** Questa è la directory in cui verranno installati i file binari.</span><span class="sxs-lookup"><span data-stu-id="fd978-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="fd978-153">È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**</span><span class="sxs-lookup"><span data-stu-id="fd978-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="fd978-154">**AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati.</span><span class="sxs-lookup"><span data-stu-id="fd978-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="fd978-155">È possibile modificarla rispetto all'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fd978-155">You may change it from the default.</span></span> <span data-ttu-id="fd978-156">Non verrà eliminato durante la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="fd978-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="fd978-157">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="fd978-157">Click **Install**.</span></span>
    
<span data-ttu-id="fd978-158">Per convalidare l'installazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="fd978-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="fd978-159">Aprire un browser e passare a https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="fd978-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="fd978-160">Per impostazione predefinita, la porta del servizio è 8443 (a meno che non sia stata specificata un'altra porta).</span><span class="sxs-lookup"><span data-stu-id="fd978-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="fd978-161">Per verificare che listener sia installato correttamente, cercare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="fd978-162">Se viene visualizzata la pagina di controllo dell'integrità, l'installazione del listener ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fd978-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="fd978-163">Se KnownServerCount è 1 o superiore, viene stabilita la connessione a Redis.</span><span class="sxs-lookup"><span data-stu-id="fd978-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="fd978-164">Dopo aver atteso alcuni minuti e dopo aver installato almeno un agente, verificare che il contatore ValuesWritten sia in aumento.</span><span class="sxs-lookup"><span data-stu-id="fd978-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="fd978-165">Installare il sito Web</span><span class="sxs-lookup"><span data-stu-id="fd978-165">Install the Website</span></span>

<span data-ttu-id="fd978-166">Installare il sito Web nel computer host eseguendo il StatsManWebSite.msi (incluso in [Skype for Business Server, Real-Time Statistics Manager (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)e specificando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="fd978-167">Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="fd978-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="fd978-168">Nella pagina successiva specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd978-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="fd978-169">**Porta servizio:** Questo è il numero di porta su cui il sito Web sarà in ascolto.</span><span class="sxs-lookup"><span data-stu-id="fd978-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="fd978-170">È possibile modificarlo in un secondo momento utilizzando il binding di Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="fd978-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="fd978-171">Durante l'installazione, questa porta verrà consentita attraverso il firewall locale.</span><span class="sxs-lookup"><span data-stu-id="fd978-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="fd978-172">**Installa Dir:** Questa è la directory in cui verranno installati i file binari.</span><span class="sxs-lookup"><span data-stu-id="fd978-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="fd978-173">È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**</span><span class="sxs-lookup"><span data-stu-id="fd978-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="fd978-174">**AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati.</span><span class="sxs-lookup"><span data-stu-id="fd978-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="fd978-175">È possibile modificarla rispetto all'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fd978-175">You may change it from the default.</span></span> <span data-ttu-id="fd978-176">Non verrà eliminato durante la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="fd978-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="fd978-177">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="fd978-177">Click **Install**.</span></span>
    
<span data-ttu-id="fd978-178">Per visualizzare il sito Web, aprire un browser e passare a: http://localhost ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="fd978-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="fd978-179">Per visualizzare solo le informazioni sull'integrità, aprire un browser e passare a: http://localhost: \<webport\> /healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="fd978-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="fd978-180">Per impostazione predefinita, il numero di porta Web è 8080.</span><span class="sxs-lookup"><span data-stu-id="fd978-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="fd978-181">È possibile modificare il binding di porta del sito Web utilizzando Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="fd978-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="fd978-182">Il programma di installazione Web aggiunge un gruppo di sicurezza locale, denominato StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="fd978-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="fd978-183">È possibile aggiungere account a questo gruppo di sicurezza per concedere l'accesso al sito Web.</span><span class="sxs-lookup"><span data-stu-id="fd978-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="fd978-184">Installare gli agenti</span><span class="sxs-lookup"><span data-stu-id="fd978-184">Install the Agents</span></span>

<span data-ttu-id="fd978-185">Installare un agente in ogni Skype for Business Server che si desidera monitorare eseguendo il StatsManPerfAgent.msi e specificando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="fd978-186">Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="fd978-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="fd978-187">Nella pagina successiva specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd978-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="fd978-188">**Password servizio:** Questa è la password che l'agente remoto utilizzerà per eseguire l'autenticazione nel servizio Listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="fd978-189">**URI servizio:** Questo è l'URI in cui risiede il listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="fd978-190">Deve utilizzare il https://name:port formato.</span><span class="sxs-lookup"><span data-stu-id="fd978-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="fd978-191">È possibile utilizzare un nome NETBIOS o un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="fd978-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="fd978-192">È possibile utilizzare il nome specificato  anche come Subject o **Subject Alternative Names** del certificato nel servizio Listener, ma questo non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="fd978-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="fd978-193">**Identificazione personale servizio:** Questa è l'identificazione personale del certificato SSL utilizzato dal listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="fd978-194">L'agente utilizzerà questa identificazione personale per eseguire l'autenticazione nel listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="fd978-195">Non verrà eseguita la convalida completa del certificato perché è possibile utilizzare certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="fd978-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="fd978-196">**Installa Dir:** Questa è la directory in cui verranno installati i file binari.</span><span class="sxs-lookup"><span data-stu-id="fd978-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="fd978-197">È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**</span><span class="sxs-lookup"><span data-stu-id="fd978-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="fd978-198">**AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e il file password.txt crittografato.</span><span class="sxs-lookup"><span data-stu-id="fd978-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="fd978-199">È possibile modificare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fd978-199">You may thanks change it from the default.</span></span> <span data-ttu-id="fd978-200">Non verrà eliminato durante la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="fd978-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="fd978-201">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="fd978-201">Click **Install**.</span></span>
    
<span data-ttu-id="fd978-202">Se si installa un agente in più computer, è probabile che si desideri eseguire questa operazione in modalità automatica.</span><span class="sxs-lookup"><span data-stu-id="fd978-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="fd978-203">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fd978-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="fd978-204">Importare la topologia</span><span class="sxs-lookup"><span data-stu-id="fd978-204">Import the topology</span></span>
<span data-ttu-id="fd978-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="fd978-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="fd978-206">Dopo l'installazione e l'esecuzione di Gestione statistiche, è necessario importare la topologia di Skype for Business Server in modo che Gestione statistiche conosca il sito, il pool e il ruolo di ogni server.</span><span class="sxs-lookup"><span data-stu-id="fd978-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="fd978-207">Per importare la topologia di Skype for Business Server, si utilizzerà il cmdlet [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) per recuperare informazioni su ogni pool in uso nell'organizzazione, quindi importare tali informazioni in Gestione statistiche.</span><span class="sxs-lookup"><span data-stu-id="fd978-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="fd978-208">Per importare la topologia di Skype for Business Server, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="fd978-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="fd978-209">In un host con i cmdlet di PowerShell di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="fd978-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="fd978-210">a.</span><span class="sxs-lookup"><span data-stu-id="fd978-210">a.</span></span> <span data-ttu-id="fd978-211">Eseguire il comando qui riportato:</span><span class="sxs-lookup"><span data-stu-id="fd978-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="fd978-212">b.</span><span class="sxs-lookup"><span data-stu-id="fd978-212">b.</span></span> <span data-ttu-id="fd978-213">Copiare il file "mypoolinfo.xml" nel server che esegue il listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="fd978-214">Nell'host che esegue il listener:</span><span class="sxs-lookup"><span data-stu-id="fd978-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="fd978-215">a.</span><span class="sxs-lookup"><span data-stu-id="fd978-215">a.</span></span> <span data-ttu-id="fd978-216">Eseguire PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd978-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="fd978-217">b.</span><span class="sxs-lookup"><span data-stu-id="fd978-217">b.</span></span> <span data-ttu-id="fd978-218">Passare alla directory in cui è installato listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="fd978-219">Il valore predefinito è:</span><span class="sxs-lookup"><span data-stu-id="fd978-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="fd978-220">Per verificare quali server vengono aggiunti e aggiornati, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fd978-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="fd978-221">Il comando seguente consente di visualizzare tutte le opzioni:</span><span class="sxs-lookup"><span data-stu-id="fd978-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="fd978-222">Per visualizzare le informazioni sul server attualmente importate, eseguire lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="fd978-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="fd978-223">Se si desidera monitorare i server non presenti nella topologia di Skype for Business Server, ad esempio un Exchange Server, è possibile eseguire un'importazione a server singolo nell'host che esegue il listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="fd978-224">Per eseguire un'importazione a server singolo, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="fd978-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="fd978-225">Passare alla directory in cui è installato listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="fd978-226">Il valore predefinito è:</span><span class="sxs-lookup"><span data-stu-id="fd978-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="fd978-227">Eseguire il comando qui riportato:</span><span class="sxs-lookup"><span data-stu-id="fd978-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="fd978-228">Risolvere i problemi relativi alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="fd978-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="fd978-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="fd978-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="fd978-230">Se l'avvio di un agente non riesce, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="fd978-231">L'agente è registrato in Gestione statistiche?</span><span class="sxs-lookup"><span data-stu-id="fd978-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="fd978-232">Assicurarsi di aver seguito le istruzioni per l'importazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="fd978-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="fd978-233">Vedere [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="fd978-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="fd978-234">Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi in un cluster AlwaysOn di SQL, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni in Importare la [topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="fd978-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="fd978-235">L'agente può contattare il listener?</span><span class="sxs-lookup"><span data-stu-id="fd978-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="fd978-236">Verificare che il servizio Listener sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fd978-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="fd978-237">Se non è in esecuzione, assicurati che Redis sia in esecuzione e quindi prova a riavviare il listener.</span><span class="sxs-lookup"><span data-stu-id="fd978-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="fd978-238">Verificare che la porta sia aperta per il servizio Listener e che il computer agente possa comunicare con la porta.</span><span class="sxs-lookup"><span data-stu-id="fd978-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="fd978-239">Per assicurarsi che Gestione statistiche raccoglie dati, puoi controllare il file CSV come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fd978-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="fd978-240">Il comando seguente recupera i nomi di archiviazione dei contatori:</span><span class="sxs-lookup"><span data-stu-id="fd978-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="fd978-241">Il comando successivo recupera i valori per i contatori specificati:</span><span class="sxs-lookup"><span data-stu-id="fd978-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="fd978-242">Per informazioni su tutti gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione, vedere [Troubleshoot Statistics Manager for Skype for Business Server.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="fd978-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="fd978-243">Creare un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="fd978-243">Create a self-signed certificate</span></span>
<span data-ttu-id="fd978-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="fd978-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="fd978-245">Microsoft consiglia vivamente di utilizzare un certificato firmato da un'autorità di certificazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="fd978-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="fd978-246">Tuttavia, se si desidera utilizzare un certificato autofirmato a scopo di test, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd978-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="fd978-247">Da una console di PowerShell mentre si è connessi come amministratore, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fd978-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="fd978-248">Digitare  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="fd978-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="fd978-249">Verrà aperto Gestione certificati per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="fd978-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="fd978-250">Passare a **Personale** e quindi aprire **Certificati**.</span><span class="sxs-lookup"><span data-stu-id="fd978-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="fd978-251">Fai clic con il pulsante destro del mouse su **StatsManListener- \> Tutte le attività- \> Gestisci chiavi private...**</span><span class="sxs-lookup"><span data-stu-id="fd978-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="fd978-252">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fd978-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="fd978-253">Nella casella **Immettere i nomi degli oggetti da selezionare** digitare quanto segue: Servizio di rete</span><span class="sxs-lookup"><span data-stu-id="fd978-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="fd978-254">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd978-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="fd978-255">In **Controllo completo** deselezionare la casella **di** controllo Consenti.</span><span class="sxs-lookup"><span data-stu-id="fd978-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="fd978-256">È necessario solo l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="fd978-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="fd978-257">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd978-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="fd978-258">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="fd978-258">For more information</span></span>
<span data-ttu-id="fd978-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="fd978-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="fd978-260">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd978-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="fd978-261">Pianificare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd978-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="fd978-262">Aggiornare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd978-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="fd978-263">[Risolvere i problemi di Gestione statistiche per Skype for Business Server](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="fd978-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>