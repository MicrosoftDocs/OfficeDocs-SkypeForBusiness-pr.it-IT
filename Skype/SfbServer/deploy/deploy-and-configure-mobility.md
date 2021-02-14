---
title: Distribuire e configurare i dispositivi mobili per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In questo articolo viene illustrata la procedura per configurare un'installazione esistente di Skype for Business Server per l'utilizzo del servizio per dispositivi mobili, consentendo ai dispositivi mobili di sfruttare le funzionalità di Skype for Business Server Mobility.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820896"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="c3ad8-103">Distribuire e configurare i dispositivi mobili per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3ad8-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="c3ad8-104">In questo articolo viene illustrata la procedura per configurare un'installazione esistente di Skype for Business Server per l'utilizzo del servizio per dispositivi mobili, consentendo ai dispositivi mobili di sfruttare le funzionalità di Skype for Business Server Mobility.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="c3ad8-105">Dopo aver esaminato l'articolo Plan [for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) si dovrebbe essere pronti a procedere con i passaggi seguenti per distribuire Mobility nell'ambiente Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="c3ad8-106">I passaggi sono i seguenti (e in questa tabella viene incluso un elenco di autorizzazioni):</span><span class="sxs-lookup"><span data-stu-id="c3ad8-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="c3ad8-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-107">**Phase**</span></span>|<span data-ttu-id="c3ad8-108">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-108">**Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3ad8-109">[Creare record DNS](deploy-and-configure-mobility.md#CreateDNSRec).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-109">[Create DNS records](deploy-and-configure-mobility.md#CreateDNSRec)</span></span> <br/> |<span data-ttu-id="c3ad8-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c3ad8-110">Domain Admins</span></span>  <br/> <span data-ttu-id="c3ad8-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="c3ad8-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-112">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="c3ad8-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="c3ad8-113">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="c3ad8-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-114">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c3ad8-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="c3ad8-115">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="c3ad8-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-116">Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c3ad8-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="c3ad8-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c3ad8-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-118">Testare la distribuzione per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3ad8-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="c3ad8-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c3ad8-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-120">Configurare il sistema per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c3ad8-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="c3ad8-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c3ad8-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="c3ad8-122">Configurare i criteri per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3ad8-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="c3ad8-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c3ad8-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="c3ad8-124">Tutte le sezioni seguenti contengono passaggi che presuppongono che sia stato letto l'argomento Relativo alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="c3ad8-125">Se qualcosa ti confonde, non esita a consultare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="c3ad8-126">Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c3ad8-127">Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c3ad8-128">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="c3ad8-129">Creare record DNS</span><span class="sxs-lookup"><span data-stu-id="c3ad8-129">Create DNS records</span></span>
<span data-ttu-id="c3ad8-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="c3ad8-131">Potrebbero essere già presenti nell'ambiente Skype for Business Server, ma è necessario creare i record seguenti per il funzionamento di Individuazione automatica:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="c3ad8-132">Un record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="c3ad8-133">Un record DNS esterno (o pubblico) per supportare gli utenti mobili che si connettono dall'esterno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="c3ad8-134">Questi record possono essere nomi A (host) o record CNAME (non è necessario creare entrambi, stiamo solo includendo i passaggi per tutto qui).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="c3ad8-135">Creare un record CNAME DNS interno</span><span class="sxs-lookup"><span data-stu-id="c3ad8-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="c3ad8-136">Accedere a un server DNS nella rete membro del gruppo **Domain Admins** o **DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c3ad8-137">Fare clic sul pulsante **Start,**  scegliere Strumenti di amministrazione **(potrebbe** essere necessario cercarlo se non è un'opzione disponibile nel menu Start), quindi fare clic su **DNS** per aprire lo snap-in di amministrazione DNS.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c3ad8-138">Nel riquadro sinistro della finestra della console, è necessario passare al dominio che ospita i Front End Server di  Skype for Business Server ed espandere le zone di ricerca diretta.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c3ad8-139">Prenditi un po' di tempo per vedere quale dei seguenti elementi hai:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c3ad8-140">Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c3ad8-141">Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c3ad8-142">Dopo aver specificato questa operazione, fare clic con il pulsante destro del mouse sul nome di dominio SIP e scegliere **Nuovo alias (CNAME)** dal menu.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="c3ad8-143">Nella casella **di testo Alias name** digitare lyncdiscoverinternal per il nome host, per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c3ad8-144">Nel nome di dominio completo **(FQDN** per l'host di destinazione), è necessario digitare o selezionare l'FQDN dei servizi Web interni per il pool Front End (o un singolo Front End Server, un pool di server Director o un Director), identificato nel passaggio 4 precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="c3ad8-145">Al momento dell'immissione, fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="c3ad8-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="c3ad8-147">Creare un record CNAME DNS esterno</span><span class="sxs-lookup"><span data-stu-id="c3ad8-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="c3ad8-148">Questi passaggi sono generici, perché non è possibile indicare quale provider DNS pubblico potrebbe essere in uso, ma si vuole comunque aiutare l'utente. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c3ad8-149">A questo punto nel tempo, dovrebbe esistere già un dominio SIP per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c3ad8-150">Espandere la **zona di ricerca diretta** per il dominio SIP o aprirla in altro modo.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c3ad8-151">Prenditi un po' di tempo per vedere quale dei seguenti elementi hai:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c3ad8-152">Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c3ad8-153">Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c3ad8-154">Dopo aver creato queste informazioni, dovrebbe essere possibile selezionare un'opzione per la creazione di un **nuovo alias (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="c3ad8-155">A questo punto dovrebbe essere possibile immettere un **nome alias,** è necessario immettere lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c3ad8-156">Successivamente, deve essere presente un'area da immettere in un FQDN per **l'host** di destinazione, che dovrà essere il nome di dominio completo per il pool Front End (o un singolo Front End Server o un pool di server Director o Director), identificato nel passaggio 3 precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c3ad8-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="c3ad8-158">Creare un record A DNS interno</span><span class="sxs-lookup"><span data-stu-id="c3ad8-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="c3ad8-159">Accedere a un server DNS nella rete membro del gruppo **Domain Admins** o **DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c3ad8-160">Fare clic sul pulsante **Start,**  scegliere Strumenti di amministrazione **(potrebbe** essere necessario cercarlo se non è un'opzione disponibile nel menu Start), quindi fare clic su **DNS** per aprire lo snap-in di amministrazione DNS.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c3ad8-161">Nel riquadro sinistro della finestra della console, è necessario passare al dominio che ospita i Front End Server di  Skype for Business Server ed espandere le zone di ricerca diretta.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c3ad8-162">Prenditi un po' di tempo per vedere quale dei seguenti elementi hai:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c3ad8-163">Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c3ad8-164">Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c3ad8-165">Dopo aver specificato questo parametro, fare clic con il pulsante destro del mouse sul nome di dominio SIP e quindi scegliere Nuovo host (A o **AAAA)** dal menu.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="c3ad8-166">Nella casella **di testo Nome** digitare lyncdiscoverinternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c3ad8-167">Nella casella **di testo Indirizzo IP** digitare l'indirizzo IP dei servizi Web interni per il pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 4 precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="c3ad8-168">Al termine, fare clic **su Aggiungi host** e quindi su **OK.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="c3ad8-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="c3ad8-170">A tale scopo, ripetere i passaggi da 6 a 8 tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="c3ad8-171">Al termine, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="c3ad8-172">Creare un record A DNS esterno</span><span class="sxs-lookup"><span data-stu-id="c3ad8-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="c3ad8-173">Questi passaggi sono generici, perché non è possibile indicare quale provider DNS pubblico potrebbe essere in uso, ma si vuole comunque aiutare l'utente. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c3ad8-174">A questo punto nel tempo, dovrebbe esistere già un dominio SIP per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c3ad8-175">Espandere la **zona di ricerca diretta** per il dominio SIP o aprirla in altro modo.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c3ad8-176">Prenditi un po' di tempo per vedere quale dei seguenti elementi hai:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c3ad8-177">Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c3ad8-178">Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c3ad8-179">Dopo aver creato queste informazioni, dovrebbe essere possibile selezionare un'opzione per la creazione di un nuovo **host A o AAAA.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="c3ad8-180">A questo punto dovrebbe essere possibile immettere **un** nome, è necessario immettere lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c3ad8-181">Successivamente, dovrebbe essere presente un'area da immettere in un indirizzo **IP,** che dovrà essere l'IP del pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 3 precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c3ad8-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="c3ad8-183">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="c3ad8-183">Modify certificates</span></span>
<span data-ttu-id="c3ad8-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="c3ad8-185">In caso di domande sulla pianificazione dei certificati, è stato documentato nell'articolo [Plan for Mobility for Skype for Business Server.](../plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="c3ad8-186">Dopo aver esaminato questo articolo, verrà illustrata la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="c3ad8-187">Sono necessari nuovi certificati?</span><span class="sxs-lookup"><span data-stu-id="c3ad8-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="c3ad8-188">Richiesta di nuovi certificati all'autorità di certificazione (CA).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="c3ad8-189">Aggiornamento dei certificati sul posto con le sostituzioni tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="c3ad8-190">Verifica dei certificati tramite lo snapin Certificati in Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="c3ad8-191">Sono necessari nuovi certificati?</span><span class="sxs-lookup"><span data-stu-id="c3ad8-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="c3ad8-192">In primo luogo, potrebbe essere necessario controllare e vedere quali certificati sono sul posto e se dispongono o meno delle voci necessarie.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="c3ad8-193">A tale scopo, è necessario accedere a Skype for Business Server con un account amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="c3ad8-194">Per alcuni di questi passaggi, potrebbe inoltre essere necessario disporre dei diritti per l'Autorità di certificazione (CA) emittente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="c3ad8-195">Aprire Skype for Business Server Management Shell (è possibile usare la ricerca per trovarla se non è stata aggiunta al menu Start o alla barra delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="c3ad8-196">Sarà essenziale sapere quali certificati sono stati assegnati prima di provare ad aggiungere un certificato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="c3ad8-197">Quindi, al comando, digitare:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="c3ad8-198">Le informazioni del passaggio 3 saranno specifiche dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="c3ad8-199">È necessario cercarlo per determinare se è stato assegnato un singolo certificato per più elementi o se è stato assegnato un certificato diverso per i diversi componenti che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="c3ad8-200">Il **parametro Use** indica come viene utilizzato un certificato e il parametro **Thumbprint** indica se si tratta dello stesso certificato o di più certificati.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="c3ad8-201">Se si dispone delle voci SAN consigliate nella sezione Pianificazione, è possibile.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="c3ad8-202">In caso contrario, dovrai richiedere un nuovo certificato o più certificati (a seconda della configurazione) dall'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="c3ad8-203">Richiedere un nuovo certificato, o certificati, all'autorità di certificazione (CA)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="c3ad8-204">Dopo aver controllato le voci SAN di cui si dispone, si è a sapere di disporre di un singolo certificato **(dopo** aver controllato tramite i passaggi precedenti) e di aver appreso di non disporre di tutte le voci necessarie.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="c3ad8-205">È necessario eseguire una nuova richiesta di certificato all'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c3ad8-206">Aprire Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c3ad8-207">Per un SAN del servizio di individuazione automatica mancante (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c3ad8-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c3ad8-208">Ora, se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c3ad8-209">Sarà invece necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c3ad8-210">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c3ad8-211">Un esempio potrebbe essere la sostituzione del parametro -Ca con il percorso dell'autorità di certificazione:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="c3ad8-212">In or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all thentries you need.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="c3ad8-213">È necessario eseguire una nuova richiesta di certificato all'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c3ad8-214">Aprire Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c3ad8-215">Per un SAN del servizio di individuazione automatica mancante (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c3ad8-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c3ad8-216">Ora, se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c3ad8-217">Sarà invece necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c3ad8-218">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c3ad8-219">Alcuni esempi sono la sostituzione del parametro -Ca con il percorso dell'autorità di certificazione:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="c3ad8-220">Dopo che i nuovi certificati sono stati generati dall'autorità di certificazione, sarà necessario assegnarli.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c3ad8-221">Assegnare certificati tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c3ad8-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="c3ad8-222">A seconda di ciò che hai trovato nella sezione Do I need new certifications precedente, devi eseguire **una** delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="c3ad8-223">Se si dispone di un singolo certificato per tutti gli elementi (le identificazioni di identificazione personale sono identiche), è necessario eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="c3ad8-224">Se hai certificati diversi per le cose (le identificazioni personali sono tutte diverse), esegui questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="c3ad8-225">Visualizzazione dei certificati in Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="c3ad8-226">È possibile esaminare i certificati utilizzando lo snap-in Certificati per MMC.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="c3ad8-227">È sufficiente digitare MMC nella ricerca e dovrebbe essere visualizzato come opzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="c3ad8-228">Per aggiungere lo snap-in Certificati, è necessario fare clic su **File** e quindi su **Aggiungi/Rimuovi snap-in...** (o funzionerebbe anche la scelta rapida da tastiera **CTRL+M).**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="c3ad8-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="c3ad8-230">Sempre nella finestra popup, con ogni probabilità si esegue questa operazione nel computer che ospita i certificati che è necessario esaminare, quindi lasciare la selezione nel **computer** locale, in questo caso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="c3ad8-231">Se lavori su un computer remoto, modifica il pulsante di opzione in Un altro  **computer** e quindi immetti il nome di dominio completo del computer o usa il pulsante Sfoglia per cercare il computer tramite Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="c3ad8-232">Dopo aver selezionato il computer,  è necessario fare clic su Fine quando è pronto e quindi **su OK** per aggiungere lo snap-in a MMC.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="c3ad8-233">Espandere la **sezione** Certificati nel riquadro sinistro di MMC.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="c3ad8-234">Espandere anche **la cartella** Personale e quindi selezionare **Certificati.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="c3ad8-235">In questo modo è possibile visualizzare i certificati in questo archivio.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="c3ad8-236">È necessario individuare il certificato che si desidera visualizzare, fare clic con il pulsante destro del mouse su di esso e scegliere **Apri.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3ad8-237">Come si fa a sapere che certificato si tratta?</span><span class="sxs-lookup"><span data-stu-id="c3ad8-237">How do you know what certificate this is?</span></span> <span data-ttu-id="c3ad8-238">Deve essere il singolo certificato assegnato a tutti gli elementi della farm oppure è possibile disporre di più certificati per elementi diversi, ad esempio Predefinito, Servizi Web interni e così via, nel qual caso potrebbe essere necessario esaminare più certificati.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="c3ad8-239">Più certificati avranno la stessa identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="c3ad8-240">Dopo aver ottenuto la visualizzazione **Certificato,** scegliere **Dettagli.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="c3ad8-241">In questo modo sarà possibile visualizzare il nome del soggetto del certificato quando si seleziona **Oggetto** e vengono visualizzati il nome soggetto assegnato e le proprietà associate.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="c3ad8-242">Sarà inoltre necessario controllare le voci **relative** al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="c3ad8-243">Sono disponibili una o più delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="c3ad8-244">Il nome del pool per il pool o il nome del singolo server se non si tratta di un pool.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="c3ad8-245">Nome del server a cui è assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="c3ad8-246">Record URL semplici, in genere meet e dialin.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="c3ad8-247">Nomi esterni di servizi Web interni e di servizi Web ,ad esempio webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e nelle selezioni di servizi Web sovraccariche.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="c3ad8-248">Se già assegnato, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="c3ad8-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="c3ad8-249">e lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="c3ad8-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="c3ad8-250">record.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-250">records.</span></span>
    
     <span data-ttu-id="c3ad8-251">Dovrai controllare più certificati se ne hai assegnati più di uno (controlla la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="c3ad8-252">Pertanto, se si trova lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="c3ad8-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="c3ad8-253">e lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="c3ad8-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="c3ad8-254">record, questa configurazione è già stata configurata.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-254">records, you've got this configured already.</span></span> <span data-ttu-id="c3ad8-255">È possibile chiudere MMC.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="c3ad8-256">Se non sono assegnati, dovrai effettuare una nuova richiesta di certificato (descritta in precedenza) o installarli dopo la richiesta (ti consigliamo di seguire powershell sopra per questo).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="c3ad8-257">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c3ad8-257">Configure the reverse proxy</span></span>
<span data-ttu-id="c3ad8-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="c3ad8-259">I passaggi seguenti non devono essere eseguiti esattamente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="c3ad8-260">Ciò è dovuto al fatto che nelle versioni precedenti del prodotto, sarebbe stato illustrato, ad esempio, la configurazione di Threat Management Gateway (TMG) e, se non lo si usasse, è necessario determinare la propria versione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="c3ad8-261">TMG non viene più offerto da Microsoft come prodotto e, se è ancora necessario configurarlo, è possibile esaminare i passaggi di [Lync Server 2013.](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="c3ad8-262">Tuttavia, le informazioni seguenti sono destinate a essere più in generale utili, anche se non è possibile fornire passaggi dettagliati specifici per ogni proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="c3ad8-263">Abbiamo due aspetti principali da considerare:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="c3ad8-264">Si sta per eseguire la richiesta di individuazione automatica iniziale su HTTPS (scelta consigliata)?</span><span class="sxs-lookup"><span data-stu-id="c3ad8-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="c3ad8-265">Se si dispone di una regola di pubblicazione Web, è necessario modificarla.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="c3ad8-266">Se non si dispone ancora di una regola di pubblicazione Web, è necessario crearla.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="c3ad8-267">Se si sta eseguendo la richiesta di individuazione automatica iniziale su HTTP, sarà necessario creare o modificare anche tale regola.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c3ad8-268">**Importante** Un valore di timeout proxy è un numero che varia da distribuzione a distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="c3ad8-269">È consigliabile monitorare la distribuzione e modificare il valore per un'esperienza ottimale per i client.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="c3ad8-270">Potresti essere in grado di impostare un valore minimo di 200.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="c3ad8-271">Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire timeout di notifica Push da Office 365, con un valore di timeout pari a 900.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="c3ad8-272">È molto probabile che sia necessario aumentare il valore di timeout per evitare la disconnessione del client quando il valore è troppo basso o diminuire il numero se le connessioni tramite il proxy non si disconnettino, ma si cancellano molto dopo la disconnessione del client.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="c3ad8-273">Il monitoraggio e la definizione delle normali impostazioni dell'ambiente sono l'unico modo accurato per determinare l'impostazione appropriata per questo valore.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="c3ad8-274">Modificare la regola di pubblicazione Web esistente per l'URL e il san di individuazione automatica esterni</span><span class="sxs-lookup"><span data-stu-id="c3ad8-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="c3ad8-275">Apri l'interfaccia del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c3ad8-276">Sarà necessario individuare la regola di pubblicazione Web e scegliere l'opzione Modifica (può essere in un menu o in una scheda, a seconda della configurazione del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="c3ad8-277">Deve essere presente un'area che indica a cosa viene applicata questa regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="c3ad8-278">È necessario modificare questa regola per i siti o le richieste in arrivo per i siti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="c3ad8-279">Si aggiungerà **una** nuova voce.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="c3ad8-280">Digitare il nome del sito di individuazione automatica (l'esempio che verrà utilizzato è lyncdiscover.contoso.com) e fare clic su **OK** o **Salva,** a seconda del formato del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="c3ad8-281">È possibile che sia presente un nuovo certificato contenente la voce san di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="c3ad8-282">Deve essere installato e configurato per l'utilizzo in base alle impostazioni del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="c3ad8-283">Assicurarsi di salvare tutti gli elementi al termine della configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="c3ad8-284">Se il proxy inverso dispone di **una funzionalità di test,** usala per assicurarti che tutto funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="c3ad8-285">A questo punto, potrebbe essere necessario ripetere questi passaggi se si dispone di un director o di un pool di server Director nell'ambiente (ciò significa che si dispone di una seconda regola).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c3ad8-286">Creare una regola di pubblicazione Web per l'URL di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="c3ad8-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="c3ad8-287">Apri l'interfaccia del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c3ad8-288">Dovrai individuare la posizione nell'interfaccia in cui crei le  regole  di pubblicazione Web e scegliere l'opzione Nuovo o Crea (può essere in un menu o in una scheda, a seconda della configurazione del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c3ad8-289">Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c3ad8-290">In genere, è necessario immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c3ad8-291">**Nome**: il nome della regola</span><span class="sxs-lookup"><span data-stu-id="c3ad8-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c3ad8-292">**Azione regola:** in questo caso  si tratta di una regola Consenti, si consente a un elemento di passare attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c3ad8-293">La **regola o** l'opzione di pubblicazione scelta sarà un singolo sito Web o un servizio di **bilanciamento del carico.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c3ad8-294">Deve essere **SSL per** l'accesso esterno, scegliere questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="c3ad8-295">Sarà necessario pubblicare un percorso per La pubblicazione interna e immettere il nome di dominio completo per i servizi Web esterni nel servizio di bilanciamento del carico del pool Front End (o il nome di dominio completo del servizio di bilanciamento del carico del pool di server Director, se esistente), un esempio potrebbe essere sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c3ad8-296">È necessario digitare _ come percorso da pubblicare, ma è necessario **/\\** anche _\*inoltrare l'intestazione host originale\*\*.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="c3ad8-297">Sarà disponibile un'opzione per informazioni o **dettagli sul nome** pubblico o esterno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c3ad8-298">Questo è il punto in cui potrai immettere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c3ad8-299">**Accetta richieste,** ma deve essere per il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c3ad8-300">Per il **nome**, è necessario immettere **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c3ad8-301"><sipdomain> (questo è l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="c3ad8-302">Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, sarà necessario digitare il nome di dominio completo per i servizi Web esterni nel pool Front End, ad esempio lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="c3ad8-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="c3ad8-304">È necessario selezionare un listener _ *SSL*\* con il certificato pubblico aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="c3ad8-305">**La delega dell'autenticazione** deve essere impostata **su Nessuna delega,** ma l'autenticazione client **diretta deve** essere consentita.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="c3ad8-306">La regola deve essere impostata su **Tutti gli utenti.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c3ad8-307">Queste dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire all'utente di procedere.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c3ad8-308">Dovrai assicurarti che l'intestazione **host originale** sia inoltrata.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="c3ad8-309">Sarà necessario impostare anche le porte del server **Web,** sarà necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c3ad8-310">**Reindirizzare le richieste alla porta HTTP** e il numero di porta deve essere **8080.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c3ad8-311">**Reindirizzare le richieste alla porta SSL** e il numero di porta deve essere **4443.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="c3ad8-312">Quando tutto è configurato, sarà necessario salvarli o applicarlo e quindi sarà necessario testare la regola.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="c3ad8-313">Creare una regola di pubblicazione Web per la porta 80 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="c3ad8-314">Apri l'interfaccia del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c3ad8-315">Dovrai individuare la posizione nell'interfaccia in cui crei le  regole  di pubblicazione Web e scegliere l'opzione Nuovo o Crea (può essere in un menu o in una scheda, a seconda della configurazione del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c3ad8-316">Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c3ad8-317">In genere, è necessario immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c3ad8-318">**Nome**: il nome della regola</span><span class="sxs-lookup"><span data-stu-id="c3ad8-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c3ad8-319">**Azione regola:** in questo caso  si tratta di una regola Consenti, si consente a un elemento di passare attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c3ad8-320">La **regola o** l'opzione di pubblicazione scelta sarà un singolo sito Web o un servizio di **bilanciamento del carico.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c3ad8-321">Deve essere una connessione non protetta per connettersi al server Web o **alla farm pubblicata.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="c3ad8-322">Sarà necessario pubblicare un percorso per Pubblicazione interna e immettere il nome di dominio completo per l'indirizzo **VIP** del servizio di bilanciamento del carico del pool Front End, ad esempio sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c3ad8-323">È necessario digitare _ come percorso da pubblicare, ma è necessario **/\\** anche _\*inoltrare l'intestazione host originale\*\*.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="c3ad8-324">Sarà disponibile un'opzione per informazioni o **dettagli sul nome** pubblico o esterno.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c3ad8-325">Questo è il punto in cui potrai immettere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c3ad8-326">**Accetta richieste,** ma deve essere per il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c3ad8-327">Per il **nome**, è necessario immettere **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c3ad8-328"><sipdomain> (questo è l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="c3ad8-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="c3ad8-330">Dovrai selezionare un listener Web o consentire al proxy inverso di crearne uno automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="c3ad8-331">_ *Delega autenticazione*\* deve essere impostata su Nessuna **delega,** ma l'autenticazione client **diretta non deve** essere consentita.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-331">_ *Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="c3ad8-332">La regola deve essere impostata su **Tutti gli utenti.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c3ad8-333">Queste dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire all'utente di procedere.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c3ad8-334">Le **porte del server Web** dovranno essere impostate, sarà necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c3ad8-335">**Reindirizzare le richieste alla porta HTTP** e il numero di porta deve essere **8080.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c3ad8-336">**Reindirizzare le richieste alla porta SSL** e il numero di porta deve essere **4443.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="c3ad8-337">Quando tutto è configurato, sarà necessario salvarli o applicarlo e quindi sarà necessario testare la regola.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="c3ad8-338">Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c3ad8-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="c3ad8-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="c3ad8-340">Gli ambienti ibridi in Skype for Business Server sono ambienti che combinano un ambiente locale e un ambiente O365.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="c3ad8-341">Quando Skype for Business Server lavora in un ambiente ibrido, il servizio di individuazione automatica deve essere in grado di individuare un utente da uno di questi ambienti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="c3ad8-342">Per consentire ai client mobili di individuare la posizione di un utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c3ad8-343">Ecco come procedere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-343">The steps are:</span></span>
  
1. <span data-ttu-id="c3ad8-344">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c3ad8-345">Eseguire il comando seguente per ottenere il valore dell'attributo **ProxyFQDN per** l'ambiente Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="c3ad8-346">Quindi, sempre nella finestra della shell, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="c3ad8-347">Dove [identity] viene sostituito dal nome di dominio dello spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="c3ad8-348">Testare la distribuzione per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3ad8-348">Test your Mobility deployment</span></span>
<span data-ttu-id="c3ad8-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="c3ad8-350">Dopo aver distribuito il servizio Per dispositivi mobili di Skype for Business Server e il servizio di individuazione automatica di Skype for Business Server, è necessario eseguire una transazione di prova per verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="c3ad8-351">È possibile eseguire **Test-CsUcwaConference** per verificare la capacità di due utenti di creare, partecipare e comunicare in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="c3ad8-352">Per eseguire questo test saranno necessari due utenti (reali o test) e le relative credenziali complete.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="c3ad8-353">Questo comando funzionerà sia per i client Skype for Business che per i client Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="c3ad8-354">Per i client Lync Server 2010 in Skype for Business Server 2015, è necessario eseguire **Test-CsMcxP2PIM** per testare.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="c3ad8-355">Gli utenti di Lync Server 2010 dovranno comunque essere utenti effettivi o utenti di test predefiniti e saranno necessarie le credenziali della password.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="c3ad8-356">Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c3ad8-357">Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c3ad8-358">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="c3ad8-359">Testare le conferenze per i client mobili Skype for Business e Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c3ad8-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="c3ad8-360">Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-361">Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome nella ricerca o passare a **Tutti** i programmi e sceglierlo).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c3ad8-362">Nella riga di comando immettere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c3ad8-363">È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c3ad8-364">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="c3ad8-365">Testare le conferenze per i client mobili Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c3ad8-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="c3ad8-366">Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c3ad8-367">Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c3ad8-368">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="c3ad8-369">Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-370">Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome nella ricerca o passare a **Tutti** i programmi e sceglierlo).</span><span class="sxs-lookup"><span data-stu-id="c3ad8-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c3ad8-371">Nella riga di comando immettere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c3ad8-372">È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c3ad8-373">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="c3ad8-374">Per esaminare ulteriormente le procedure di comando, è possibile consultare [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM.](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-374">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="c3ad8-375">Configurare il sistema per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c3ad8-375">Configure for push notifications</span></span>
<span data-ttu-id="c3ad8-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="c3ad8-377">Le notifiche push, sotto forma di notifiche, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'app Skype o Lync è inattiva.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="c3ad8-378">Ma cosa sono le notifiche push?</span><span class="sxs-lookup"><span data-stu-id="c3ad8-378">But what are push notifications?</span></span> <span data-ttu-id="c3ad8-379">Si tratta di avvisi per eventi, ad esempio un invito di messaggistica istantanea nuovo o perso, o per una segreteria telefonica ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="c3ad8-380">Il servizio Per dispositivi mobili di Skype for Business Server invia queste notifiche al servizio di notifica Push di Skype for Business Server basato su cloud, che quindi invia le notifiche al servizio di notifica Push Microsoft (MSNS) per gli utenti di Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="c3ad8-381">Questa funzionalità è invariata rispetto a Lync Server 2013, ma se si dispone di Skype for Business Server, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="c3ad8-382">Per un server perimetrale di Skype for Business Server, aggiungere un nuovo provider di hosting, Microsoft Skype for Business online, quindi configurare la federazione del provider di hosting tra l'organizzazione e Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="c3ad8-383">Abilitare le notifiche push eseguendo il cmdlet **Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="c3ad8-384">Per impostazione predefinita, le notifiche push sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="c3ad8-385">Testare la configurazione della federazione e le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="c3ad8-386">Configurare il server perimetrale Skype for Business per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c3ad8-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="c3ad8-387">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-388">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-389">Aggiungere un provider di hosting online di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="c3ad8-390">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="c3ad8-391">Non è possibile avere più relazioni di federazione con un singolo provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="c3ad8-392">Pertanto, se hai già configurato un provider di hosting con una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="c3ad8-393">Configurare la federazione del provider di hosting tra l'organizzazione e il servizio notifica Push in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="c3ad8-394">Nella riga di comando è necessario digitare:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="c3ad8-395">Abilitare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c3ad8-395">Enable push notifications</span></span>

1. <span data-ttu-id="c3ad8-396">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-397">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-398">Abilitare le notifiche push:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="c3ad8-399">Abilita federazione:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="c3ad8-400">Testare la federazione e le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c3ad8-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="c3ad8-401">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-402">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-403">Testare la configurazione della federazione:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="c3ad8-404">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="c3ad8-405">Testare le notifiche push:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="c3ad8-406">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="c3ad8-407">Configurare i criteri per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3ad8-407">Configure Mobility policy</span></span>
<span data-ttu-id="c3ad8-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="c3ad8-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="c3ad8-409">Con Skype for Business Server è possibile determinare chi può usare il servizio Per dispositivi mobili, Chiamata tramite lavoro, VoIP (Voice over IP) o video, nonché se il WiFi sarà necessario per VoIP o video.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="c3ad8-410">Chiamata tramite ufficio consente a un utente mobile di usare il proprio numero di telefono dell'ufficio, anziché il proprio numero di cellulare, durante l'esecuzione e la ricezione di chiamate.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="c3ad8-411">La persona all'altra estremità della linea non vede il numero di cellulare dell'utente mobile e consente all'utente mobile di evitare addebiti per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="c3ad8-412">Quando voIP e video sono impostati, gli utenti possono effettuare chiamate VoIP e video.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="c3ad8-413">Le impostazioni per l'utilizzo del WiFi determinano se il dispositivo mobile di un utente dovrà usare una rete WiFi su una rete dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="c3ad8-414">Le funzionalità Per dispositivi mobili, Chiamata tramite il lavoro e VoIP e video sono tutte abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="c3ad8-415">L'impostazione per richiedere la connessione WiFi per VoIP e video è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="c3ad8-416">Un amministratore può modificare questa impostazione a livello globale, in base al sito o all'utente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="c3ad8-417">Per poter utilizzare le funzionalità per dispositivi mobili e Chiama da lavoro, gli utenti devono essere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="c3ad8-418">Abilitato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3ad8-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="c3ad8-419">Abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="c3ad8-420">Assegnato un criterio per dispositivi mobili con **l'opzione EnableMobility** impostata su **True.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="c3ad8-421">Per consentire agli utenti di usare Chiama da lavoro, dovranno anche essere:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="c3ad8-422">Assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei** telefoni selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="c3ad8-423">Assegnato un criterio per dispositivi mobili con **EnableOutsideVoice** impostato su **True.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c3ad8-424">Gli utenti che non sono abilitati per VoIP aziendale possono usare i propri dispositivi mobili per effettuare chiamate VoIP Skype a Skype o possono partecipare alle conferenze usando il collegamento A clic per partecipare mentre sono sui dispositivi mobili, se le opzioni appropriate sono impostate per il criterio vocale a cui sono associati.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="c3ad8-425">Nell'argomento relativo alla pianificazione sono disponibili ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="c3ad8-426">Modificare i criteri per dispositivi mobili globali</span><span class="sxs-lookup"><span data-stu-id="c3ad8-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="c3ad8-427">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-428">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-429">Disattiva l'accesso a Dispositivi mobili e Chiama da lavoro a livello globale digitando:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="c3ad8-430">È possibile disattivare Chiama da lavoro senza disattivare l'accesso ai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c3ad8-431">Tuttavia, non è possibile disattivare La mobilità senza disattivare anche Chiama da lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="c3ad8-432">Per altre info, vedere [Set-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-432">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="c3ad8-433">Modificare i criteri per dispositivi mobili in base al sito</span><span class="sxs-lookup"><span data-stu-id="c3ad8-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="c3ad8-434">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-435">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-436">Puoi creare criteri a livello di sito, disattivare VoIP e video, abilitare Richiedi WiFi per IP Audio e Richiedi WiFi per IP Video per sito.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="c3ad8-437">Digitare:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="c3ad8-438">Per ulteriori [informazioni, vedere New-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3ad8-438">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="c3ad8-439">Modificare i criteri per dispositivi mobili in base all'utente</span><span class="sxs-lookup"><span data-stu-id="c3ad8-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="c3ad8-440">Accedere, con un account membro del ruolo **CsAdministrator,** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c3ad8-441">Avviare **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="c3ad8-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3ad8-442">Creare criteri per dispositivi mobili a livello di utente e disattivare Mobilità e Chiamata tramite lavoro per utente.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="c3ad8-443">Digitare:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="c3ad8-444">Un altro esempio con dati di esempio:</span><span class="sxs-lookup"><span data-stu-id="c3ad8-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="c3ad8-445">È possibile disattivare Chiama da lavoro senza disattivare l'accesso ai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c3ad8-446">Tuttavia, non è possibile disattivare La mobilità senza disattivare anche Chiama da lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3ad8-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

