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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leggere questo argomento per informazioni sui passaggi per distribuire il bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.
ms.openlocfilehash: 63d8f9e289c38a50444bee2667c98543e09b875d
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003486"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="cf1ec-103">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="cf1ec-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="cf1ec-104">Leggere questo argomento per informazioni sui passaggi per distribuire il bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="cf1ec-105">Il bypass multimediale consente a un client di inviare elementi multimediali direttamente alla rete PSTN (Public Switched Telephone Network) Next Hop, ovvero un gateway o un border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="cf1ec-106">Vedere anche [piano per il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="cf1ec-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="cf1ec-107">Abilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="cf1ec-107">Enable media bypass</span></span>

<span data-ttu-id="cf1ec-108">Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web di bypass multimediale e attivare il bypass multimediale nella configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="cf1ec-109">Il servizio Web di bypass multimediale viene distribuito automaticamente in ogni Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="cf1ec-110">Un amministratore del tenant deve selezionare un nome per un servizio vocale ibrido (sito) e questo nome deve essere da un dominio SIP registrato per la voce ibrida.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="cf1ec-111">Il nome del servizio deve essere lo stesso in tutti gli elettrodomestici di Cloud Connector e in tutti i siti PSTN indipendentemente dalla posizione del client.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="cf1ec-112">Il servizio Web dovrebbe essere disponibile solo internamente alla rete.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="cf1ec-113">Un amministratore del tenant deve configurare un record DNS nell'Active Directory di produzione interna.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="cf1ec-114">Se si dispone di un ambiente multisito complesso, vedere l'esempio seguente [: record DNS del sito Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="cf1ec-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="cf1ec-115">Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="cf1ec-116">Dopo aver configurato il DNS, connettersi a Skype for business online usando Remote PowerShell con le credenziali di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="cf1ec-117">Per altre informazioni, vedere [configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="cf1ec-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="cf1ec-118">Nella sessione di PowerShell Immetti i comandi seguenti per abilitare il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="cf1ec-119">L'abilitazione del bypass multimediale è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="cf1ec-120">Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. Crea solo le impostazioni in memoria.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="cf1ec-121">L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="cf1ec-122">Per altre informazioni, vedere [esempio: record DNS del sito Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="cf1ec-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="cf1ec-123">La replica tra i componenti locali e online può richiedere fino a 24 ore, quindi Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="cf1ec-124">Confermare le impostazioni di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="cf1ec-124">Confirm media bypass settings</span></span>

<span data-ttu-id="cf1ec-125">È possibile controllare le impostazioni di bypass multimediale nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="cf1ec-126">Per controllare la replica online nel pool di tenant, eseguire il comando seguente in PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="cf1ec-127">Per verificare la replica locale, connettersi a Cloud Connector Mediation Servers, eseguire il comando seguente in PowerShell e verificare che Enabled = true e AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="cf1ec-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="cf1ec-128">Per controllare le impostazioni del client, disconnettersi dal client Skype for business, accedere di nuovo e verificare che il client abbia ricevuto l'URL del servizio nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="cf1ec-129">Aprire%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="cf1ec-130">Cercare hybridconfigserviceinternalurl e verificare che l'URL corrisponda a quello definito.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="cf1ec-131">Modificare i parametri di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="cf1ec-131">Change media bypass parameters</span></span>

<span data-ttu-id="cf1ec-132">Gli amministratori del tenant possono modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="cf1ec-133">I client devono disconnettersi ed eseguire l'accesso per ottenere il nome del nuovo servizio e riconoscere la modifica.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="cf1ec-134">Disabilitare temporaneamente il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="cf1ec-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="cf1ec-135">Questo scenario potrebbe essere utile per la risoluzione dei problemi o la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-135">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="cf1ec-136">Per disabilitare il servizio, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-136">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="cf1ec-137">Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti i connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="cf1ec-138">Per verificare lo stato della replica, eseguire il cmdlet seguente in PowerShell in server di mediazione Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="cf1ec-139">Dopo la replica delle modifiche, il servizio Web su Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="cf1ec-140">Disabilitare il bypass multimediale in modo permanente</span><span class="sxs-lookup"><span data-stu-id="cf1ec-140">Disable media bypass permanently</span></span>

<span data-ttu-id="cf1ec-141">Per disabilitare definitivamente il bypass multimediale, è necessario che un amministratore del tenant esegua i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="cf1ec-142">Un amministratore dovrà inoltre rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="cf1ec-143">Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo per modificare la replica in tutti gli elettrodomestici di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="cf1ec-144">Esempio: record DNS del sito Web di bypass multimediale in ambienti multisito complessi</span><span class="sxs-lookup"><span data-stu-id="cf1ec-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="cf1ec-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1ec-145"></span></span>

<span data-ttu-id="cf1ec-146">I client riceveranno l'indirizzo Web del servizio Web di bypass multimediale da un server DNS interno.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="cf1ec-147">Il nome del servizio Web sarà lo stesso in tutti i siti PSTN di appliance Connector e Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="cf1ec-148">In un ambiente multisito complesso è consigliabile usare il criterio DNS di Windows 2016 per la gestione del traffico basato su Geo-location, in modo che i client possano essere reindirizzati al servizio Web locale per la rete.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="cf1ec-149">Per altre informazioni sui criteri DNS di Windows 2016, vedere [usare i criteri DNS per la gestione del traffico basato su Geo-location con i server primari](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="cf1ec-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="cf1ec-150">Di seguito è riportato un esempio di configurazione per una società con diversi siti che usano i criteri DNS di Windows 2016 per la gestione del traffico basata su Geo-location.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="cf1ec-151">Il nome del servizio di bypass è "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="cf1ec-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="cf1ec-152">Il sito di Amsterdam include quattro appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="cf1ec-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="cf1ec-153">192.168.1.45</span></span>
    
- <span data-ttu-id="cf1ec-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="cf1ec-154">192.168.1.46</span></span>
    
- <span data-ttu-id="cf1ec-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="cf1ec-155">192.168.1.47</span></span>
    
- <span data-ttu-id="cf1ec-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="cf1ec-156">192.168.1.48</span></span>
    
<span data-ttu-id="cf1ec-157">Il sito di Seattle include tre appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="cf1ec-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="cf1ec-158">10.10.1.8</span></span>
    
- <span data-ttu-id="cf1ec-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="cf1ec-159">10.10.1.9</span></span>
    
- <span data-ttu-id="cf1ec-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="cf1ec-160">10.10.1.10</span></span>
    
<span data-ttu-id="cf1ec-161">Usando la gestione del traffico basato su Geo-location, i server DNS verrebbero configurati come segue:</span><span class="sxs-lookup"><span data-stu-id="cf1ec-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="cf1ec-162">Creare subnet client DNS per le subnet di Amsterdam e Seattle.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="cf1ec-163">Creare ambiti di zona DNS per adatum.biz sia per Amsterdam che per Seattle.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="cf1ec-164">Creare record DNS in ogni ambito di area DNS.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="cf1ec-165">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="cf1ec-165">Amsterdam</span></span>
    
   - <span data-ttu-id="cf1ec-166">Digitare A;</span><span class="sxs-lookup"><span data-stu-id="cf1ec-166">Type A;</span></span>
    
   - <span data-ttu-id="cf1ec-167">Nome: HybridVoice nella zona DNS di adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cf1ec-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="cf1ec-168">Destinazione: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="cf1ec-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="cf1ec-169">Creare record aggiuntivi per altri Mediation Server</span><span class="sxs-lookup"><span data-stu-id="cf1ec-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="cf1ec-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="cf1ec-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="cf1ec-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="cf1ec-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="cf1ec-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="cf1ec-172">192.168.1.48</span></span>
    
     <span data-ttu-id="cf1ec-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="cf1ec-173">Seattle</span></span>
    
   - <span data-ttu-id="cf1ec-174">Digitare un</span><span class="sxs-lookup"><span data-stu-id="cf1ec-174">Type A</span></span>
    
   - <span data-ttu-id="cf1ec-175">Nome: HybridVoice nella zona DNS di adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cf1ec-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="cf1ec-176">Destinazione: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="cf1ec-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="cf1ec-177">Creare record aggiuntivi per altri Mediation Server</span><span class="sxs-lookup"><span data-stu-id="cf1ec-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="cf1ec-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="cf1ec-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="cf1ec-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="cf1ec-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="cf1ec-180">Creare i criteri DNS che collegano le subnet client agli ambiti di zona appropriati per garantire la risoluzione DNS desiderata.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="cf1ec-181">A questo punto, i client che eseguono query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno gli indirizzi 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che eseguono lo stesso modulo di query Seattle restituiranno 10.10.1.8. 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="cf1ec-182">Se l'accessorio CCE non sembra ricevere le impostazioni aggiornate, verificare se l'appliance è in grado di contattare il tenant tramite una versione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="cf1ec-183">Puoi usare PowerShell remoto per controllare lo stato dell'appliance con Get-CsHybridPSTNAppliance oppure usare PowerShell nell'host CCE per verificare lo stato con Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="cf1ec-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1ec-184">See also</span></span>
<span data-ttu-id="cf1ec-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1ec-185"></span></span>

[<span data-ttu-id="cf1ec-186">Pianificare il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="cf1ec-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
