---
title: Distribuire il bypass multimediale in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leggere questo argomento per informazioni sui passaggi per la distribuzione di bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359312"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="152b2-103">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="152b2-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="152b2-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="152b2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="152b2-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="152b2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="152b2-106">Leggere questo argomento per informazioni sui passaggi per la distribuzione di bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="152b2-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="152b2-107">Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente alla rete PSTN (Public Switched Telephone Network), ovvero a un gateway o a un session border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="152b2-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="152b2-108">Vedere anche [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="152b2-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="152b2-109">Abilita bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="152b2-109">Enable media bypass</span></span>

<span data-ttu-id="152b2-110">Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web bypass multimediale e attivare il bypass multimediale nella configurazione tenant.</span><span class="sxs-lookup"><span data-stu-id="152b2-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="152b2-111">Il servizio Web bypass multimediale viene distribuito automaticamente su ogni Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="152b2-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="152b2-112">Un amministratore tenant deve scegliere un nome per un servizio vocale ibrido (sito) e questo nome deve provenire da un dominio SIP registrato per la voce ibrida.</span><span class="sxs-lookup"><span data-stu-id="152b2-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="152b2-113">Il nome del servizio deve essere lo stesso in tutti gli apparecchi del connettore Cloud e in tutti i siti PSTN indipendentemente dalla posizione del client.</span><span class="sxs-lookup"><span data-stu-id="152b2-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="152b2-114">Il servizio Web deve essere disponibile solo all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="152b2-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="152b2-115">Un amministratore tenant deve configurare un record a DNS nell'Active Directory di produzione interna.</span><span class="sxs-lookup"><span data-stu-id="152b2-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="152b2-116">Se si dispone di un ambiente multi-sito complesso, vedere l'esempio seguente [: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="152b2-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="152b2-117">Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.</span><span class="sxs-lookup"><span data-stu-id="152b2-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="152b2-118">Dopo aver configurato DNS, connettersi a Skype for business online tramite Remote PowerShell con le credenziali di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="152b2-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="152b2-119">Per ulteriori informazioni, vedere [configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="152b2-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="152b2-120">Nella sessione di PowerShell, immettere i seguenti comandi per abilitare il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="152b2-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="152b2-121">L'abilitazione del bypass multimediale è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="152b2-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="152b2-122">Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. consente di creare solo le impostazioni in memoria.</span><span class="sxs-lookup"><span data-stu-id="152b2-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="152b2-123">L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="152b2-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="152b2-124">Per ulteriori informazioni, vedere [esempio: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="152b2-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="152b2-125">La replica tra i componenti locali e online può richiedere fino a 24 ore, pertanto Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="152b2-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="152b2-126">Confermare le impostazioni di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="152b2-126">Confirm media bypass settings</span></span>

<span data-ttu-id="152b2-127">È possibile controllare le impostazioni di bypass multimediale come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="152b2-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="152b2-128">Per controllare la replica online nel pool tenant, eseguire il comando riportato di seguito in Remote PowerShell:</span><span class="sxs-lookup"><span data-stu-id="152b2-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="152b2-129">Per verificare la replica locale, connettersi al Cloud Connector Mediation Server, eseguire il comando seguente in PowerShell e verificare che Enabled = true e AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="152b2-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="152b2-130">Per controllare le impostazioni del client, disconnettersi dal client Skype for business, eseguire l'accesso e verificare che il client abbia ricevuto l'URL del servizio, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="152b2-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="152b2-131">Aprire%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="152b2-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="152b2-132">Cercare hybridconfigserviceinternalurl e confermare che l'URL corrisponda a quello definito.</span><span class="sxs-lookup"><span data-stu-id="152b2-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="152b2-133">Modificare i parametri di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="152b2-133">Change media bypass parameters</span></span>

<span data-ttu-id="152b2-134">Gli amministratori tenant sono in grado di modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="152b2-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="152b2-135">I client devono disconnettersi ed eseguire l'accesso per ottenere il nuovo nome del servizio e riconoscere la modifica.</span><span class="sxs-lookup"><span data-stu-id="152b2-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="152b2-136">Disattiva temporaneamente il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="152b2-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="152b2-137">Questo scenario potrebbe essere utile per la risoluzione dei problemi o la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="152b2-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="152b2-138">Per disabilitare il servizio, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="152b2-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="152b2-139">Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti i connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="152b2-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="152b2-140">Per controllare lo stato della replica, eseguire il seguente cmdlet in PowerShell su cloud Connector Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="152b2-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="152b2-141">Dopo la replica delle modifiche, il servizio Web sul Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="152b2-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="152b2-142">Disabilitare il bypass multimediale in modo permanente</span><span class="sxs-lookup"><span data-stu-id="152b2-142">Disable media bypass permanently</span></span>

<span data-ttu-id="152b2-143">Per disabilitare definitivamente il bypass multimediale, è necessario che un amministratore tenant esegua i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="152b2-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="152b2-144">Anche un amministratore dovrà rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni.</span><span class="sxs-lookup"><span data-stu-id="152b2-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="152b2-145">Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti gli apparecchi del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="152b2-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="152b2-146">Esempio: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi</span><span class="sxs-lookup"><span data-stu-id="152b2-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="152b2-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="152b2-147"><a name="Example"> </a></span></span>

<span data-ttu-id="152b2-148">I client riceveranno l'indirizzo Web del servizio Web bypass multimediale da un server DNS interno.</span><span class="sxs-lookup"><span data-stu-id="152b2-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="152b2-149">Il nome del servizio Web sarà lo stesso in tutti i siti PSTN dei connettori cloud e del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="152b2-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="152b2-150">In un ambiente multisito complesso, è consigliabile utilizzare il criterio DNS di Windows 2016 per la gestione del traffico basato sulla posizione geografica, in modo che i client possano essere reindirizzati al servizio Web locale per la rete.</span><span class="sxs-lookup"><span data-stu-id="152b2-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="152b2-151">Per ulteriori informazioni sui criteri DNS di Windows 2016, vedere [Use DNS Policy for Geo-location based Traffic Management with primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="152b2-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="152b2-152">Di seguito è riportato un esempio di configurazione per una società con diversi siti che utilizzano i criteri DNS di Windows 2016 per la gestione del traffico basato sulla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="152b2-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="152b2-153">Il nome del servizio di bypass è' hybridvoice.adatum.biz '.</span><span class="sxs-lookup"><span data-stu-id="152b2-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="152b2-154">Il sito di Amsterdam ha quattro appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="152b2-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="152b2-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="152b2-155">192.168.1.45</span></span>
    
- <span data-ttu-id="152b2-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="152b2-156">192.168.1.46</span></span>
    
- <span data-ttu-id="152b2-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="152b2-157">192.168.1.47</span></span>
    
- <span data-ttu-id="152b2-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="152b2-158">192.168.1.48</span></span>
    
<span data-ttu-id="152b2-159">Il sito di Seattle dispone di tre appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="152b2-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="152b2-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="152b2-160">10.10.1.8</span></span>
    
- <span data-ttu-id="152b2-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="152b2-161">10.10.1.9</span></span>
    
- <span data-ttu-id="152b2-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="152b2-162">10.10.1.10</span></span>
    
<span data-ttu-id="152b2-163">Utilizzando la gestione del traffico basato sulla posizione geografica, i server DNS verrebbero configurati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="152b2-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="152b2-164">Creare subnet client DNS per le subnet di Amsterdam e Seattle.</span><span class="sxs-lookup"><span data-stu-id="152b2-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="152b2-165">Creare gli ambiti delle aree DNS per adatum.biz sia per Amsterdam che per Seattle.</span><span class="sxs-lookup"><span data-stu-id="152b2-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="152b2-166">Creare record DNS in ogni ambito della zona DNS.</span><span class="sxs-lookup"><span data-stu-id="152b2-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="152b2-167">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="152b2-167">Amsterdam</span></span>
    
   - <span data-ttu-id="152b2-168">Digitare A;</span><span class="sxs-lookup"><span data-stu-id="152b2-168">Type A;</span></span>
    
   - <span data-ttu-id="152b2-169">Nome: HybridVoice nella zona DNS di adatum.biz</span><span class="sxs-lookup"><span data-stu-id="152b2-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="152b2-170">Destinazione: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="152b2-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="152b2-171">Creare record aggiuntivi per altri Mediation Server</span><span class="sxs-lookup"><span data-stu-id="152b2-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="152b2-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="152b2-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="152b2-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="152b2-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="152b2-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="152b2-174">192.168.1.48</span></span>
    
     <span data-ttu-id="152b2-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="152b2-175">Seattle</span></span>
    
   - <span data-ttu-id="152b2-176">Digitare A</span><span class="sxs-lookup"><span data-stu-id="152b2-176">Type A</span></span>
    
   - <span data-ttu-id="152b2-177">Nome: HybridVoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="152b2-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="152b2-178">Destinazione: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="152b2-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="152b2-179">Creare record aggiuntivi per altri Mediation Server</span><span class="sxs-lookup"><span data-stu-id="152b2-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="152b2-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="152b2-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="152b2-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="152b2-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="152b2-182">Creare il criterio DNS che connette le subnet client agli ambiti di area corretti per garantire la risoluzione DNS desiderata.</span><span class="sxs-lookup"><span data-stu-id="152b2-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="152b2-183">A questo punto, i client che eseguono query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno gli indirizzi 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che eseguono lo stesso modulo di query Seattle restituiranno 10.10.1.8, 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="152b2-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="152b2-184">Se l'apparecchio CCE non sembra ricevere le impostazioni aggiornate, controllare se l'apparecchio è in grado di contattare il tenant tramite Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="152b2-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="152b2-185">È possibile utilizzare Remote PowerShell per controllare lo stato dell'accessorio con Get-CsHybridPSTNAppliance oppure utilizzare PowerShell nell'host CCE per controllare lo stato con Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="152b2-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="152b2-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="152b2-186">See also</span></span>
<span data-ttu-id="152b2-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="152b2-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="152b2-188">Pianificare il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="152b2-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
