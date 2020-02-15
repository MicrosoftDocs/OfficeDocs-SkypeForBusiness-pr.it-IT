---
title: 'Lync Server 2013: pianificazione per le distribuzioni ibride'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0efc4a6a9e9f195705801969b8459c17855388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="9a56e-102">Pianificazione delle distribuzioni ibride di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a56e-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a56e-103">_**Ultimo argomento modificato:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="9a56e-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="9a56e-104">È consigliabile prendere in considerazione i requisiti seguenti per gli utenti e l'infrastruttura di rete durante la pianificazione di una distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="9a56e-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="9a56e-105">Requisiti dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="9a56e-105">Infrastructure Requirements</span></span>

<span data-ttu-id="9a56e-106">Per implementare e distribuire una distribuzione ibrida, è necessario che nel proprio ambiente siano configurati i seguenti elementi.</span><span class="sxs-lookup"><span data-stu-id="9a56e-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="9a56e-107">Un tenant di Microsoft Office 365 con Skype for business online abilitato.</span><span class="sxs-lookup"><span data-stu-id="9a56e-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="9a56e-108">Si noti che è possibile utilizzare solo un singolo tenant per una configurazione ibrida con la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="9a56e-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="9a56e-109">Una singola distribuzione locale (Infrastructure) di Skype for Business Server o Lync Server distribuito in una topologia supportata.</span><span class="sxs-lookup"><span data-stu-id="9a56e-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="9a56e-110">Vedere Requisiti per la topologia.</span><span class="sxs-lookup"><span data-stu-id="9a56e-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="9a56e-111">Per informazioni sulla configurazione della distribuzione di Lync Server 2013 o Lync Server 2010 per l'ambiente ibrido, vedere [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="9a56e-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="9a56e-112">Strumenti di amministrazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9a56e-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="9a56e-113">Se si utilizza Lync Server 2013 o Lync Server 2010, è possibile utilizzare gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a56e-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="9a56e-114">Per supportare l'accesso Single Sign-on con Office 365 in modo che gli utenti possano utilizzare le stesse credenziali di accesso per l'accesso a Office come in locale, è possibile utilizzare le funzionalità di sincronizzazione delle password di Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="9a56e-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="9a56e-115">È inoltre possibile utilizzare Active Directory Federation Services (AD FS) per l'accesso Single Sign-on con Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a56e-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="9a56e-116">Per ulteriori informazioni, vedere [Integrazione delle identità locali con Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="9a56e-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="9a56e-117">Una singola soluzione di sincronizzazione della directory per sincronizzare gli oggetti di Active Directory locali e online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="9a56e-118">Per informazioni dettagliate sulla sincronizzazione della directory, vedere [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="9a56e-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="9a56e-119">Supporto per client Lync</span><span class="sxs-lookup"><span data-stu-id="9a56e-119">Lync Client Support</span></span>

<span data-ttu-id="9a56e-120">Esistono alcune differenze nelle funzionalità supportate nei client Lync, nonché le funzionalità disponibili negli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="9a56e-121">Prima di decidere dove si desiderano gli utenti privati nell'organizzazione, è possibile visualizzare il supporto client per le diverse configurazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a56e-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="9a56e-122">I client seguenti sono supportati con Skype for business online in una distribuzione ibrida di Lync:</span><span class="sxs-lookup"><span data-stu-id="9a56e-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="9a56e-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9a56e-123">Lync 2010</span></span>

  - <span data-ttu-id="9a56e-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9a56e-124">Lync 2013</span></span>

  - <span data-ttu-id="9a56e-125">App Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="9a56e-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="9a56e-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9a56e-126">Lync Web App</span></span>

  - <span data-ttu-id="9a56e-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="9a56e-127">Lync Mobile</span></span>

  - <span data-ttu-id="9a56e-128">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="9a56e-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="9a56e-129">Sistema chat room Lync</span><span class="sxs-lookup"><span data-stu-id="9a56e-129">Lync Room System</span></span>

  - <span data-ttu-id="9a56e-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="9a56e-130">Lync Basic 2013</span></span>

<span data-ttu-id="9a56e-131">Per informazioni dettagliate sul supporto dei client, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9a56e-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="9a56e-132">Client per Lync Online</span><span class="sxs-lookup"><span data-stu-id="9a56e-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="9a56e-133">Tabelle di confronto dei client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a56e-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="9a56e-134">Tabelle di confronto dei client per dispositivi mobili per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a56e-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="9a56e-135">Requisiti della topologia</span><span class="sxs-lookup"><span data-stu-id="9a56e-135">Topology Requirements</span></span>

<span data-ttu-id="9a56e-136">Per configurare la distribuzione ibrida con Skype for business online, è necessario disporre di una delle topologie supportate seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a56e-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="9a56e-137">Una distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9a56e-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="9a56e-138">Una distribuzione di Lync Server 2013 con tutti i server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a56e-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="9a56e-139">Una distribuzione di Lync Server 2010 con tutti i server che eseguono Lync Server 2010 con gli aggiornamenti cumulativi più recenti.</span><span class="sxs-lookup"><span data-stu-id="9a56e-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="9a56e-140">È necessario che il server perimetrale federativo e il server dell'hop successivo del server perimetrale federativo esegua l'esecuzione di Lync Server 2010 con gli aggiornamenti cumulativi più recenti.</span><span class="sxs-lookup"><span data-stu-id="9a56e-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="9a56e-141">Gli strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o una workstation di gestione.</span><span class="sxs-lookup"><span data-stu-id="9a56e-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="9a56e-142">Distribuzione di Lync Server 2013 e Skype for business 2015 server misto con i ruoli del server seguenti in almeno un sito che esegue Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="9a56e-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="9a56e-143">Almeno un pool Enterprise o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="9a56e-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="9a56e-144">Il pool di server Director associato alla federazione SIP, se esistente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="9a56e-145">Pool di server perimetrali associati alla federazione SIP</span><span class="sxs-lookup"><span data-stu-id="9a56e-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="9a56e-146">Una distribuzione mista di Lync Server 2010 e Skype for Business Server 2015 con i ruoli dei server seguenti in almeno un sito che esegue Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="9a56e-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="9a56e-147">Almeno un pool Enterprise o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="9a56e-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="9a56e-148">Il pool di server Director associato alla federazione SIP, se esistente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="9a56e-149">Pool di server perimetrali associati alla federazione SIP per il sito</span><span class="sxs-lookup"><span data-stu-id="9a56e-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="9a56e-150">Distribuzione di Lync Server 2010 e Lync Server 2013 mista con i ruoli del server seguenti in almeno un sito in cui è in esecuzione Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9a56e-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="9a56e-151">Almeno un pool Enterprise o un server Standard Edition nel sito</span><span class="sxs-lookup"><span data-stu-id="9a56e-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="9a56e-152">Il pool di server Director associato alla federazione SIP, se esiste nel sito</span><span class="sxs-lookup"><span data-stu-id="9a56e-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="9a56e-153">Pool di server perimetrali associati alla federazione SIP per il sito</span><span class="sxs-lookup"><span data-stu-id="9a56e-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a56e-154">Tutte le attività di gestione degli utenti, inclusi gli spostamenti degli utenti tra locali e UNRESOLVED_TOKEN_VAL (skypeforbusiness) online, devono essere eseguite utilizzando la versione più recente installata degli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="9a56e-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="9a56e-155">Gli strumenti di amministrazione devono essere installati in un server separato che dispone dell'accesso connesso alla distribuzione locale esistente e a Internet.</span><span class="sxs-lookup"><span data-stu-id="9a56e-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="9a56e-156">Il cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> per spostare gli utenti dalla distribuzione locale a UNRESOLVED_TOKEN_VAL (skype16_online) deve essere eseguito dagli strumenti di amministrazione connessi alla distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="9a56e-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="9a56e-157">Per ulteriori informazioni sulle topologie supportate, vedere [Supported topologies in Lync server 2013](lync-server-2013-supported-topologies.md)e [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="9a56e-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="9a56e-158">Per informazioni sulla risoluzione dei problemi relativi alle distribuzioni ibride e sulla connessione di PowerShell a Lync Online, vedere [Lync Online: Lync PowerShell e la risoluzione dei problemi ibridi](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="9a56e-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="9a56e-159">Requisiti per gli elenchi di Federazione consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a56e-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="9a56e-160">L'elenco dei domini consentiti include i domini che dispongono di un nome di dominio completo (FQDN) del partner perimetrale configurato.</span><span class="sxs-lookup"><span data-stu-id="9a56e-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="9a56e-161">A volte sono indicati come *server partner consentiti* o *partner di Federazione diretti*.</span><span class="sxs-lookup"><span data-stu-id="9a56e-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="9a56e-162">È necessario avere familiarità con la differenza tra la Federazione aperta e la federazione chiusa, denominate rispettivamente come *Individuazione partner* e *elenco di domini consentiti partner*, nelle distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="9a56e-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="9a56e-163">Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a56e-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="9a56e-164">La corrispondenza del dominio deve essere configurata per la distribuzione locale e per il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a56e-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="9a56e-165">Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la Federazione aperta per il tenant online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="9a56e-166">Se l'individuazione dei partner non è abilitata, la federazione chiusa deve essere configurata per il tenant online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="9a56e-167">L'elenco dei domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco dei domini bloccati per il tenant online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="9a56e-168">L'elenco dei domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco dei domini consentiti per il tenant online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="9a56e-169">La Federazione deve essere abilitata per le comunicazioni esterne per il tenant online, configurata utilizzando il pannello di controllo di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="9a56e-170">Impostazioni DNS</span><span class="sxs-lookup"><span data-stu-id="9a56e-170">DNS Settings</span></span>

<span data-ttu-id="9a56e-171">Quando si creano record DNS per le distribuzioni ibride, tutti i record DNS esterni di Lync devono puntare all'infrastruttura locale.</span><span class="sxs-lookup"><span data-stu-id="9a56e-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="9a56e-172">Per informazioni dettagliate sui record DNS necessari, fare riferimento ai [requisiti DNS (Domain Name System) per Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a56e-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="9a56e-173">Inoltre, è necessario assicurarsi che la risoluzione DNS descritta nella tabella seguente sia compatibile con la distribuzione locale:</span><span class="sxs-lookup"><span data-stu-id="9a56e-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-174">Record DNS</span><span class="sxs-lookup"><span data-stu-id="9a56e-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="9a56e-175">Risolvibile da</span><span class="sxs-lookup"><span data-stu-id="9a56e-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="9a56e-176">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="9a56e-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a56e-177">Record SRV DNS per _sipfederationtls. _tcp. &lt;SipDomain.com&gt; per tutti i domini SIP supportati che si risolvono in Access Edge IP esterni (s)</span><span class="sxs-lookup"><span data-stu-id="9a56e-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="9a56e-178">Server perimetrali</span><span class="sxs-lookup"><span data-stu-id="9a56e-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="9a56e-179">Abilitare la comunicazione federata in una configurazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="9a56e-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="9a56e-180">Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP suddiviso tra locali e online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-181">DNS un record (s) per FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com che si risolvono in Web Conferencing Edge IP esterno (s)</span><span class="sxs-lookup"><span data-stu-id="9a56e-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="9a56e-182">Computer degli utenti connessi alla rete aziendale interna</span><span class="sxs-lookup"><span data-stu-id="9a56e-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="9a56e-183">Consente agli utenti online di presentare o visualizzare il contenuto nelle riunioni ospitate locali.</span><span class="sxs-lookup"><span data-stu-id="9a56e-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="9a56e-184">Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.</span><span class="sxs-lookup"><span data-stu-id="9a56e-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a56e-185">A seconda del modo in cui il DNS è configurato nell'organizzazione, potrebbe essere necessario aggiungere questi record all'area DNS interna ospitata per i domini SIP corrispondenti per fornire la risoluzione DNS interna a questi record.</span><span class="sxs-lookup"><span data-stu-id="9a56e-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="9a56e-186">Considerazioni sui firewall</span><span class="sxs-lookup"><span data-stu-id="9a56e-186">Firewall Considerations</span></span>

<span data-ttu-id="9a56e-187">I computer della rete devono essere in grado di eseguire ricerche DNS standard su Internet.</span><span class="sxs-lookup"><span data-stu-id="9a56e-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="9a56e-188">Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.</span><span class="sxs-lookup"><span data-stu-id="9a56e-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="9a56e-189">A seconda della posizione del data center dei Microsoft Online Services, è inoltre necessario configurare i dispositivi firewall di rete in modo che accettino connessioni basate su nomi di dominio con caratteri jolly, \*ad esempio tutto il traffico proveniente da. Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9a56e-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="9a56e-190">Se i firewall dell'organizzazione non supportano le configurazioni del nome con caratteri jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.</span><span class="sxs-lookup"><span data-stu-id="9a56e-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="9a56e-191">Fare riferimento all'argomento della Guida per gli [URL e gli intervalli di indirizzi IP di Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="9a56e-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="9a56e-192">Requisiti relativi a porte e protocolli</span><span class="sxs-lookup"><span data-stu-id="9a56e-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="9a56e-193">Oltre ai requisiti delle porte per la comunicazione interna di Lync Server 2013, è inoltre necessario configurare le porte seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a56e-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a56e-194">Protocollo/porta</span><span class="sxs-lookup"><span data-stu-id="9a56e-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="9a56e-195">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="9a56e-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="9a56e-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9a56e-197">Aperta in ingresso</span><span class="sxs-lookup"><span data-stu-id="9a56e-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="9a56e-198">Active Directory Federation Services (ruolo del server federativo)</span><span class="sxs-lookup"><span data-stu-id="9a56e-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="9a56e-199">Per ulteriori informazioni, vedere <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding ADFS Role Services</a>.</span><span class="sxs-lookup"><span data-stu-id="9a56e-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="9a56e-200">Active Directory Federation Services (ruolo del server proxy)</span><span class="sxs-lookup"><span data-stu-id="9a56e-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="9a56e-201">Portale dei Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="9a56e-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="9a56e-202">Portale della società personale</span><span class="sxs-lookup"><span data-stu-id="9a56e-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="9a56e-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="9a56e-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="9a56e-204">Client Lync (comunicazione con Lync Online da Lync Server locale)</span><span class="sxs-lookup"><span data-stu-id="9a56e-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a56e-205">TCP 80 e 443</span><span class="sxs-lookup"><span data-stu-id="9a56e-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="9a56e-206">Aperta in ingresso</span><span class="sxs-lookup"><span data-stu-id="9a56e-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="9a56e-207">Strumento di sincronizzazione della directory dei Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="9a56e-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="9a56e-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="9a56e-209">Apertura in ingresso/in uscita sul server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9a56e-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a56e-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="9a56e-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="9a56e-211">Aprire in ingresso/in uscita per le sessioni di condivisione dei dati</span><span class="sxs-lookup"><span data-stu-id="9a56e-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="9a56e-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9a56e-213">Aprire in ingresso/in uscita per le sessioni di audio, video, condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="9a56e-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a56e-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="9a56e-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="9a56e-215">Aprire in ingresso/in uscita per le sessioni audio e video</span><span class="sxs-lookup"><span data-stu-id="9a56e-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a56e-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="9a56e-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="9a56e-217">Aprire le sessioni audio e video in uscita</span><span class="sxs-lookup"><span data-stu-id="9a56e-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="9a56e-218">Account utente e dati</span><span class="sxs-lookup"><span data-stu-id="9a56e-218">User Accounts and Data</span></span>

<span data-ttu-id="9a56e-219">In una distribuzione ibrida di Lync Server 2013, tutti gli utenti che desiderano effettuare la propria abitazione in Lync Online devono essere prima creati nella distribuzione locale, in modo che l'account utente venga creato in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a56e-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="9a56e-220">È quindi possibile spostare l'utente in Skype for business online, che sposterà l'elenco dei contatti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="9a56e-221">Quando si sincronizzano gli account utente tra le distribuzioni di Lync in locale e Lync Online con ADFS e dirsync, è necessario sincronizzare gli account di Active Directory per tutti gli utenti di Lync nell'organizzazione tra le distribuzioni di Lync locali e online, anche se gli utenti non vengono spostati in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="9a56e-222">Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e quelli online nell'organizzazione potrebbe non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="9a56e-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a56e-223">Se l'utente viene creato utilizzando il portale online per Office 365, l'account utente non verrà sincronizzato con Active Directory locale e l'utente non sarà presente in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="9a56e-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="9a56e-224">Se gli utenti sono già stati creati in Lync Online e si desidera configurare l'ambiente ibrido con un server Lync locale, vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">moveing users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9a56e-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9a56e-225">Durante la pianificazione di una distribuzione ibrida, è consigliabile considerare anche i seguenti problemi relativi all'utente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="9a56e-226">**Contatti utente il**   limite per i contatti per gli utenti di Lync Online è 250.</span><span class="sxs-lookup"><span data-stu-id="9a56e-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="9a56e-227">Tutti i contatti oltre tale numero verranno rimossi dall'elenco contatti dell'utente quando l'account viene spostato in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="9a56e-228">\*\*\*\*   Gli elenchi di contatti, i gruppi e gli elenchi di controllo di accesso per gli utenti di messaggistica istantanea e presenza vengono migrati con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="9a56e-229">**Dati per le conferenze, contenuto di riunioni e riunioni**   pianificate questo contenuto non viene migrato con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="9a56e-230">Gli utenti devono ripianificare le riunioni dopo la migrazione degli account a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="9a56e-231">Criteri e funzionalità per gli utenti</span><span class="sxs-lookup"><span data-stu-id="9a56e-231">User Policies and Features</span></span>

  - <span data-ttu-id="9a56e-232">In un ambiente ibrido di Lync Server 2013, gli utenti possono essere abilitati per la messaggistica istantanea, la voce e le riunioni sia in locale che online, ma non entrambi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9a56e-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="9a56e-233">**Client Lync alcuni**     utenti potrebbero richiedere una nuova versione client quando vengono spostati in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="9a56e-234">Per Office Communications Server 2007 R2, gli utenti devono essere spostati in un pool Lync Server 2013 prima della migrazione a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9a56e-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="9a56e-235">Per ulteriori informazioni sul supporto client, vedere client [per Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) e [i client Lync supportati e le configurazioni delle porte di rete](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="9a56e-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="9a56e-236">**I criteri locali e i criteri di configurazione (non utente)**   online e locale richiedono una configurazione separata.</span><span class="sxs-lookup"><span data-stu-id="9a56e-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="9a56e-237">Non è possibile impostare criteri globali che si applicano a entrambi.</span><span class="sxs-lookup"><span data-stu-id="9a56e-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

