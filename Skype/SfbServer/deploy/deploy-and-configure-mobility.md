---
title: Distribuire e configurare i dispositivi mobili per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In questo articolo vengono illustrati i passaggi necessari per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, in modo da poter usufruire delle funzionalità di mobilità di Skype for Business Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029067"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="c86e7-103">Distribuire e configurare i dispositivi mobili per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c86e7-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="c86e7-104">In questo articolo vengono illustrati i passaggi necessari per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, in modo da poter usufruire delle funzionalità di mobilità di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="c86e7-105">Dopo aver esaminato l'articolo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , è necessario essere pronti a procedere con i passaggi riportati di seguito per distribuire la mobilità nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="c86e7-106">I passaggi sono i seguenti (e in questa tabella è incluso un elenco delle autorizzazioni):</span><span class="sxs-lookup"><span data-stu-id="c86e7-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="c86e7-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="c86e7-107">**Phase**</span></span>|<span data-ttu-id="c86e7-108">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="c86e7-108">**Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c86e7-109">[Creare record DNS](deploy-and-configure-mobility.md#CreateDNSRec).</span><span class="sxs-lookup"><span data-stu-id="c86e7-109">[Create DNS records](deploy-and-configure-mobility.md#CreateDNSRec)</span></span> <br/> |<span data-ttu-id="c86e7-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c86e7-110">Domain Admins</span></span>  <br/> <span data-ttu-id="c86e7-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="c86e7-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="c86e7-112">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="c86e7-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="c86e7-113">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="c86e7-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c86e7-114">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c86e7-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="c86e7-115">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="c86e7-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c86e7-116">Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c86e7-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="c86e7-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c86e7-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="c86e7-118">Testare la distribuzione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c86e7-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="c86e7-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c86e7-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="c86e7-120">Configurare il sistema per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c86e7-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="c86e7-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c86e7-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="c86e7-122">Configurare i criteri per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c86e7-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="c86e7-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c86e7-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="c86e7-124">Tutte le sezioni seguenti contengono passaggi che presumono di aver letto l'argomento relativo alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="c86e7-125">Se qualcosa ti confonde, sentiti libero di consultare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="c86e7-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="c86e7-126">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c86e7-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c86e7-127">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c86e7-128">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="c86e7-129">Creare record DNS.</span><span class="sxs-lookup"><span data-stu-id="c86e7-129">Create DNS records</span></span>
<span data-ttu-id="c86e7-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="c86e7-131">Potrebbe essere già presente come parte dell'ambiente di Skype for Business Server, ma è necessario creare i record seguenti per il funzionamento dell'individuazione automatica:</span><span class="sxs-lookup"><span data-stu-id="c86e7-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="c86e7-132">Un record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="c86e7-133">Un record DNS esterno (o pubblico) per supportare gli utenti mobili che si connettono dall'esterno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="c86e7-134">Questi record possono essere nomi A (host) o record CNAME (non è necessario effettuare entrambe le operazioni, sono inclusi solo i passaggi per tutto ciò che segue).</span><span class="sxs-lookup"><span data-stu-id="c86e7-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="c86e7-135">Creare un record CNAME DNS interno</span><span class="sxs-lookup"><span data-stu-id="c86e7-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="c86e7-136">Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c86e7-137">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non è disponibile nel menu Start) e quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.</span><span class="sxs-lookup"><span data-stu-id="c86e7-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c86e7-138">Nel riquadro sinistro della finestra della console, è necessario accedere al dominio che ospita i front end server di Skype for business e quindi espandere le **zone di ricerca diretta** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c86e7-139">Prendere un momento per vedere quali delle seguenti operazioni sono:</span><span class="sxs-lookup"><span data-stu-id="c86e7-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c86e7-140">Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c86e7-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c86e7-141">Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c86e7-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c86e7-142">Dopo aver notato questo passaggio, fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)** dal menu.</span><span class="sxs-lookup"><span data-stu-id="c86e7-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="c86e7-143">Nella casella di testo **nome alias** Digitare lyncdiscoverinternal per il nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c86e7-144">Nel **nome di dominio completo (FQDN per l'host di destinazione**, è necessario digitare o passare all'FQDN dei servizi Web interni per il pool Front End (o un singolo front end server o un pool di Director o un Director), identificato nel passaggio 4 sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="c86e7-145">Quando viene immesso, fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c86e7-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="c86e7-146">È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="c86e7-147">Creare un record CNAME DNS esterno</span><span class="sxs-lookup"><span data-stu-id="c86e7-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="c86e7-148">Questi passaggi sono generici, perché non è possibile stabilire quale provider DNS pubblico è possibile utilizzare, ma è comunque necessario darvi una mano. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.</span><span class="sxs-lookup"><span data-stu-id="c86e7-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c86e7-149">A questo punto, un dominio SIP dovrebbe esistere già per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c86e7-150">Espandere la **zona di ricerca diretta** per il dominio SIP o altrimenti aprirla.</span><span class="sxs-lookup"><span data-stu-id="c86e7-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c86e7-151">Prendere un momento per vedere quali delle seguenti operazioni sono:</span><span class="sxs-lookup"><span data-stu-id="c86e7-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c86e7-152">Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c86e7-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c86e7-153">Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c86e7-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c86e7-154">Una volta che si dispone di tali informazioni, è possibile selezionare un'opzione per la creazione di un **nuovo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="c86e7-155">A questo punto, è possibile immettere un **nome alias**, è necessario immettere lyncdiscover per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c86e7-156">Successivamente dovrebbe essere presente un'area per immettere un **nome di dominio completo per l'host di destinazione**, il nome di dominio completo del pool Front End (o un singolo front end server o un pool di Director o un Director), identificato nel passaggio 3 sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c86e7-157">Potrebbe essere necessario salvare qui, o se è necessario creare altri record CNAME nella zona di ricerca diretta di ogni dominio SIP nell'ambiente di Skype for Business Server, è consigliabile farlo, ma una volta che si è pronti, salvare il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="c86e7-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="c86e7-158">Creare un record A DNS interno</span><span class="sxs-lookup"><span data-stu-id="c86e7-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="c86e7-159">Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c86e7-160">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non è disponibile nel menu Start) e quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.</span><span class="sxs-lookup"><span data-stu-id="c86e7-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c86e7-161">Nel riquadro sinistro della finestra della console, è necessario accedere al dominio che ospita i front end server di Skype for business e quindi espandere le **zone di ricerca diretta** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c86e7-162">Prendere un momento per vedere quali delle seguenti operazioni sono:</span><span class="sxs-lookup"><span data-stu-id="c86e7-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c86e7-163">Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c86e7-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c86e7-164">Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c86e7-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c86e7-165">Dopo aver notato questo passaggio, fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)** dal menu.</span><span class="sxs-lookup"><span data-stu-id="c86e7-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="c86e7-166">Nella casella di testo **nome** Digitare lyncdiscoverinternal per il nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c86e7-167">Nella casella di testo **indirizzo IP** Digitare l'indirizzo IP dei servizi Web interni per il pool Front End (o un singolo server front-end o un pool di Director o un Director), identificato nel passaggio 4 sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="c86e7-168">Al termine, fare clic su **Aggiungi host**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="c86e7-169">È necessario creare un nuovo record a o AAAA di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="c86e7-170">A tale scopo, ripetere i passaggi 6-8 tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="c86e7-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="c86e7-171">Al termine, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="c86e7-172">Creare un record A DNS esterno</span><span class="sxs-lookup"><span data-stu-id="c86e7-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="c86e7-173">Questi passaggi sono generici, perché non è possibile stabilire quale provider DNS pubblico è possibile utilizzare, ma è comunque necessario darvi una mano. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.</span><span class="sxs-lookup"><span data-stu-id="c86e7-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c86e7-174">A questo punto, un dominio SIP dovrebbe esistere già per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c86e7-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c86e7-175">Espandere la **zona di ricerca diretta** per il dominio SIP o altrimenti aprirla.</span><span class="sxs-lookup"><span data-stu-id="c86e7-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c86e7-176">Prendere un momento per vedere quali delle seguenti operazioni sono:</span><span class="sxs-lookup"><span data-stu-id="c86e7-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c86e7-177">Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c86e7-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c86e7-178">Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="c86e7-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c86e7-179">Una volta che si dispone di tali informazioni, è possibile selezionare un'opzione per la creazione di un **nuovo host a o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="c86e7-180">Ora si dovrebbe essere in grado di immettere un **nome**, è necessario immettere Lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c86e7-181">Successivamente dovrebbe essere presente un'area da immettere in un **indirizzo IP**, questo dovrà essere l'IP per il pool Front End (o un singolo server front-end o un pool di Director o un Director), individuato nel passaggio 3 precedente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c86e7-182">Potrebbe essere necessario salvare qui, o se è necessario creare altri record a o AAAA nella zona di ricerca diretta di ogni dominio SIP per l'ambiente di Skype for Business Server, è consigliabile farlo, ma una volta che si è pronti, salvare il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="c86e7-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="c86e7-183">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="c86e7-183">Modify certificates</span></span>
<span data-ttu-id="c86e7-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="c86e7-185">In caso di domande sulla pianificazione dei certificati, è stato documentato l'articolo [relativo al piano per dispositivi mobili per Skype for Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="c86e7-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="c86e7-186">Dopo aver esaminato questo articolo, verrà illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c86e7-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="c86e7-187">Sono necessarie nuove certificazioni?</span><span class="sxs-lookup"><span data-stu-id="c86e7-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="c86e7-188">Richiedere nuovi certificati dall'autorità di certificazione (CA).</span><span class="sxs-lookup"><span data-stu-id="c86e7-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="c86e7-189">Aggiornamento dei certificati sul posto con le sostituzioni tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c86e7-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="c86e7-190">Verifica dei certificati mediante lo snap-in certificati in Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="c86e7-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="c86e7-191">Sono necessarie nuove certificazioni?</span><span class="sxs-lookup"><span data-stu-id="c86e7-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="c86e7-192">In primo luogo, potrebbe essere necessario controllare e vedere quali certificati sono sul posto e se dispongono o meno delle voci necessarie.</span><span class="sxs-lookup"><span data-stu-id="c86e7-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="c86e7-193">A tale scopo, è necessario accedere al server Skype for business con un account che sia un amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="c86e7-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="c86e7-194">Questo account potrebbe anche dover disporre dei diritti per l'autorità di certificazione (CA) emittente, per alcuni di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c86e7-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="c86e7-195">Aprire Skype for Business Server Management Shell (è possibile utilizzare la funzione di ricerca per trovarla se non è stata bloccata al menu Start o alla barra delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="c86e7-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="c86e7-196">Sarà essenziale sapere quali certificati sono stati assegnati prima di provare ad aggiungere un certificato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="c86e7-197">Quindi, al comando, digitare:</span><span class="sxs-lookup"><span data-stu-id="c86e7-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="c86e7-198">Le informazioni del passaggio 3 saranno univoche per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="c86e7-199">È necessario esaminarlo per determinare se si dispone di un singolo certificato assegnato per più elementi o se è stato assegnato un certificato diverso per i diversi componenti che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="c86e7-200">Il parametro **use** indica in che modo viene utilizzato un certificato e il parametro **identificazione personale** indica se si tratta dello stesso certificato o di più certificati.</span><span class="sxs-lookup"><span data-stu-id="c86e7-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="c86e7-201">Se si dispone delle voci di SAN consigliate nella sezione pianificazione, si è a posto.</span><span class="sxs-lookup"><span data-stu-id="c86e7-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="c86e7-202">In caso contrario, è necessario richiedere un nuovo certificato o più certificati (a seconda della configurazione) dall'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="c86e7-203">Richiedere un nuovo certificato o i certificati dall'autorità di certificazione (CA)</span><span class="sxs-lookup"><span data-stu-id="c86e7-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="c86e7-204">Dopo aver verificato la verifica delle voci di SAN, è possibile sapere di disporre di un **singolo certificato** (dopo aver eseguito la procedura descritta in alto) e di aver imparato che non si dispone di tutte le voci necessarie.</span><span class="sxs-lookup"><span data-stu-id="c86e7-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="c86e7-205">È necessario apportare una nuova richiesta di certificato all'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c86e7-206">Aprire la PowerShell di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c86e7-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c86e7-207">Per un servizio SAN di individuazione automatica mancante (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c86e7-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c86e7-208">Se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c86e7-209">È necessario utilizzare invece il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="c86e7-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c86e7-210">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="c86e7-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c86e7-211">Un esempio potrebbe essere (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c86e7-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="c86e7-212">In alternativa, dopo aver verificato le voci di SAN che sono state trovate, si dispone di **più certificati** che non dispongono di tutte le voci necessarie.</span><span class="sxs-lookup"><span data-stu-id="c86e7-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="c86e7-213">È necessario apportare una nuova richiesta di certificato all'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c86e7-214">Aprire la PowerShell di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c86e7-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c86e7-215">Per un servizio SAN di individuazione automatica mancante (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c86e7-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c86e7-216">Se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c86e7-217">È necessario utilizzare invece il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="c86e7-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c86e7-218">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="c86e7-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c86e7-219">Gli esempi potrebbero essere (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):</span><span class="sxs-lookup"><span data-stu-id="c86e7-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="c86e7-220">Dopo che i nuovi certificati sono stati generati dall'autorità di certificazione, sarà necessario assegnarli.</span><span class="sxs-lookup"><span data-stu-id="c86e7-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c86e7-221">Assegnare certificati tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c86e7-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="c86e7-222">A seconda di cosa si è trovato nella sezione non ho bisogno di nuove certificazioni, è necessario eseguire **una** delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="c86e7-223">Se si dispone di un solo certificato per tutti gli elementi (le identificazioni personali sono identici), è necessario eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c86e7-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="c86e7-224">Se sono presenti certificati diversi per gli elementi (le identificazioni personali sono tutte diverse), eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c86e7-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="c86e7-225">Visualizzazione di certificati in Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="c86e7-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="c86e7-226">È possibile esaminare i certificati utilizzando lo snap-in certificati per MMC.</span><span class="sxs-lookup"><span data-stu-id="c86e7-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="c86e7-227">È sufficiente digitare MMC in Search e dovrebbe apparire come un'opzione di applicazione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="c86e7-228">Per aggiungere lo snap-in certificati, è necessario fare clic su **file**e quindi **aggiungere/rimuovere lo snap-in...** (o la combinazione di tasti di scelta rapida **CTRL + M** funzionerebbe anche).</span><span class="sxs-lookup"><span data-stu-id="c86e7-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="c86e7-229">I **certificati** saranno un'opzione nel riquadro sinistro, selezionarlo e quindi **account computer** nella finestra popup, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="c86e7-230">Sempre nella finestra popup, è probabile che si stia eseguendo questa operazione nel computer che ospita i certificati che è necessario esaminare, quindi lasciare la selezione sul **computer locale** , se è così.</span><span class="sxs-lookup"><span data-stu-id="c86e7-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="c86e7-231">Se si lavora su un computer remoto, cambiare il pulsante di opzione su un **altro calcolatore** e quindi immettere il nome di dominio completo del computer o utilizzare il pulsante **Sfoglia** per cercare il computer tramite Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c86e7-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="c86e7-232">Dopo aver selezionato il computer, è necessario fare clic su **fine** quando pronto e quindi su **OK** per aggiungere lo snap-in alla console MMC.</span><span class="sxs-lookup"><span data-stu-id="c86e7-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="c86e7-233">Espandere la sezione **certificati** nel riquadro sinistro della console MMC.</span><span class="sxs-lookup"><span data-stu-id="c86e7-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="c86e7-234">Espandere anche la cartella **personale** e quindi selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="c86e7-235">In questo modo è possibile visualizzare i certificati in questo archivio.</span><span class="sxs-lookup"><span data-stu-id="c86e7-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="c86e7-236">È necessario individuare il certificato che si desidera visualizzare, fare clic con il pulsante destro del mouse su di esso e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c86e7-237">Come si fa a sapere quale certificato è?</span><span class="sxs-lookup"><span data-stu-id="c86e7-237">How do you know what certificate this is?</span></span> <span data-ttu-id="c86e7-238">Dovrebbe essere il singolo certificato assegnato a tutto per la farm oppure possono essere presenti più certificati per cose diverse, come default, servizi Web interni e così via, in questo caso potrebbe essere necessario esaminare più certificati.</span><span class="sxs-lookup"><span data-stu-id="c86e7-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="c86e7-239">Più certificati avranno la stessa identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="c86e7-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="c86e7-240">Dopo aver ottenuto la visualizzazione **certificato** , scegliere **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="c86e7-241">In questo modo viene visualizzato il nome del soggetto del certificato quando si seleziona **soggetto**e viene visualizzato il nome del soggetto assegnato e le proprietà associate.</span><span class="sxs-lookup"><span data-stu-id="c86e7-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="c86e7-242">È inoltre necessario controllare le voci del **nome alternativo soggetto** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="c86e7-243">Sono disponibili una o più delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="c86e7-244">Il nome del pool per il pool o il nome del server singolo se non si tratta di un pool.</span><span class="sxs-lookup"><span data-stu-id="c86e7-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="c86e7-245">Nome del server a cui è assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="c86e7-246">Simple URL Records, in genere Meet e dialin.</span><span class="sxs-lookup"><span data-stu-id="c86e7-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="c86e7-247">Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="c86e7-248">Se è già stato assegnato, il lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.</span><span class="sxs-lookup"><span data-stu-id="c86e7-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="c86e7-249">Se si dispone di più di un utente, è necessario controllare più certificati (vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="c86e7-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="c86e7-250">Pertanto, se si trova lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<SipDomain\> Records, la configurazione è già stata configurata.</span><span class="sxs-lookup"><span data-stu-id="c86e7-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="c86e7-251">È possibile chiudere la console MMC.</span><span class="sxs-lookup"><span data-stu-id="c86e7-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="c86e7-252">Se non sono assegnati, è necessario effettuare una nuova richiesta di certificato (descritta sopra) oppure è necessario installarla dopo la richiesta (si consiglia di eseguire la seguente procedura di PowerShell in questo caso).</span><span class="sxs-lookup"><span data-stu-id="c86e7-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="c86e7-253">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c86e7-253">Configure the reverse proxy</span></span>
<span data-ttu-id="c86e7-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="c86e7-255">I passaggi riportati di seguito non devono essere seguiti in modo esatto.</span><span class="sxs-lookup"><span data-stu-id="c86e7-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="c86e7-256">Ciò è dovuto al fatto che nelle versioni precedenti del prodotto, ad esempio, è stata configurata la configurazione di Threat Management Gateway (TMG) e, se non è stato utilizzato, è necessario elaborare la propria versione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="c86e7-257">TMG non è più offerto da Microsoft come prodotto e, se è ancora necessario configurarlo, è possibile esaminare i [passaggi di Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c86e7-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="c86e7-258">Tuttavia, le seguenti informazioni sono destinate a essere più generalmente utili, anche se non è possibile fornire procedure dettagliate specifiche per ogni proxy inverso là fuori.</span><span class="sxs-lookup"><span data-stu-id="c86e7-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="c86e7-259">Sono due le principali considerazioni da prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="c86e7-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="c86e7-260">Si intende eseguire la richiesta di individuazione automatica iniziale su HTTPS (cosa consigliata)?</span><span class="sxs-lookup"><span data-stu-id="c86e7-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="c86e7-261">Se si dispone di una regola di pubblicazione Web, è necessario modificarla.</span><span class="sxs-lookup"><span data-stu-id="c86e7-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="c86e7-262">Se non si dispone ancora di una regola di pubblicazione Web, è necessario crearla.</span><span class="sxs-lookup"><span data-stu-id="c86e7-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="c86e7-263">Se si sta eseguendo la richiesta di individuazione automatica iniziale su HTTP, sarà necessario creare o modificare anche la regola.</span><span class="sxs-lookup"><span data-stu-id="c86e7-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c86e7-264">**Importante** Un valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="c86e7-265">È necessario monitorare la distribuzione e modificare il valore per la migliore esperienza per i client.</span><span class="sxs-lookup"><span data-stu-id="c86e7-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="c86e7-266">Potrebbe essere possibile impostare il valore come minimo di 200.</span><span class="sxs-lookup"><span data-stu-id="c86e7-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="c86e7-267">Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire i timeout di notifica push da Office 365, che hanno un valore di timeout di 900.</span><span class="sxs-lookup"><span data-stu-id="c86e7-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="c86e7-268">È molto probabile che sia necessario aumentare il valore di timeout per evitare che il client si disconnetta quando il valore è troppo basso oppure diminuisce il numero se le connessioni tramite il proxy non si disconnettono ma sono chiare dopo la disconnessione del client.</span><span class="sxs-lookup"><span data-stu-id="c86e7-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="c86e7-269">Il monitoraggio e la previsione dei requisiti usuali per l'ambiente sono l'unico modo esatto per determinare l'impostazione appropriata per questo valore.</span><span class="sxs-lookup"><span data-stu-id="c86e7-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="c86e7-270">Modificare la regola di pubblicazione Web esistente per la SAN e l'URL di individuazione automatica esterni</span><span class="sxs-lookup"><span data-stu-id="c86e7-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="c86e7-271">Aprire l'interfaccia proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c86e7-272">È necessario individuare la regola di pubblicazione Web e scegliere l'opzione di modifica, che può essere visualizzata in un menu o in una scheda, a seconda della configurazione del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="c86e7-273">Deve essere presente un'area a cui viene applicata la regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c86e7-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="c86e7-274">È necessario modificare questa regola per i siti in ingresso o le richieste per i siti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="c86e7-275">Si sta per **aggiungere** una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="c86e7-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="c86e7-276">Digitare il nome del sito di individuazione automatica (l'esempio che verrà utilizzato è lyncdiscover.contoso.com) e fare clic su **OK** o su **Salva**, a seconda del formato del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="c86e7-277">Potrebbe essere presente un nuovo certificato che contiene la voce SAN di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="c86e7-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="c86e7-278">Che deve essere installato e configurato per l'utilizzo in base alle impostazioni del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="c86e7-279">Assicurarsi di salvare tutto quando la configurazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c86e7-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="c86e7-280">Se il proxy inverso dispone di una funzionalità di **testing** , utilizzarlo per assicurarsi che tutto funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="c86e7-281">A questo punto, potrebbe essere necessario ripetere questi passaggi se si dispone di un server Director o di un pool di server Director nell'ambiente in uso, ovvero se si dispone di una seconda regola.</span><span class="sxs-lookup"><span data-stu-id="c86e7-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c86e7-282">Creare una regola di pubblicazione Web per l'URL di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="c86e7-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="c86e7-283">Aprire l'interfaccia proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c86e7-284">È necessario individuare la posizione dell'interfaccia per la creazione delle regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o in una scheda, a seconda della configurazione del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="c86e7-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c86e7-285">Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c86e7-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c86e7-286">In genere, è necessario immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c86e7-287">**Nome**: il nome della regola</span><span class="sxs-lookup"><span data-stu-id="c86e7-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c86e7-288">**Azione della regola**: in questo caso è una regola **Allow** , si sta lasciando che qualcosa passi attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c86e7-289">La regola di **pubblicazione** o l'opzione che si sta scegliendo potrebbe essere un **singolo sito Web o un bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c86e7-290">Questo deve essere **SSL** per l'accesso esterno, scegliere quell'opzione.</span><span class="sxs-lookup"><span data-stu-id="c86e7-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="c86e7-291">Sarà necessario pubblicare un percorso per la **pubblicazione interna**e immettere il nome di dominio completo per i servizi Web esterni sul bilanciamento del carico del pool Front End (o il nome di dominio completo del servizio di bilanciamento del carico del pool di server Director se ne esiste uno), un esempio potrebbe essere sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="c86e7-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c86e7-292">È necessario digitare \*\* / \*\*\* come percorso da pubblicare, ma è anche necessario **inoltrare l'intestazione host originale**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="c86e7-293">Vi sarà un'opzione per i dettagli del **nome pubblico o esterno** o informazioni.</span><span class="sxs-lookup"><span data-stu-id="c86e7-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c86e7-294">Questo è il luogo in cui sarà possibile immettere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c86e7-295">**Accetta richieste**, ma dovrebbe essere per il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="c86e7-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c86e7-296">Per il **nome**, è necessario immettere **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="c86e7-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c86e7-297"><sipdomain>(questo è l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="c86e7-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="c86e7-298">A questo punto, se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, è necessario digitare il nome di dominio completo per i servizi Web esterni nel pool Front End (ad esempio, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c86e7-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="c86e7-299">Verrà visualizzata un'opzione **percorso** e sarà necessario immettere \*\* / \*\*\* qui.</span><span class="sxs-lookup"><span data-stu-id="c86e7-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="c86e7-300">È necessario selezionare un **listener SSL** con il certificato pubblico aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c86e7-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="c86e7-301">La **delega di autenticazione** deve essere impostata su **Nessuna delega**, ma **dovrebbe** essere consentita l'autenticazione diretta del client.</span><span class="sxs-lookup"><span data-stu-id="c86e7-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="c86e7-302">La regola deve essere impostata su **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c86e7-303">Queste devono essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.</span><span class="sxs-lookup"><span data-stu-id="c86e7-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c86e7-304">Sarà necessario verificare che l' **intestazione host originale** sia inoltrata.</span><span class="sxs-lookup"><span data-stu-id="c86e7-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="c86e7-305">Sarà necessario impostare anche le porte del **server Web** , è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c86e7-306">**Reindirizzare le richieste alla porta http** e il numero di porta dovrebbe essere **8080**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c86e7-307">**Reindirizzare le richieste alla porta SSL** e il numero di porta dovrebbe essere **4443**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="c86e7-308">Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si desidera testare la regola.</span><span class="sxs-lookup"><span data-stu-id="c86e7-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="c86e7-309">Creare una regola di pubblicazione Web per la porta 80 (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="c86e7-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="c86e7-310">Aprire l'interfaccia proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c86e7-311">È necessario individuare la posizione dell'interfaccia per la creazione delle regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o in una scheda, a seconda della configurazione del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="c86e7-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c86e7-312">Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c86e7-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c86e7-313">In genere, è necessario immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c86e7-314">**Nome**: il nome della regola</span><span class="sxs-lookup"><span data-stu-id="c86e7-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c86e7-315">**Azione della regola**: in questo caso è una regola **Allow** , si sta lasciando che qualcosa passi attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c86e7-316">La regola di **pubblicazione** o l'opzione che si sta scegliendo potrebbe essere un **singolo sito Web o un bilanciamento del carico**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c86e7-317">Questa operazione deve essere una **connessione non protetta per la connessione al server Web o alla farm pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="c86e7-318">Sarà necessario pubblicare un percorso per la **pubblicazione interna**e immettere il nome di dominio completo per l' **indirizzo VIP** del sistema di bilanciamento del carico del pool Front End, un esempio potrebbe essere sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="c86e7-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c86e7-319">È necessario digitare \*\* / \*\*\* come percorso da pubblicare, ma è anche necessario **inoltrare l'intestazione host originale**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="c86e7-320">Vi sarà un'opzione per i dettagli del **nome pubblico o esterno** o informazioni.</span><span class="sxs-lookup"><span data-stu-id="c86e7-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c86e7-321">Questo è il luogo in cui sarà possibile immettere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c86e7-322">**Accetta richieste**, ma dovrebbe essere per il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="c86e7-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c86e7-323">Per il **nome**, è necessario immettere **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="c86e7-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c86e7-324"><sipdomain>(questo è l'URL del servizio di individuazione automatica esterno).</span><span class="sxs-lookup"><span data-stu-id="c86e7-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="c86e7-325">Verrà visualizzata un'opzione **percorso** e sarà necessario immettere \*\* / \*\*\* qui.</span><span class="sxs-lookup"><span data-stu-id="c86e7-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="c86e7-326">È necessario selezionare un listener Web o consentire al proxy inverso di crearne uno.</span><span class="sxs-lookup"><span data-stu-id="c86e7-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="c86e7-327">La **delega di autenticazione** deve essere impostata su **Nessuna delega**, ma **non deve** essere consentita l'autenticazione diretta del client.</span><span class="sxs-lookup"><span data-stu-id="c86e7-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="c86e7-328">La regola deve essere impostata su **tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c86e7-329">Queste devono essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.</span><span class="sxs-lookup"><span data-stu-id="c86e7-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c86e7-330">Sarà necessario impostare le porte del **server Web** , è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c86e7-331">**Reindirizzare le richieste alla porta http** e il numero di porta dovrebbe essere **8080**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c86e7-332">**Reindirizzare le richieste alla porta SSL** e il numero di porta dovrebbe essere **4443**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="c86e7-333">Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si desidera testare la regola.</span><span class="sxs-lookup"><span data-stu-id="c86e7-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="c86e7-334">Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c86e7-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="c86e7-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="c86e7-336">Gli ambienti ibridi in Skype for Business Server sono ambienti che combinano un ambiente locale e O365.</span><span class="sxs-lookup"><span data-stu-id="c86e7-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="c86e7-337">Quando si utilizza Skype for Business Server in un ambiente ibrido, il servizio di individuazione automatica deve essere in grado di individuare un utente da uno di questi ambienti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="c86e7-338">Per consentire ai client mobili di individuare il luogo in cui si trova l'utente, il servizio di individuazione automatica deve essere configurato con un nuovo URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="c86e7-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c86e7-339">Ecco come procedere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-339">The steps are:</span></span>
  
1. <span data-ttu-id="c86e7-340">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c86e7-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c86e7-341">Per ottenere il valore dell'attributo **ProxyFqdn** per l'ambiente di Skype for Business Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="c86e7-342">Quindi, sempre nella finestra di Shell, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c86e7-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="c86e7-343">Dove [identity] viene sostituito dal nome di dominio dello spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="c86e7-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="c86e7-344">Testare la distribuzione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c86e7-344">Test your Mobility deployment</span></span>
<span data-ttu-id="c86e7-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="c86e7-346">Dopo aver distribuito il servizio per dispositivi mobili di Skype for Business Server e il servizio di individuazione automatica di Skype for Business Server, è necessario eseguire una transazione di test per verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="c86e7-347">È possibile eseguire **test-CsUcwaConference** per verificare la capacità di due utenti di creare, partecipare e comunicare in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c86e7-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="c86e7-348">Per eseguire questo test, sono necessari due utenti (reale o di prova) e le loro credenziali complete.</span><span class="sxs-lookup"><span data-stu-id="c86e7-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="c86e7-349">Questo comando funzionerà sia per i client Skype for business che per i client Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c86e7-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="c86e7-350">Per i client di Lync Server 2010 su Skype for Business Server 2015, è necessario eseguire **Test-CsMcxP2PIM** per testare.</span><span class="sxs-lookup"><span data-stu-id="c86e7-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="c86e7-351">Gli utenti di Lync Server 2010 dovranno comunque essere utenti effettivi, o utenti di test predefiniti, ed è necessario disporre delle credenziali per la password.</span><span class="sxs-lookup"><span data-stu-id="c86e7-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="c86e7-352">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c86e7-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c86e7-353">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c86e7-354">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="c86e7-355">Servizi di conferenza di prova per Skype for business e Lync 2013 per i client mobili</span><span class="sxs-lookup"><span data-stu-id="c86e7-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="c86e7-356">Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sia installato **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-357">Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in Search o andare a **tutti i programmi** e sceglierlo).</span><span class="sxs-lookup"><span data-stu-id="c86e7-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c86e7-358">Nella riga di comando, immettere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c86e7-359">È inoltre possibile impostare le credenziali in uno script e passarle al cmdlet test.</span><span class="sxs-lookup"><span data-stu-id="c86e7-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c86e7-360">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="c86e7-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="c86e7-361">Testare le conferenze per i client per dispositivi mobili Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c86e7-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="c86e7-362">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c86e7-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c86e7-363">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="c86e7-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c86e7-364">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="c86e7-365">Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sia installato **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-366">Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in Search o andare a **tutti i programmi** e sceglierlo).</span><span class="sxs-lookup"><span data-stu-id="c86e7-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c86e7-367">Nella riga di comando, immettere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c86e7-368">È inoltre possibile impostare le credenziali in uno script e passarle al cmdlet test.</span><span class="sxs-lookup"><span data-stu-id="c86e7-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c86e7-369">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="c86e7-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="c86e7-370">Per esaminare ulteriormente le procedure dei comandi, è possibile estrarre [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c86e7-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="c86e7-371">Configurare il sistema per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c86e7-371">Configure for push notifications</span></span>
<span data-ttu-id="c86e7-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="c86e7-373">Le notifiche push, sotto forma di badge, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'app Skype o Lync non è attiva.</span><span class="sxs-lookup"><span data-stu-id="c86e7-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="c86e7-374">Ma cosa sono le notifiche push?</span><span class="sxs-lookup"><span data-stu-id="c86e7-374">But what are push notifications?</span></span> <span data-ttu-id="c86e7-375">Sono avvisi di eventi, come un invito a messaggistica istantanea nuovo o mancante, o per una segreteria telefonica ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c86e7-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="c86e7-376">Il servizio per dispositivi mobili di Skype for Business Server invia queste notifiche al servizio di notifica push di Skype for Business Server basato sul cloud, che invia quindi le notifiche al servizio di notifica push di Microsoft (MSNS) per gli utenti di Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="c86e7-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="c86e7-377">Questa funzionalità è invariata rispetto a Lync Server 2013, ma se si dispone di un server Skype for business, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c86e7-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="c86e7-378">Per un server perimetrale di Skype for Business Server, aggiungere un nuovo provider di hosting, Microsoft Skype for business online e quindi configurare la Federazione dei provider di hosting tra l'organizzazione e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c86e7-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="c86e7-379">Abilitare le notifiche push eseguendo il cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="c86e7-380">Per impostazione predefinita, le notifiche push sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="c86e7-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="c86e7-381">Testare la configurazione della Federazione e le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="c86e7-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="c86e7-382">Configurare il server perimetrale di Skype for business per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c86e7-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="c86e7-383">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-384">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-385">Aggiungere un provider di hosting di Skype for Business Server online.</span><span class="sxs-lookup"><span data-stu-id="c86e7-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="c86e7-386">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c86e7-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="c86e7-387">Non è possibile avere più di una relazione di federazione con un singolo provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="c86e7-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="c86e7-388">Pertanto, se è già stato configurato un provider di hosting con una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="c86e7-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="c86e7-389">Configurare la Federazione dei provider di hosting tra l'organizzazione e il servizio di notifica push in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c86e7-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="c86e7-390">Nella riga di comando, è necessario digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c86e7-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="c86e7-391">Abilitare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c86e7-391">Enable push notifications</span></span>

1. <span data-ttu-id="c86e7-392">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-393">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-394">Abilitare le notifiche push:</span><span class="sxs-lookup"><span data-stu-id="c86e7-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="c86e7-395">Abilitare la Federazione:</span><span class="sxs-lookup"><span data-stu-id="c86e7-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="c86e7-396">Verificare la Federazione e le notifiche push</span><span class="sxs-lookup"><span data-stu-id="c86e7-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="c86e7-397">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-398">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-399">Testare la configurazione della Federazione:</span><span class="sxs-lookup"><span data-stu-id="c86e7-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="c86e7-400">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c86e7-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="c86e7-401">Testare le notifiche push:</span><span class="sxs-lookup"><span data-stu-id="c86e7-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="c86e7-402">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c86e7-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="c86e7-403">Configurare i criteri per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c86e7-403">Configure Mobility policy</span></span>
<span data-ttu-id="c86e7-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="c86e7-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="c86e7-405">Si ha la possibilità con Skype for Business Server di determinare gli utenti che possono utilizzare il servizio per dispositivi mobili, la chiamata tramite lavoro, la VoIP (Voice over IP) o il video, nonché l'eventuale presenza di WiFi per VoIP o video.</span><span class="sxs-lookup"><span data-stu-id="c86e7-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="c86e7-406">Chiamata tramite lavoro consente a un utente mobile di utilizzare il numero di telefono dell'ufficio, invece del numero di cellulare, quando si effettuano chiamate.</span><span class="sxs-lookup"><span data-stu-id="c86e7-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="c86e7-407">La persona all'altra estremità della linea non vedrà il numero di cellulare dell'utente mobile e consente all'utente mobile di evitare le spese di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="c86e7-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="c86e7-408">Quando vengono configurati VoIP e video, gli utenti possono effettuare chiamate VoIP e video.</span><span class="sxs-lookup"><span data-stu-id="c86e7-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="c86e7-409">Le impostazioni per l'utilizzo di Wi-Fi determinano se il dispositivo mobile di un utente dovrà utilizzare una rete Wi-Fi su una rete di dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="c86e7-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="c86e7-410">La mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono tutte abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c86e7-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="c86e7-411">L'impostazione per richiedere il WiFi per VoIP e video è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c86e7-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="c86e7-412">Un amministratore può modificare questa impostazione, sia a livello globale, per sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="c86e7-413">Per poter utilizzare le funzionalità di mobilità e chiamare tramite il lavoro, gli utenti devono essere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="c86e7-414">Abilitata per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c86e7-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="c86e7-415">Abilitata per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c86e7-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="c86e7-416">Assegnato un criterio per dispositivi mobili con l'opzione **EnableMobility** impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="c86e7-417">Affinché gli utenti siano in grado di utilizzare la chiamata tramite il lavoro, dovranno anche essere:</span><span class="sxs-lookup"><span data-stu-id="c86e7-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="c86e7-418">È stato assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei telefoni** selezionati.</span><span class="sxs-lookup"><span data-stu-id="c86e7-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="c86e7-419">Assegnato un criterio per dispositivi mobili con **EnableOutsideVoice** impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c86e7-420">Gli utenti che non sono abilitati per VoIP aziendale possono utilizzare i propri dispositivi mobili per effettuare chiamate Skype su Skype o possono partecipare a conferenze usando il collegamento fare clic per partecipare ai propri dispositivi mobili, se sono state impostate le opzioni appropriate per il criterio vocale a cui sono associati. con.</span><span class="sxs-lookup"><span data-stu-id="c86e7-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="c86e7-421">Nell'argomento relativo alla pianificazione sono disponibili ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="c86e7-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="c86e7-422">Modificare i criteri di mobilità globale</span><span class="sxs-lookup"><span data-stu-id="c86e7-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="c86e7-423">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-424">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-425">Disattivare l'accesso alla mobilità e chiamare tramite il lavoro a livello globale digitando:</span><span class="sxs-lookup"><span data-stu-id="c86e7-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="c86e7-426">È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="c86e7-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c86e7-427">Tuttavia, non è possibile disattivare la mobilità senza disattivare anche la chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="c86e7-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="c86e7-428">Per altre informazioni, vedere [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c86e7-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="c86e7-429">Modificare i criteri per dispositivi mobili per sito</span><span class="sxs-lookup"><span data-stu-id="c86e7-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="c86e7-430">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-431">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-432">È possibile creare criteri a livello di sito, disattivare VoIP e video, abilitare Richiedi WiFi per l'audio IP e richiedere il Wi-Fi per IP video per sito.</span><span class="sxs-lookup"><span data-stu-id="c86e7-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="c86e7-433">Tipo</span><span class="sxs-lookup"><span data-stu-id="c86e7-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="c86e7-434">Per ulteriori informazioni, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c86e7-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="c86e7-435">Modifica dei criteri per dispositivi mobili in base all'utente</span><span class="sxs-lookup"><span data-stu-id="c86e7-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="c86e7-436">Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .</span><span class="sxs-lookup"><span data-stu-id="c86e7-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c86e7-437">Avviare la **Shell di gestione di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c86e7-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c86e7-438">Creare criteri di mobilità a livello di utente e disattivare la mobilità e la chiamata tramite lavoro da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c86e7-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="c86e7-439">Tipo</span><span class="sxs-lookup"><span data-stu-id="c86e7-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="c86e7-440">Un ulteriore esempio con i dati di esempio:</span><span class="sxs-lookup"><span data-stu-id="c86e7-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="c86e7-441">È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="c86e7-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c86e7-442">Tuttavia, non è possibile disattivare la mobilità senza disattivare anche la chiamata tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="c86e7-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

