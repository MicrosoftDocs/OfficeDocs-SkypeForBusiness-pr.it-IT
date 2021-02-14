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
description: Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359312"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="6a8cc-103">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6a8cc-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="6a8cc-104">Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6a8cc-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="6a8cc-106">Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="6a8cc-107">Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente all'hop successivo PSTN (Public Switched Telephone Network), ovvero un gateway o un Session Border Controller (SBC), ed eliminare il componente Cloud Connector Edition dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="6a8cc-108">Vedere anche [Pianificare il bypass multimediale in Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="6a8cc-109">Abilita bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6a8cc-109">Enable media bypass</span></span>

<span data-ttu-id="6a8cc-110">Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web di bypass multimediale e attivare il bypass multimediale nella configurazione tenant.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="6a8cc-111">Il servizio Web di bypass multimediale viene distribuito automaticamente in ogni Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="6a8cc-112">Un amministratore tenant deve selezionare un nome per un servizio vocale ibrido (sito) e questo nome deve derivare da un dominio SIP registrato per la voce ibrida.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="6a8cc-113">Il nome del servizio deve essere lo stesso in tutti i dispositivi Cloud Connector e in tutti i siti PSTN indipendentemente dalla posizione del client.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="6a8cc-114">Il servizio Web deve essere disponibile solo internamente nella rete.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="6a8cc-115">Un amministratore tenant deve configurare un record A DNS in Active Directory di produzione interna.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="6a8cc-116">Se si dispone di un ambiente multisnode complesso, vedere l'esempio in Esempio: record DNS del sito Web bypass multimediale [in ambienti multisodei complessi.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="6a8cc-117">Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="6a8cc-118">Dopo aver configurato DNS, connettersi a Skype for Business online usando Remote PowerShell con le credenziali di amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="6a8cc-119">Per ulteriori informazioni, vedere [Configurare il computer per Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="6a8cc-120">Nella sessione di PowerShell, immettere i comandi seguenti per abilitare il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="6a8cc-121">L'abilitazione del bypass multimediale è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="6a8cc-122">Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. crea solo le impostazioni in memoria.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="6a8cc-123">L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="6a8cc-124">Per ulteriori informazioni, vedere [Example: media bypass web site DNS records in complex multi-site environments.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="6a8cc-125">La replica tra i componenti locali e online può richiedere fino a 24 ore, pertanto Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="6a8cc-126">Verificare le impostazioni di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6a8cc-126">Confirm media bypass settings</span></span>

<span data-ttu-id="6a8cc-127">Puoi controllare le impostazioni di bypass multimediale come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="6a8cc-128">Per controllare la replica online nel pool tenant, eseguire il comando seguente in PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="6a8cc-129">Per controllare la replica locale, connettersi ai Mediation Server cloud Connector, eseguire il comando seguente in PowerShell e verificare che Enabled=True e AlwaysBypass=True</span><span class="sxs-lookup"><span data-stu-id="6a8cc-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="6a8cc-130">Per controllare le impostazioni del client, disconnettersi dal client Skype for Business, accedere di nuovo e verificare che il client abbia ricevuto l'URL del servizio nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="6a8cc-131">Aprire %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="6a8cc-132">Cercare hybridconfigserviceinternalurl e verificare che l'URL corrisponda a quello definito.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="6a8cc-133">Modificare i parametri di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6a8cc-133">Change media bypass parameters</span></span>

<span data-ttu-id="6a8cc-134">Gli amministratori tenant possono modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="6a8cc-135">I client devono disconnettersi e accedere per ottenere il nuovo nome del servizio e riconoscere la modifica.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="6a8cc-136">Disabilitare temporaneamente il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6a8cc-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="6a8cc-137">Questo scenario può essere utile per la risoluzione dei problemi o la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="6a8cc-138">Per disabilitare il servizio, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="6a8cc-139">Dopo aver apportato la modifica, la replica delle modifiche in tutti i connettori cloud potrebbe richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="6a8cc-140">Per controllare lo stato della replica, eseguire il cmdlet seguente in PowerShell nei Mediation Server cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="6a8cc-141">Dopo la replica delle modifiche, il servizio Web nel Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="6a8cc-142">Disabilitare in modo permanente il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6a8cc-142">Disable media bypass permanently</span></span>

<span data-ttu-id="6a8cc-143">Per disabilitare definitivamente il bypass multimediale, un amministratore tenant deve eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="6a8cc-144">Un amministratore dovrà anche rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="6a8cc-145">Dopo aver apportato la modifica, potrebbe essere necessario del tempo prima che le modifiche vengano replicate in tutte le appliance del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="6a8cc-146">Esempio: record DNS del sito Web bypass multimediale in ambienti multisolutore complessi</span><span class="sxs-lookup"><span data-stu-id="6a8cc-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="6a8cc-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="6a8cc-147"><a name="Example"> </a></span></span>

<span data-ttu-id="6a8cc-148">I client riceveranno l'indirizzo Web del servizio Web di bypass multimediale da un server DNS interno.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="6a8cc-149">Il nome del servizio Web sarà lo stesso per tutti i dispositivi Cloud Connector e i siti PSTN di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="6a8cc-150">In un ambiente multisito complesso, è consigliabile usare i criteri DNS di Windows 2016 per la gestione del traffico basato su Geo-Location, in modo che i client possano essere reindirizzati al servizio Web locale per la propria rete.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="6a8cc-151">Per ulteriori informazioni sui criteri DNS di Windows 2016, vedere Use [DNS Policy for Geo-Location Based Traffic Management with Primary Servers.](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)</span><span class="sxs-lookup"><span data-stu-id="6a8cc-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="6a8cc-152">Di seguito è riportato un esempio di configurazione per una società con diversi siti che usano i criteri DNS di Windows 2016 per la Geo-Location del traffico basato su windows.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="6a8cc-153">Il nome del servizio di bypass è "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="6a8cc-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="6a8cc-154">Il sito di Amsterdam dispone di quattro appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="6a8cc-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="6a8cc-155">192.168.1.45</span></span>
    
- <span data-ttu-id="6a8cc-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="6a8cc-156">192.168.1.46</span></span>
    
- <span data-ttu-id="6a8cc-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="6a8cc-157">192.168.1.47</span></span>
    
- <span data-ttu-id="6a8cc-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="6a8cc-158">192.168.1.48</span></span>
    
<span data-ttu-id="6a8cc-159">Il sito di Seattle dispone di tre appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="6a8cc-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="6a8cc-160">10.10.1.8</span></span>
    
- <span data-ttu-id="6a8cc-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="6a8cc-161">10.10.1.9</span></span>
    
- <span data-ttu-id="6a8cc-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="6a8cc-162">10.10.1.10</span></span>
    
<span data-ttu-id="6a8cc-163">Utilizzando Geo-Location traffico basato su server DNS, i server DNS verrebbero configurati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6a8cc-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="6a8cc-164">Creare subnet client DNS per entrambe le subnet di Amsterdam e Seattle.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="6a8cc-165">Creare ambiti di zona DNS per adatum.biz sia per Amsterdam che per Seattle.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="6a8cc-166">Creare record DNS in ogni ambito di zona DNS.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="6a8cc-167">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="6a8cc-167">Amsterdam</span></span>
    
   - <span data-ttu-id="6a8cc-168">Tipo A;</span><span class="sxs-lookup"><span data-stu-id="6a8cc-168">Type A;</span></span>
    
   - <span data-ttu-id="6a8cc-169">Nome : hybridvoice nella adatum.biz DNS</span><span class="sxs-lookup"><span data-stu-id="6a8cc-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="6a8cc-170">Destinazione: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="6a8cc-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="6a8cc-171">Creare record aggiuntivi per mediation server aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="6a8cc-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="6a8cc-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="6a8cc-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="6a8cc-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="6a8cc-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="6a8cc-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="6a8cc-174">192.168.1.48</span></span>
    
     <span data-ttu-id="6a8cc-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="6a8cc-175">Seattle</span></span>
    
   - <span data-ttu-id="6a8cc-176">Tipo A</span><span class="sxs-lookup"><span data-stu-id="6a8cc-176">Type A</span></span>
    
   - <span data-ttu-id="6a8cc-177">Name : hybridvoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="6a8cc-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="6a8cc-178">Destinazione: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="6a8cc-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="6a8cc-179">Creare record aggiuntivi per mediation server aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="6a8cc-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="6a8cc-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="6a8cc-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="6a8cc-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="6a8cc-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="6a8cc-182">Creare i criteri DNS che connettono le subnet client agli ambiti di zona appropriati per garantire la risoluzione DNS desiderata.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="6a8cc-183">A questo punto, i client che effettuano query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno il valore 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che effettuano lo stesso modulo di query Seattle restituiranno 10.10.1.8, 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="6a8cc-184">Se l'applicazione CCE non sembra ottenere le impostazioni aggiornate, verificare se l'applicazione è in grado di contattare il tenant tramite Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="6a8cc-185">È possibile utilizzare Remote PowerShell per controllare lo stato dell'applicazione con Get-CsHybridPSTNAppliance o utilizzare PowerShell nell'host CCE per controllare lo stato con Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="6a8cc-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="6a8cc-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a8cc-186">See also</span></span>
<span data-ttu-id="6a8cc-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="6a8cc-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="6a8cc-188">Pianificare il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6a8cc-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
