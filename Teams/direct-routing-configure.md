---
title: Configurare il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: 4013e0fd914630f154f407ad9c70e2c6915723f5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464612"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="1965c-103">Configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="1965c-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="1965c-104">Vedere la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificare la procedura e su come distribuirla: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="1965c-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="1965c-105">Se non è già stato fatto, leggere [pianificare il routing diretto](direct-routing-plan.md) per i prerequisiti e rivedere altri passaggi che è necessario eseguire prima di configurare la rete del sistema telefonico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1965c-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="1965c-106">Questo articolo descrive come configurare il routing diretto di Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="1965c-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="1965c-107">Descrive come associare un SBC (Session Border Controller) supportato a routing diretto e come configurare gli utenti di Microsoft teams per usare il routing diretto per la connessione alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1965c-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1965c-108">Per completare la procedura descritta in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1965c-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1965c-109">Per altre informazioni sull'uso di PowerShell, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1965c-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="1965c-110">È consigliabile verificare che SBC sia già stato configurato come consigliato dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="1965c-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="1965c-111">Documentazione di distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="1965c-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="1965c-112">Documentazione di distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="1965c-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="1965c-113">Documentazione sulla distribuzione delle comunicazioni della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="1965c-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="1965c-114">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="1965c-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="1965c-115">È possibile configurare il sistema telefonico Microsoft e consentire agli utenti di usare il routing diretto, quindi configurare Microsoft teams come client chiamante preferito completando le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="1965c-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="1965c-116">Associare il SBC a un sistema telefonico Microsoft e convalidare l'associazione</span><span class="sxs-lookup"><span data-stu-id="1965c-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="1965c-117">Abilitare gli utenti per il servizio di routing diretto</span><span class="sxs-lookup"><span data-stu-id="1965c-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="1965c-118">Verificare che Microsoft teams sia il client chiamante preferito per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1965c-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="1965c-119">Associare il SBC al servizio di routing diretto del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="1965c-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="1965c-120">Di seguito sono riportati i tre passaggi di alto livello per consentire di connettersi o associare l'SBC all'interfaccia di routing diretto:</span><span class="sxs-lookup"><span data-stu-id="1965c-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="1965c-121">Connettersi all'interfaccia di amministrazione di **Skype for business online** con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1965c-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="1965c-122">Associare il SBC</span><span class="sxs-lookup"><span data-stu-id="1965c-122">Pair the SBC</span></span> 
- <span data-ttu-id="1965c-123">Convalidare l'associazione</span><span class="sxs-lookup"><span data-stu-id="1965c-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="1965c-124">Connettersi a Skype for business online tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="1965c-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="1965c-125">Puoi usare una sessione di PowerShell connessa al tenant per associare il SBC all'interfaccia di routing diretta.</span><span class="sxs-lookup"><span data-stu-id="1965c-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="1965c-126">Per aprire una sessione di PowerShell, seguire i passaggi descritti in [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1965c-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="1965c-127">Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per la gestione di SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="1965c-128">Per convalidare i comandi, digitare o copiare/incollare il comando seguente nella sessione di PowerShell e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1965c-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="1965c-129">Il comando restituirà le quattro funzioni visualizzate in questa sezione che consente di gestire il SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="1965c-130">Associare il SBC al tenant</span><span class="sxs-lookup"><span data-stu-id="1965c-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="1965c-131">Per associare il SBC al tenant, nella sessione di PowerShell digitare il testo seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1965c-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="1965c-132">Ti consigliamo vivamente di impostare un limite massimo per le chiamate in SBC, usando le informazioni che puoi trovare nella documentazione SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="1965c-133">Il limite attiverà una notifica se SBC è a livello di capacità.</span><span class="sxs-lookup"><span data-stu-id="1965c-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="1965c-134">Puoi associare l'SBC solo se la parte del dominio del relativo nome FQDN corrisponde a uno dei domini registrati nel tenant, eccetto \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="1965c-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="1965c-135">L' \*uso dei nomi di dominio con estensione onmicrosoft.com non è supportato per il nome FQDN di SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="1965c-136">Se ad esempio sono presenti due nomi di dominio:</span><span class="sxs-lookup"><span data-stu-id="1965c-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="1965c-137">**Contoso**. com</span><span class="sxs-lookup"><span data-stu-id="1965c-137">**contoso**.com</span></span><br/><span data-ttu-id="1965c-138">**Contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="1965c-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="1965c-139">Per il nome SBC, è possibile usare il nome sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1965c-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="1965c-140">Se si tenta di associare l'SBC con un nome SBC. contoso. ABC, il sistema non lo consente, poiché il dominio non è di proprietà del tenant.</span><span class="sxs-lookup"><span data-stu-id="1965c-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="1965c-141">Oltre al dominio registrato nel tenant, è importante che ci sia un utente con tale dominio e una licenza E3 o E5 assegnata.</span><span class="sxs-lookup"><span data-stu-id="1965c-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="1965c-142">In caso contrario, verrà visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="1965c-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="1965c-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="1965c-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="1965c-144">Restituisce</span><span class="sxs-lookup"><span data-stu-id="1965c-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="1965c-145">Sono disponibili altre opzioni che possono essere impostate durante il processo di associazione.</span><span class="sxs-lookup"><span data-stu-id="1965c-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="1965c-146">Nell'esempio precedente vengono tuttavia visualizzati solo i parametri minimi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="1965c-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="1965c-147">Nella tabella seguente sono elencati i parametri aggiuntivi che è possibile usare per impostare i parametri per`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="1965c-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="1965c-148">Obbligatorio?</span><span class="sxs-lookup"><span data-stu-id="1965c-148">Required?</span></span>|<span data-ttu-id="1965c-149">Nome</span><span class="sxs-lookup"><span data-stu-id="1965c-149">Name</span></span>|<span data-ttu-id="1965c-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1965c-150">Description</span></span>|<span data-ttu-id="1965c-151">Predefinita</span><span class="sxs-lookup"><span data-stu-id="1965c-151">Default</span></span>|<span data-ttu-id="1965c-152">Valori possibili</span><span class="sxs-lookup"><span data-stu-id="1965c-152">Possible values</span></span>|<span data-ttu-id="1965c-153">Tipo e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1965c-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1965c-154">Sì</span><span class="sxs-lookup"><span data-stu-id="1965c-154">Yes</span></span>|<span data-ttu-id="1965c-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="1965c-155">FQDN</span></span>|<span data-ttu-id="1965c-156">Nome FQDN di SBC</span><span class="sxs-lookup"><span data-stu-id="1965c-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="1965c-157">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1965c-157">None</span></span>|<span data-ttu-id="1965c-158">Nome NoneFQDN, limite di 63 caratteri</span><span class="sxs-lookup"><span data-stu-id="1965c-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="1965c-159">Stringa, elenco dei caratteri consentiti e non consentiti nelle convenzioni di [denominazione in Active Directory per computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="1965c-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="1965c-160">No</span><span class="sxs-lookup"><span data-stu-id="1965c-160">No</span></span>|<span data-ttu-id="1965c-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="1965c-161">MediaBypass</span></span> |<span data-ttu-id="1965c-162">Parametro riservato per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1965c-162">The parameter reserved for future use.</span></span> <span data-ttu-id="1965c-163">Il parametro indicato da SBC supporta il bypass multimediale e l'amministratore vuole usarlo.</span><span class="sxs-lookup"><span data-stu-id="1965c-163">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="1965c-164">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1965c-164">None</span></span>|<span data-ttu-id="1965c-165">True</span><span class="sxs-lookup"><span data-stu-id="1965c-165">True</span></span><br/><span data-ttu-id="1965c-166">False</span><span class="sxs-lookup"><span data-stu-id="1965c-166">False</span></span>|<span data-ttu-id="1965c-167">Boolean</span><span class="sxs-lookup"><span data-stu-id="1965c-167">Boolean</span></span>|
|<span data-ttu-id="1965c-168">Sì</span><span class="sxs-lookup"><span data-stu-id="1965c-168">Yes</span></span>|<span data-ttu-id="1965c-169">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="1965c-169">SipSignallingPort</span></span> |<span data-ttu-id="1965c-170">Porta di ascolto usata per comunicare con i servizi di routing diretto usando il protocollo Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="1965c-170">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="1965c-171">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1965c-171">None</span></span>|<span data-ttu-id="1965c-172">Qualsiasi porta</span><span class="sxs-lookup"><span data-stu-id="1965c-172">Any port</span></span>|<span data-ttu-id="1965c-173">da 0 a 65535</span><span class="sxs-lookup"><span data-stu-id="1965c-173">0 to 65535</span></span> |
|<span data-ttu-id="1965c-174">No</span><span class="sxs-lookup"><span data-stu-id="1965c-174">No</span></span>|<span data-ttu-id="1965c-175">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="1965c-175">FailoverTimeSeconds</span></span> |<span data-ttu-id="1965c-176">Se impostato su 10 (valore predefinito), le chiamate in uscita non risposte dal gateway entro 10 secondi vengono instradate al successivo trunk disponibile. Se non sono presenti trunk aggiuntivi, la chiamata viene automaticamente eliminata.</span><span class="sxs-lookup"><span data-stu-id="1965c-176">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="1965c-177">In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.</span><span class="sxs-lookup"><span data-stu-id="1965c-177">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="1965c-178">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="1965c-178">The default value is 10.</span></span>|<span data-ttu-id="1965c-179">10</span><span class="sxs-lookup"><span data-stu-id="1965c-179">10</span></span>|<span data-ttu-id="1965c-180">Numero</span><span class="sxs-lookup"><span data-stu-id="1965c-180">Number</span></span>|<span data-ttu-id="1965c-181">Int</span><span class="sxs-lookup"><span data-stu-id="1965c-181">Int</span></span>|
|<span data-ttu-id="1965c-182">No</span><span class="sxs-lookup"><span data-stu-id="1965c-182">No</span></span>|<span data-ttu-id="1965c-183">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="1965c-183">ForwardCallHistory</span></span> |<span data-ttu-id="1965c-184">Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.</span><span class="sxs-lookup"><span data-stu-id="1965c-184">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="1965c-185">Se abilitata, il proxy PSTN di Office 365 invia due intestazioni: History-info e riferimento.</span><span class="sxs-lookup"><span data-stu-id="1965c-185">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="1965c-186">Il valore predefinito è **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="1965c-186">The default value is **False** ($False).</span></span> |<span data-ttu-id="1965c-187">False</span><span class="sxs-lookup"><span data-stu-id="1965c-187">False</span></span>|<span data-ttu-id="1965c-188">True</span><span class="sxs-lookup"><span data-stu-id="1965c-188">True</span></span><br/><span data-ttu-id="1965c-189">False</span><span class="sxs-lookup"><span data-stu-id="1965c-189">False</span></span>|<span data-ttu-id="1965c-190">Boolean</span><span class="sxs-lookup"><span data-stu-id="1965c-190">Boolean</span></span>|
|<span data-ttu-id="1965c-191">No</span><span class="sxs-lookup"><span data-stu-id="1965c-191">No</span></span>|<span data-ttu-id="1965c-192">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="1965c-192">ForwardPAI</span></span>|<span data-ttu-id="1965c-193">Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="1965c-193">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="1965c-194">L'intestazione PAI consente di verificare l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1965c-194">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="1965c-195">Se è abilitata anche l'intestazione privacy: ID verrà inviata.</span><span class="sxs-lookup"><span data-stu-id="1965c-195">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="1965c-196">Il valore predefinito è **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="1965c-196">The default value is **False** ($False).</span></span>|<span data-ttu-id="1965c-197">False</span><span class="sxs-lookup"><span data-stu-id="1965c-197">False</span></span>|<span data-ttu-id="1965c-198">True</span><span class="sxs-lookup"><span data-stu-id="1965c-198">True</span></span><br/><span data-ttu-id="1965c-199">False</span><span class="sxs-lookup"><span data-stu-id="1965c-199">False</span></span>|<span data-ttu-id="1965c-200">Boolean</span><span class="sxs-lookup"><span data-stu-id="1965c-200">Boolean</span></span>|
|<span data-ttu-id="1965c-201">No</span><span class="sxs-lookup"><span data-stu-id="1965c-201">No</span></span>|<span data-ttu-id="1965c-202">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="1965c-202">SendSIPOptions</span></span> |<span data-ttu-id="1965c-203">Definisce se un SBC riceverà o non invierà le opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="1965c-203">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="1965c-204">Se disabilitato, SBC verrà escluso dal sistema di monitoraggio e avviso.</span><span class="sxs-lookup"><span data-stu-id="1965c-204">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="1965c-205">Ti consigliamo vivamente di abilitare le opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="1965c-205">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="1965c-206">Il valore predefinito è **true**.</span><span class="sxs-lookup"><span data-stu-id="1965c-206">Default value is **True**.</span></span> |<span data-ttu-id="1965c-207">True</span><span class="sxs-lookup"><span data-stu-id="1965c-207">True</span></span>|<span data-ttu-id="1965c-208">True</span><span class="sxs-lookup"><span data-stu-id="1965c-208">True</span></span><br/><span data-ttu-id="1965c-209">False</span><span class="sxs-lookup"><span data-stu-id="1965c-209">False</span></span>|<span data-ttu-id="1965c-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="1965c-210">Boolean</span></span>|
|<span data-ttu-id="1965c-211">No</span><span class="sxs-lookup"><span data-stu-id="1965c-211">No</span></span>|<span data-ttu-id="1965c-212">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="1965c-212">MaxConcurrentSessions</span></span> |<span data-ttu-id="1965c-213">Usato da Alerting System.</span><span class="sxs-lookup"><span data-stu-id="1965c-213">Used by alerting system.</span></span> <span data-ttu-id="1965c-214">Quando viene impostato un valore qualsiasi, il sistema di avviso genera un avviso per l'amministratore del tenant quando il numero di sessione simultanea è pari a 90% o superiore a questo valore.</span><span class="sxs-lookup"><span data-stu-id="1965c-214">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="1965c-215">Se il parametro non è impostato, gli avvisi non vengono generati.</span><span class="sxs-lookup"><span data-stu-id="1965c-215">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="1965c-216">Tuttavia, il sistema di monitoraggio riporterà il numero di sessioni simultanee ogni 24 ore.</span><span class="sxs-lookup"><span data-stu-id="1965c-216">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="1965c-217">Null</span><span class="sxs-lookup"><span data-stu-id="1965c-217">Null</span></span>|<span data-ttu-id="1965c-218">Null</span><span class="sxs-lookup"><span data-stu-id="1965c-218">Null</span></span><br/><span data-ttu-id="1965c-219">1-100.000</span><span class="sxs-lookup"><span data-stu-id="1965c-219">1 to 100,000</span></span> ||
|<span data-ttu-id="1965c-220">No</span><span class="sxs-lookup"><span data-stu-id="1965c-220">No</span></span>|<span data-ttu-id="1965c-221">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="1965c-221">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="1965c-222">Consente di selezionare manualmente il percorso per elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="1965c-222">Allows selecting path for media manually.</span></span> <span data-ttu-id="1965c-223">Il routing diretto assegna un Data Center per il percorso multimediale basato sull'IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-223">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="1965c-224">Selezionare sempre più vicino al Data Center SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-224">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="1965c-225">Tuttavia, in alcuni casi un IP pubblico da ad esempio un intervallo degli Stati Uniti può essere assegnato a un SBC situato in Europa.</span><span class="sxs-lookup"><span data-stu-id="1965c-225">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="1965c-226">In questo caso useremo un percorso di supporto non ottimale.</span><span class="sxs-lookup"><span data-stu-id="1965c-226">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="1965c-227">Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="1965c-227">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="1965c-228">È consigliabile impostare questo parametro solo se i registri delle chiamate indicano chiaramente che l'assegnazione automatica del Data Center per il percorso multimediale non assegna il più vicino al Data Center SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-228">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="1965c-229">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1965c-229">None</span></span>|<span data-ttu-id="1965c-230">Codici paese in formato ISO</span><span class="sxs-lookup"><span data-stu-id="1965c-230">Country codes in ISO format</span></span>||
|<span data-ttu-id="1965c-231">No</span><span class="sxs-lookup"><span data-stu-id="1965c-231">No</span></span>|<span data-ttu-id="1965c-232">Abilitata</span><span class="sxs-lookup"><span data-stu-id="1965c-232">Enabled</span></span>|<span data-ttu-id="1965c-233">Usato per abilitare questo SBC per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="1965c-233">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="1965c-234">Può essere usato per rimuovere temporaneamente il SBC, mentre viene aggiornato o durante la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="1965c-234">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="1965c-235">False</span><span class="sxs-lookup"><span data-stu-id="1965c-235">False</span></span>|<span data-ttu-id="1965c-236">True</span><span class="sxs-lookup"><span data-stu-id="1965c-236">True</span></span><br/><span data-ttu-id="1965c-237">False</span><span class="sxs-lookup"><span data-stu-id="1965c-237">False</span></span>|<span data-ttu-id="1965c-238">Boolean</span><span class="sxs-lookup"><span data-stu-id="1965c-238">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="1965c-239">Verificare l'associazione di SBC</span><span class="sxs-lookup"><span data-stu-id="1965c-239">Verify the SBC pairing</span></span> 

<span data-ttu-id="1965c-240">Verificare la connessione:</span><span class="sxs-lookup"><span data-stu-id="1965c-240">Verify the connection:</span></span> 
- <span data-ttu-id="1965c-241">Verificare se il controllo SBC è nell'elenco di SBCs associati.</span><span class="sxs-lookup"><span data-stu-id="1965c-241">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="1965c-242">Convalidare le opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="1965c-242">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="1965c-243">Verificare se SBC è nell'elenco di SBCs associati</span><span class="sxs-lookup"><span data-stu-id="1965c-243">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="1965c-244">Dopo avere associato il controllo SBC, verificare che l'SBC sia presente nell'elenco di SBCs associati eseguendo il comando seguente in una sessione remota di PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="1965c-244">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="1965c-245">Il gateway associato deve essere visualizzato nell'elenco come illustrato nell'esempio seguente e verificare che il parametro *Enabled* visualizzi il valore **true**.</span><span class="sxs-lookup"><span data-stu-id="1965c-245">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="1965c-246">Immettere</span><span class="sxs-lookup"><span data-stu-id="1965c-246">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="1965c-247">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="1965c-247">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="1965c-248">Convalidare il flusso delle opzioni SIP</span><span class="sxs-lookup"><span data-stu-id="1965c-248">Validate SIP Options flow</span></span> 

<span data-ttu-id="1965c-249">Per convalidare l'associazione con le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva le risposte OK di 200 ai messaggi delle opzioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="1965c-249">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="1965c-250">Quando il routing diretto Visualizza le opzioni in arrivo, inizierà a inviare messaggi di opzioni SIP in uscita all'FQDN SBC configurato nel campo dell'intestazione del contatto nel messaggio delle opzioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="1965c-250">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="1965c-251">Per convalidare l'associazione con le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che il SBC invii una risposta ai messaggi delle opzioni provenienti da routing diretto e che il codice di risposta inviato sia 200 OK.</span><span class="sxs-lookup"><span data-stu-id="1965c-251">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="1965c-252">Abilitare gli utenti per il servizio di routing diretto</span><span class="sxs-lookup"><span data-stu-id="1965c-252">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="1965c-253">Quando si è pronti per abilitare gli utenti per il servizio di routing diretto, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1965c-253">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="1965c-254">Creare un utente in Office 365 e assegnare una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="1965c-254">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="1965c-255">Verificare che l'utente sia ospitato in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1965c-255">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="1965c-256">Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="1965c-256">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="1965c-257">Configurare il routing vocale.</span><span class="sxs-lookup"><span data-stu-id="1965c-257">Configure voice routing.</span></span> <span data-ttu-id="1965c-258">La route viene convalidata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1965c-258">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="1965c-259">Creare un utente in Office 365 e assegnare la licenza</span><span class="sxs-lookup"><span data-stu-id="1965c-259">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="1965c-260">Esistono due opzioni per la creazione di un nuovo utente in Office 365.</span><span class="sxs-lookup"><span data-stu-id="1965c-260">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="1965c-261">Tuttavia, è consigliabile che l'organizzazione selezioni e usi un'opzione per evitare problemi di routing:</span><span class="sxs-lookup"><span data-stu-id="1965c-261">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="1965c-262">Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud.</span><span class="sxs-lookup"><span data-stu-id="1965c-262">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="1965c-263">Vedere [integrare le directory locali con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="1965c-263">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="1965c-264">Creare l'utente direttamente nel portale di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1965c-264">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="1965c-265">Vedere [aggiungere utenti singolarmente o in blocco a Office 365-Guida per gli amministratori](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="1965c-265">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="1965c-266">Se la distribuzione di Skype for business online è condivisa con Skype for business 2015 o Lync 2010/2013 in locale, l'unica opzione supportata consiste nel creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1).</span><span class="sxs-lookup"><span data-stu-id="1965c-266">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="1965c-267">Licenze obbligatorie:</span><span class="sxs-lookup"><span data-stu-id="1965c-267">Required licenses:</span></span> 

- <span data-ttu-id="1965c-268">Office 365 Enterprise E3 (inclusi SfB Plan2, Exchange Plan2 e teams) + sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="1965c-268">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="1965c-269">Office 365 Enterprise E5 (inclusi SfB Plan2, Exchange Plan2, teams e Phone System)</span><span class="sxs-lookup"><span data-stu-id="1965c-269">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="1965c-270">Licenze facoltative:</span><span class="sxs-lookup"><span data-stu-id="1965c-270">Optional licenses:</span></span> 

- <span data-ttu-id="1965c-271">Piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="1965c-271">Calling Plan</span></span> 
- <span data-ttu-id="1965c-272">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="1965c-272">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="1965c-273">Verificare che l'utente sia ospitato in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="1965c-273">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="1965c-274">Il routing diretto richiede che l'utente sia ospitato in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1965c-274">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="1965c-275">Puoi controllare questo aspetto esaminando il parametro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="1965c-275">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="1965c-276">Deve avere un valore nel dominio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1965c-276">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="1965c-277">Connettersi a PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="1965c-277">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="1965c-278">Emettere il comando:</span><span class="sxs-lookup"><span data-stu-id="1965c-278">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="1965c-279">Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="1965c-279">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="1965c-280">Dopo aver creato l'utente e assegnato una licenza, il passaggio successivo consiste nel configurare il proprio numero di telefono e la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="1965c-280">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="1965c-281">Questa operazione può essere eseguita in un solo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1965c-281">This can be done in one step.</span></span> 

<span data-ttu-id="1965c-282">Per aggiungere il numero di telefono e abilitare per la segreteria telefonica:</span><span class="sxs-lookup"><span data-stu-id="1965c-282">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="1965c-283">Connettersi a una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1965c-283">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="1965c-284">Immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="1965c-284">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="1965c-285">Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer low", è necessario immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1965c-285">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="1965c-286">Il numero di telefono usato deve essere configurato come numero di telefono E. 164 completo con prefisso nazionale.</span><span class="sxs-lookup"><span data-stu-id="1965c-286">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="1965c-287">Se il numero di telefono dell'utente viene gestito in locale, USA Skype for Business Management Shell locale o pannello di controllo per configurare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1965c-287">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="1965c-288">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="1965c-288">Configure Voice Routing</span></span> 

<span data-ttu-id="1965c-289">Microsoft Phone System include un meccanismo di routing che consente di inviare una chiamata a un SBC specifico in base a:</span><span class="sxs-lookup"><span data-stu-id="1965c-289">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="1965c-290">Modello di numero definito</span><span class="sxs-lookup"><span data-stu-id="1965c-290">Called number pattern</span></span> 
- <span data-ttu-id="1965c-291">Nome modello numero + utente specifico che effettua la chiamata</span><span class="sxs-lookup"><span data-stu-id="1965c-291">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="1965c-292">SBCs può essere designato come attivo e backup.</span><span class="sxs-lookup"><span data-stu-id="1965c-292">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="1965c-293">Questo significa che quando l'SBC configurato come attivo per il modello di numero o il modello numerico + un utente specifico non è disponibile, le chiamate verranno instradate a un SBC di backup.</span><span class="sxs-lookup"><span data-stu-id="1965c-293">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="1965c-294">Il routing delle chiamate è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1965c-294">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="1965c-295">Criteri di routing vocale: contenitore per gli usi PSTN; può essere assegnato a un utente o a più utenti</span><span class="sxs-lookup"><span data-stu-id="1965c-295">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="1965c-296">Usi PSTN: contenitore per le route vocali ed usi PSTN; possono essere condivisi in criteri di routing vocale diversi</span><span class="sxs-lookup"><span data-stu-id="1965c-296">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="1965c-297">Route vocali: modello numerico e set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde al modello</span><span class="sxs-lookup"><span data-stu-id="1965c-297">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="1965c-298">Il gateway PSTN online-puntatore a un SBC, memorizza anche la configurazione applicata quando la chiamata viene inserita tramite SBC, ad esempio forward P-Asserted-Identity (PAI) o codec preferiti; può essere aggiunto alle route vocali</span><span class="sxs-lookup"><span data-stu-id="1965c-298">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="1965c-299">Creazione di un criterio di routing vocale con un solo utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="1965c-299">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="1965c-300">Il diagramma seguente mostra due esempi di criteri di routing vocale nel flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1965c-300">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="1965c-301">**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="1965c-301">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="1965c-302">Se non sono disponibili né sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="1965c-302">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="1965c-303">**Chiamata flusso 2 (a destra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene prima indirizzata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="1965c-303">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="1965c-304">Se non è disponibile alcun SBC, verrà provata la route con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="1965c-304">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="1965c-305">Se nessuna delle SBCs è disponibile, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="1965c-305">If none of the SBCs are available, the call is dropped.</span></span> 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="1965c-307">In entrambi gli esempi, mentre la route vocale è assegnata alle priorità, il SBCs nelle route viene provato in ordine casuale.</span><span class="sxs-lookup"><span data-stu-id="1965c-307">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1965c-308">A meno che l'utente non disponga anche di una licenza per il piano di chiamata Microsoft, le chiamate a qualsiasi numero eccetto i numeri corrispondenti ai pattern + 1 425 XXX XX XX o + 1 206 XXX XX XX nella configurazione di esempio vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="1965c-308">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="1965c-309">Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1965c-309">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="1965c-310">Il piano di chiamate Microsoft si applica automaticamente come ultima route a tutti gli utenti con la licenza per il piano di chiamata Microsoft e non richiede ulteriori configurazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1965c-310">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="1965c-311">Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri americani e canadesi (chiamate che vanno alla sequenza numerica chiamata + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="1965c-311">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra i criteri di routing vocale con una terza Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="1965c-313">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="1965c-313">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="1965c-314">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, passare tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1965c-314">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="1965c-315">Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="1965c-315">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1965c-316">Il valore di priorità per la route "altro + 1" non ha importanza in questo caso, in quanto esiste una sola route che corrisponde al modello + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="1965c-316">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="1965c-317">Se un utente effettua una chiamata a + 1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="1965c-317">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="1965c-318">La tabella seguente riepiloga la configurazione usando tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="1965c-318">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="1965c-319">In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="1965c-319">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="1965c-320">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="1965c-320">**PSTN usage**</span></span>|<span data-ttu-id="1965c-321">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="1965c-321">**Voice route**</span></span>|<span data-ttu-id="1965c-322">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="1965c-322">**Number pattern**</span></span>|<span data-ttu-id="1965c-323">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1965c-323">**Priority**</span></span>|<span data-ttu-id="1965c-324">**SBC**</span><span class="sxs-lookup"><span data-stu-id="1965c-324">**SBC**</span></span>|<span data-ttu-id="1965c-325">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1965c-325">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1965c-326">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-326">US only</span></span>|<span data-ttu-id="1965c-327">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="1965c-327">"Redmond 1"</span></span>|<span data-ttu-id="1965c-328">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-328">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="1965c-329">1</span><span class="sxs-lookup"><span data-stu-id="1965c-329">1</span></span>|<span data-ttu-id="1965c-330">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-330">sbc1.contoso.biz</span></span><br/><span data-ttu-id="1965c-331">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-331">sbc2.contoso.biz</span></span>|<span data-ttu-id="1965c-332">Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="1965c-332">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="1965c-333">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-333">US only</span></span>|<span data-ttu-id="1965c-334">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="1965c-334">"Redmond 2"</span></span>|<span data-ttu-id="1965c-335">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-335">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="1965c-336">2</span><span class="sxs-lookup"><span data-stu-id="1965c-336">2</span></span>|<span data-ttu-id="1965c-337">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-337">sbc3.contoso.biz</span></span><br/><span data-ttu-id="1965c-338">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-338">sbc4.contoso.biz</span></span>|<span data-ttu-id="1965c-339">Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="1965c-339">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="1965c-340">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-340">US only</span></span>|<span data-ttu-id="1965c-341">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="1965c-341">"Other +1"</span></span>|<span data-ttu-id="1965c-342">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-342">^\\+1(\d{10})$</span></span>|<span data-ttu-id="1965c-343">3</span><span class="sxs-lookup"><span data-stu-id="1965c-343">3</span></span>|<span data-ttu-id="1965c-344">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-344">sbc5.contoso.biz</span></span><br/><span data-ttu-id="1965c-345">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-345">sbc6.contoso.biz</span></span>|<span data-ttu-id="1965c-346">Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="1965c-346">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="1965c-347">Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo PSTN è associato ai criteri di routing vocale "solo Stati Uniti".</span><span class="sxs-lookup"><span data-stu-id="1965c-347">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="1965c-348">In questo esempio, il criterio di routing vocale viene assegnato all'utente Spencer low.</span><span class="sxs-lookup"><span data-stu-id="1965c-348">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="1965c-349">Esempi di route di chiamata</span><span class="sxs-lookup"><span data-stu-id="1965c-349">Examples of call routes</span></span>

<span data-ttu-id="1965c-350">Nell'esempio seguente viene illustrato come configurare le route, gli utilizzi PSTN e i criteri di routing e assegnare i criteri all'utente.</span><span class="sxs-lookup"><span data-stu-id="1965c-350">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="1965c-351">**Passaggio 1:** Creare l'utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="1965c-351">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="1965c-352">In una sessione remota di PowerShell per Skype for business digitare:</span><span class="sxs-lookup"><span data-stu-id="1965c-352">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="1965c-353">Verificare che l'utilizzo sia stato creato immettendo:</span><span class="sxs-lookup"><span data-stu-id="1965c-353">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="1965c-354">Che restituisce un elenco di nomi che possono essere troncati:</span><span class="sxs-lookup"><span data-stu-id="1965c-354">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="1965c-355">Nell'esempio seguente puoi vedere il risultato del comando `(Get-CSOnlinePSTNUsage).usage` Esegui PowerShell per visualizzare i nomi completi (non troncati).</span><span class="sxs-lookup"><span data-stu-id="1965c-355">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="1965c-356">**Passaggio 2:** In una sessione di PowerShell in Skype for business online, creare tre Route: Redmond 1, Redmond 2 e altre + 1, come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="1965c-356">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="1965c-357">Per creare la route "Redmond 1", immettere:</span><span class="sxs-lookup"><span data-stu-id="1965c-357">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="1965c-358">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="1965c-358">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
<span data-ttu-id="1965c-359">Per creare la route Redmond 2, immettere:</span><span class="sxs-lookup"><span data-stu-id="1965c-359">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="1965c-360">Per creare l'altra route + 1, immettere:</span><span class="sxs-lookup"><span data-stu-id="1965c-360">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="1965c-361">Verificare che l'espressione regolare nell'attributo NumberPattern sia valida.</span><span class="sxs-lookup"><span data-stu-id="1965c-361">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="1965c-362">Puoi testarlo usando questo sito Web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="1965c-362">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="1965c-363">In alcuni casi è necessario instradare tutte le chiamate allo stesso SBC; usare-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="1965c-363">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="1965c-364">Instradare tutte le chiamate allo stesso SBC</span><span class="sxs-lookup"><span data-stu-id="1965c-364">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="1965c-365">Verificare di aver configurato correttamente la route eseguendo il comando di `Get-CSOnlineVoiceRoute` PowerShell usando le opzioni come illustrato:</span><span class="sxs-lookup"><span data-stu-id="1965c-365">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="1965c-366">Che dovrebbe restituire:</span><span class="sxs-lookup"><span data-stu-id="1965c-366">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="1965c-367">Nell'esempio, la route "altro + 1" è stata assegnata automaticamente la priorità 4.</span><span class="sxs-lookup"><span data-stu-id="1965c-367">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="1965c-368">**Passaggio 3:** Creare un criterio di routing vocale "solo Stati Uniti" e aggiungere al criterio l'utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="1965c-368">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="1965c-369">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="1965c-369">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="1965c-370">Il risultato è illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="1965c-370">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="1965c-371">**Passaggio 4:** Concedere a user Spencer un criterio di routing vocale basso usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1965c-371">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="1965c-372">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="1965c-372">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="1965c-373">Convalidare l'assegnazione dei criteri immettendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="1965c-373">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="1965c-374">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="1965c-374">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="1965c-375">Creazione di un criterio di routing vocale con diversi usi PSTN</span><span class="sxs-lookup"><span data-stu-id="1965c-375">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="1965c-376">Il criterio di routing vocale creato in precedenza consente solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che l'utente non venga assegnato anche alla licenza per il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1965c-376">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="1965c-377">Nell'esempio seguente puoi creare il criterio di routing vocale "nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="1965c-377">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="1965c-378">Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creati nell'esempio precedente, nonché il nuovo utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="1965c-378">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="1965c-379">Questo instrada tutte le altre chiamate a SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="1965c-379">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="1965c-380">Gli esempi illustrati assegnano il criterio US only all'utente "Spencer low" e nessuna restrizione per l'utente "John Woods".</span><span class="sxs-lookup"><span data-stu-id="1965c-380">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="1965c-381">Spencer Low: le chiamate sono consentite solo ai numeri US e canadesi.</span><span class="sxs-lookup"><span data-stu-id="1965c-381">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="1965c-382">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-382">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="1965c-383">I numeri non Stati Uniti non verranno instradati, a meno che non venga assegnata all'utente la licenza per il piano chiamante.</span><span class="sxs-lookup"><span data-stu-id="1965c-383">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="1965c-384">John Woods-chiamate consentite a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="1965c-384">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="1965c-385">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1965c-385">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="1965c-386">I numeri non US verranno instradati tramite sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="1965c-386">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente Spencer low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="1965c-388">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="1965c-388">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="1965c-389">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, passare tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1965c-389">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="1965c-390">Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="1965c-390">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="1965c-392">Nella tabella seguente vengono riepilogati i criteri di routing "nessuna restrizione" denominazioni di utilizzo e route vocali.</span><span class="sxs-lookup"><span data-stu-id="1965c-392">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="1965c-393">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="1965c-393">**PSTN usage**</span></span>|<span data-ttu-id="1965c-394">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="1965c-394">**Voice route**</span></span>|<span data-ttu-id="1965c-395">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="1965c-395">**Number pattern**</span></span>|<span data-ttu-id="1965c-396">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1965c-396">**Priority**</span></span>|<span data-ttu-id="1965c-397">**SBC**</span><span class="sxs-lookup"><span data-stu-id="1965c-397">**SBC**</span></span>|<span data-ttu-id="1965c-398">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1965c-398">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1965c-399">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-399">US Only</span></span>|<span data-ttu-id="1965c-400">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="1965c-400">"Redmond 1"</span></span>|<span data-ttu-id="1965c-401">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-401">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="1965c-402">1</span><span class="sxs-lookup"><span data-stu-id="1965c-402">1</span></span>|<span data-ttu-id="1965c-403">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-403">sbc1.contoso.biz</span></span><br/><span data-ttu-id="1965c-404">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-404">sbc2.contoso.biz</span></span>|<span data-ttu-id="1965c-405">Route attiva per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="1965c-405">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="1965c-406">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-406">US Only</span></span>|<span data-ttu-id="1965c-407">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="1965c-407">"Redmond 2"</span></span>|<span data-ttu-id="1965c-408">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-408">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="1965c-409">2</span><span class="sxs-lookup"><span data-stu-id="1965c-409">2</span></span>|<span data-ttu-id="1965c-410">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-410">sbc3.contoso.biz</span></span><br/><span data-ttu-id="1965c-411">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-411">sbc4.contoso.biz</span></span>|<span data-ttu-id="1965c-412">Percorso di backup per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="1965c-412">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="1965c-413">Solo Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1965c-413">US Only</span></span>|<span data-ttu-id="1965c-414">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="1965c-414">"Other +1"</span></span>|<span data-ttu-id="1965c-415">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="1965c-415">^\\+1(\d{10})$</span></span>|<span data-ttu-id="1965c-416">3</span><span class="sxs-lookup"><span data-stu-id="1965c-416">3</span></span>|<span data-ttu-id="1965c-417">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-417">sbc5.contoso.biz</span></span><br/><span data-ttu-id="1965c-418">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-418">sbc6>.contoso.biz</span></span>|<span data-ttu-id="1965c-419">Route per i numeri dei chiamanti + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="1965c-419">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="1965c-420">Internazionale</span><span class="sxs-lookup"><span data-stu-id="1965c-420">International</span></span>|<span data-ttu-id="1965c-421">Internazionale</span><span class="sxs-lookup"><span data-stu-id="1965c-421">International</span></span>|<span data-ttu-id="1965c-422">\d +</span><span class="sxs-lookup"><span data-stu-id="1965c-422">\d+</span></span>|<span data-ttu-id="1965c-423">4</span><span class="sxs-lookup"><span data-stu-id="1965c-423">4</span></span>|<span data-ttu-id="1965c-424">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-424">sbc2.contoso.biz</span></span><br/><span data-ttu-id="1965c-425">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="1965c-425">sbc5.contoso.biz</span></span>|<span data-ttu-id="1965c-426">Route per qualsiasi modello di numero</span><span class="sxs-lookup"><span data-stu-id="1965c-426">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="1965c-427">L'ordine degli usi PSTN nei criteri di routing vocale è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="1965c-427">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="1965c-428">Gli usi vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati.</span><span class="sxs-lookup"><span data-stu-id="1965c-428">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="1965c-429">L'utilizzo PSTN "internazionale" deve essere posizionato dopo l'uso PSTN "solo USA".</span><span class="sxs-lookup"><span data-stu-id="1965c-429">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="1965c-430">Per modificare l'ordine degli usi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="1965c-430">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="1965c-431">Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" prima e "internazionale" in secondo luogo, eseguire l'ordine inverso:</span><span class="sxs-lookup"><span data-stu-id="1965c-431">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="1965c-432">La priorità per le route vocali "altro + 1" e "internazionale" viene assegnata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1965c-432">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="1965c-433">Gli utenti non hanno importanza se hanno priorità più basse rispetto a "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="1965c-433">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="1965c-434">Esempio di criteri di routing vocale per l'utente John Woods</span><span class="sxs-lookup"><span data-stu-id="1965c-434">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="1965c-435">La procedura per creare l'utilizzo PSTN "internazionale", la route vocale "internazionale", "criteri di routing vocale" senza restrizioni "e quindi l'assegnazione all'utente" John Woods "è la seguente.</span><span class="sxs-lookup"><span data-stu-id="1965c-435">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="1965c-436">Prima di tutto, crea l'utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="1965c-436">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="1965c-437">In una sessione remota di PowerShell in Skype for business online, immettere:</span><span class="sxs-lookup"><span data-stu-id="1965c-437">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="1965c-438">Crea quindi la nuova route vocale "internazionale".</span><span class="sxs-lookup"><span data-stu-id="1965c-438">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="1965c-439">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="1965c-439">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. <span data-ttu-id="1965c-440">Creare quindi un criterio di routing vocale "nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="1965c-440">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="1965c-441">L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.</span><span class="sxs-lookup"><span data-stu-id="1965c-441">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="1965c-442">Che restituisce</span><span class="sxs-lookup"><span data-stu-id="1965c-442">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="1965c-443">Assegnare il criterio di routing vocale all'utente "John Woods" usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="1965c-443">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="1965c-444">Verificare quindi l'assegnazione usando il comando:</span><span class="sxs-lookup"><span data-stu-id="1965c-444">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="1965c-445">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="1965c-445">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="1965c-446">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.</span><span class="sxs-lookup"><span data-stu-id="1965c-446">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="1965c-447">Impostare Microsoft teams come client chiamante preferito per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1965c-447">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="1965c-448">Il routing diretto instrada solo le chiamate da e verso gli utenti se usano il client teams.</span><span class="sxs-lookup"><span data-stu-id="1965c-448">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="1965c-449">Se l'organizzazione usa solo teams, è consigliabile impostare la modalità "solo Teams" in criteri di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1965c-449">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="1965c-450">Se l'organizzazione usa Skype for Business Server o Skype for business online, vedere l'articolo seguente per altre informazioni e selezionare l'opzione appropriata: [comprendere la coesistenza e l'aggiornamento del viaggio per Skype for business e teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="1965c-450">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="1965c-451">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1965c-451">See also</span></span>

[<span data-ttu-id="1965c-452">Pianificare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="1965c-452">Plan Direct Routing</span></span>](direct-routing-plan.md)
