---
title: Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti.'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36187118"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="2ec0e-103">Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2ec0e-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="2ec0e-104">Lo scopo di questo articolo è di specificare le indicazioni necessarie per preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="2ec0e-105">Questo processo richiede pianificazione e preparazione estese.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="2ec0e-106">Esaminare attentamente tutte le informazioni contenute in questo articolo mentre si imposta il piano per disabilitare TLS 1,0 e 1,1 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="2ec0e-107">Tieni presente che esistono molte dipendenze esterne e condizioni di connettività che potrebbero essere interessate dalla disabilitazione di TLS 1.0/1.1, in modo da garantire un'ampia pianificazione e test.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="2ec0e-108">In questo articolo</span><span class="sxs-lookup"><span data-stu-id="2ec0e-108">In this article</span></span>

- [<span data-ttu-id="2ec0e-109">Sfondo e ambito</span><span class="sxs-lookup"><span data-stu-id="2ec0e-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="2ec0e-110">Prerequisiti e processi</span><span class="sxs-lookup"><span data-stu-id="2ec0e-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="2ec0e-111">Scenari di distribuzione avanzati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="2ec0e-112">Sfondo</span><span class="sxs-lookup"><span data-stu-id="2ec0e-112">Background</span></span>

<span data-ttu-id="2ec0e-113">I driver principali per la fornitura di TLS 1,0 e 1,1 disabilitano il supporto per Skype for Business Server locale sono i requisiti per gli standard di sicurezza del Consiglio e per l'elaborazione delle informazioni federali.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="2ec0e-114">Altre informazioni sui requisiti PCI sono disponibili [qui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="2ec0e-115">Microsoft non è in grado di specificare se l'organizzazione deve o meno essere tenuta a rispettare questi o altri requisiti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="2ec0e-116">Devi determinare se è necessario disabilitare TLS 1,0 e/o 1,1 negli ambienti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="2ec0e-117">Microsoft ha prodotto un white paper su TLS disponibile [qui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e consigliamo anche la lettura in background disponibile in questo [Blog di Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="2ec0e-118">Ambito di supporto</span><span class="sxs-lookup"><span data-stu-id="2ec0e-118">Supportability Scope</span></span>

<span data-ttu-id="2ec0e-119">L' *ambito* si riferisce ai limiti di supporto.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="2ec0e-120">Per Skype for Business Server locale, *in ambito* significa che siamo completamente supportati e abbiamo testato la disabilitazione di TLS 1,0 e 1,1 per le versioni di prodotto elencate.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="2ec0e-121">*Attualmente in fase di analisi* significa solo questo; Stiamo esaminando attivamente l'opportunità di portare questi prodotti nell'ambito del supporto per disabilitare TLS.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="2ec0e-122">*Fuori ambito* significa che queste versioni di prodotto non supportano la disabilitazione di TLS 1,0 o 1,1 e non funzionano, con le eccezioni note.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="2ec0e-123">Server completamente testati e supportati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="2ec0e-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2ec0e-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="2ec0e-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([aggiornamento di marzo 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="2ec0e-126">Windows Server 2012 (con KB 3140245 o aggiornamento sostitutivo), 2012 R2 o 2016</span><span class="sxs-lookup"><span data-stu-id="2ec0e-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="2ec0e-127">Aggiornamento sul posto di Skype for Business Server 2015 con CU6 HF2 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="2ec0e-128">Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo) o 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2ec0e-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="2ec0e-129">Connettività di Exchange e Outlook Web App con Exchange Server 2010 SP3 RU19 o versioni successive, indicazioni [qui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="2ec0e-130">Survivable Branch Appliance (SBA) con Skype for Business Server 2015 CU6 HF2 o versioni successive (confermare con il fornitore che ha immesso gli aggiornamenti di giuste e che sono stati resi disponibili per l'appliance)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="2ec0e-131">Survivable Branch Server (SBS) con Skype for Business Server 2015 CU6 HF2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="2ec0e-132">**Solo ruolo Edge**di Lync Server 2013, perché il ruolo Edge non ha una dipendenza dal tessuto Windows 1,0.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="2ec0e-133">Client completamente testati e supportati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="2ec0e-134">Client desktop di Lync 2013 (Skype for business), MSI e C2R, inclusi i [15.0.5023.1000 di base e versioni successive](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="2ec0e-135">Client desktop di Skype for business 2016, MSI [16.0.4678.1000 e versioni successive](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluso Basic</span><span class="sxs-lookup"><span data-stu-id="2ec0e-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="2ec0e-136">Skype for business 2016 fare clic su Esegui per richiedere gli aggiornamenti di [aprile 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="2ec0e-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="2ec0e-137">Mirati mensilmente e semestrale, 16\.0\.9126\.2152 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="2ec0e-138">Semi-annuale e Deferred Channel, 16\.0\.8431\.2242 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="2ec0e-139">Skype for business per Mac 16,15 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="2ec0e-140">Skype for business per iOS e Android 6,19 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="2ec0e-141">Skype Web App 2015 CU6 HF2 e versioni successive (navi con Server)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="2ec0e-142">Attualmente in fase di analisi</span><span class="sxs-lookup"><span data-stu-id="2ec0e-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="2ec0e-143">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="2ec0e-143">Devices</span></span>

- <span data-ttu-id="2ec0e-144">Lync room System (alias</span><span class="sxs-lookup"><span data-stu-id="2ec0e-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="2ec0e-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-145">SRSv1)</span></span>
- <span data-ttu-id="2ec0e-146">Sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ec0e-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="2ec0e-147">Hub Surface</span><span class="sxs-lookup"><span data-stu-id="2ec0e-147">Surface Hub</span></span>
- <span data-ttu-id="2ec0e-148">2015 basato su Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="2ec0e-149">Altro</span><span class="sxs-lookup"><span data-stu-id="2ec0e-149">Other</span></span>

- <span data-ttu-id="2ec0e-150">Dashboard qualità chiamata (nuova installazione dopo la disattivazione di TLS 1,0, 1,1, vedere di seguito) \*</span><span class="sxs-lookup"><span data-stu-id="2ec0e-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="2ec0e-151">Fuori ambito</span><span class="sxs-lookup"><span data-stu-id="2ec0e-151">Out of scope</span></span>

<span data-ttu-id="2ec0e-152">Eccetto dove indicato, i prodotti seguenti non sono nell'ambito del supporto di Disabilitazione TLS 1.0/1.1 e non funzioneranno in un ambiente in cui TLS 1,0 e 1,1 sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="2ec0e-153">Significato: se si usano ancora server o client fuori ambito, è necessario aggiornarli o rimuoverli se è necessario disabilitare TLS 1.0/1.1 in qualsiasi punto della distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="2ec0e-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ec0e-154">Lync Server 2013</span></span>
- <span data-ttu-id="2ec0e-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2ec0e-155">Lync Server 2010</span></span>
- <span data-ttu-id="2ec0e-156">Windows Server 2008 e inferiore</span><span class="sxs-lookup"><span data-stu-id="2ec0e-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="2ec0e-157">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2ec0e-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="2ec0e-158">Lync 2013 per dispositivi mobili-iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2ec0e-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="2ec0e-159">Client di Windows Store "MX" di Lync</span><span class="sxs-lookup"><span data-stu-id="2ec0e-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="2ec0e-160">Tutti i client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2ec0e-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="2ec0e-161">Lync Phone Edition-istruzioni aggiornate [qui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="2ec0e-162">2013 basato su Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="2ec0e-163">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="2ec0e-164">Skype for business per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2ec0e-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="2ec0e-165">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="2ec0e-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="2ec0e-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ec0e-166">Lync Server 2013</span></span>

<span data-ttu-id="2ec0e-167">Lync Server 2013 assume una dipendenza da Windows Fabric versione 1,0.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="2ec0e-168">In fase di progettazione per Lync Server 2013, Windows Fabric 1,0 è stato scelto per la sua convincente e nuova architettura distribuita per consentire la replica, la disponibilità elevata e la tolleranza di errore.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="2ec0e-169">Nel corso del tempo, sia Skype for Business Server che Windows Fabric hanno notevolmente migliorato questa architettura comune con una riprogettazione significativa nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="2ec0e-170">Il server Skype for business 2015 corrente usa il tessuto Windows 3,0, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="2ec0e-171">Purtroppo, Windows Fabric 1,0 non **supporta TLS 1,2.  Verrà tuttavia aggiornato Lync Server 2013 per l'utilizzo con TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="2ec0e-172">Verrà disponibile il prossimo aggiornamento cumulativo per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="2ec0e-173">Stiamo fornendo il supporto di TLS 1,2 per consentire la coesistenza, la migrazione, la Federazione e gli scenari ibridi.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="2ec0e-174">Se è necessaria l'organizzazione per disabilitare TLS 1,0 e 1,1 e attualmente si usa Lync Server 2013, è consigliabile iniziare il processo di pianificazione, con la possibilità di eseguire l'aggiornamento sul posto o la migrazione affiancata (nuovi pool, spostare gli utenti) in Skype for Business Server 2015 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="2ec0e-175">In alternativa, puoi accelerare la migrazione a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="2ec0e-176">Dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="2ec0e-176">Call Quality Dashboard</span></span>

<span data-ttu-id="2ec0e-177">Il dashboard di qualità delle chiamate locali ha attualmente una dipendenza da TLS 1,0 durante la nuova installazione (prima volta che si installa in ambienti locali).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="2ec0e-178">Stiamo attualmente esaminando il problema e intendiamo rilasciare una correzione in un prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="2ec0e-179">Se si prevede di installare Call Quality dashboard e disabilitare anche TLS 1,0, è consigliabile completare prima di tutto l'installazione di Call Quality dashboard e quindi procedere con la disabilitazione di TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="2ec0e-180">Dispositivi di terze parti</span><span class="sxs-lookup"><span data-stu-id="2ec0e-180">Third-party devices</span></span>

<span data-ttu-id="2ec0e-181">Nei dispositivi di terze parti, ad esempio telefoni 3PIP, videoconferenze, proxy inverso e servizi di bilanciamento del carico, assicurarsi di convalidare la supportabilità di TLS 1,2, verificare attentamente e contattare il fornitore, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="2ec0e-182">Considerazioni sulla Federazione quando si disabilita TLS 1.0/1.1 in Edge Server</span><span class="sxs-lookup"><span data-stu-id="2ec0e-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="2ec0e-183">È necessario pianificare attentamente e valutare l'impatto della disabilitazione di TLS 1.0/1.1 nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="2ec0e-184">Dopo aver disabilitato TLS 1,0 e 1,1, è possibile che altre organizzazioni non siano più in grado di eseguire la Federazione con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="2ec0e-185">Si può scegliere di mantenere TLS 1.0/1.1 abilitato in Edge Server per mantenere la compatibilità con le versioni precedenti di sistemi esterni (SfB 2015, Lync 2013) o versioni precedenti (2010).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="2ec0e-186">Microsoft non è in grado di fornire consigli o raccomandazioni per verificare se la rete Edge (o qualsiasi rete) rientra in standard PCI; Questo deve essere determinato dalla singola società.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="2ec0e-187">Skype for business online è attualmente in grado di TLS 1,2, quindi non è previsto alcun impatto sull'ibrido/Federazione con online.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="2ec0e-188">PIC (connettività per messaggistica istantanea pubblica) a Skype Consumer Service: non prevediamo la disabilitazione di TLS 1.0/1.1 per l'impatto della [connettività Skype](../../deploy/deploy-skype-connectivity.md); I gateway Microsoft PIC sono già in grado di TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="2ec0e-189">Prerequisiti e processi</span><span class="sxs-lookup"><span data-stu-id="2ec0e-189">Prerequisites and process</span></span>

<span data-ttu-id="2ec0e-190">Eccetto dove indicato sopra, una volta che i server TLS 1,0 e 1,1 sono disabilitati, i client e i dispositivi non verranno più funzionanti correttamente o a tutti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="2ec0e-191">Ciò significa che è necessario sospendere e attendere le indicazioni aggiornate da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="2ec0e-192">Quando si è soddisfatti di soddisfare tutti i requisiti e si ha un piano per affrontare le lacune, procedere.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="2ec0e-193">Ad alto livello, mentre Skype for Business Server 2019 è pronto per la procedura di installazione, Skype for Business Server 2015 richiederà di installare CU6 HF2, applicando gli aggiornamenti prerequisiti a .NET e SQL, distribuendo le chiavi del registro di sistema e infine un separato ciclo di aggiornamenti della configurazione del sistema operativo (ad esempio disabilitazione di TLS 1,0 e 1,1 tramite l'importazione di file del registro).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="2ec0e-194">È fondamentale completare l'installazione di tutti i prerequisiti, incluso Skype for Business Server 2015 CU6 HF2, prima della disabilitazione di TLS 1,0 e 1,1 in qualsiasi server dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="2ec0e-195">Ogni server Skype for business, inclusi i backend per il ruolo Edge e SQL, richiede gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="2ec0e-196">Verificare inoltre che tutti i client supportati (in ambito) siano stati aggiornati alle versioni minime richieste.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="2ec0e-197">Non dimenticare di aggiornare anche le workstation di gestione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="2ec0e-198">Vogliamo seguire l'ordine usuale delle operazioni di "Inside out" per l'aggiornamento dei server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="2ec0e-199">Trattare i pool di Director, la chat persistente e i pool di coppie nello stesso modo in cui si farebbe normalmente.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="2ec0e-200">L'ordine e i metodi per l'aggiornamento sono coperti [qui](topology.md) e [qui](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="2ec0e-201">Processo di alto livello</span><span class="sxs-lookup"><span data-stu-id="2ec0e-201">High-level process</span></span>

1. <span data-ttu-id="2ec0e-202">Testare tutti i passaggi del Lab prima di configurare i server di produzione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="2ec0e-203">Eseguire il backup e mantenere una copia del registro di sistema esportato su ogni singolo server da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="2ec0e-204">Non è possibile condividere i registri tra server, contengono chiavi esclusive basate su computer.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="2ec0e-205">Aggiornare tutti i server di Skype for business 2015 in CU6 HF2 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="2ec0e-206">(Per Skype for Business Server 2019 non è necessario alcun CU)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="2ec0e-207">Installare tutti i prerequisiti per tutti i server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="2ec0e-208">Distribuire le chiavi del registro di sistema prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="2ec0e-209">Assicurarsi che tutti i client in ambito vengano aggiornati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="2ec0e-210">Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="2ec0e-211">Verificare che i carichi di lavoro funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="2ec0e-212">Se vengono rilevati problemi, risoluzione dei problemi e Risolvi o</span><span class="sxs-lookup"><span data-stu-id="2ec0e-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="2ec0e-213">Ripristinare il registro di sistema dal passaggio 2 per riattivare TLS 1,0 e 1,1</span><span class="sxs-lookup"><span data-stu-id="2ec0e-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="2ec0e-214">Verificare che venga usato solo TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="2ec0e-215">Installare prerequisiti per tutti i server</span><span class="sxs-lookup"><span data-stu-id="2ec0e-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="2ec0e-216">È necessario un ampio aggiornamento delle dipendenze prima di iniziare a disabilitare TLS 1,0 e 1,1 a livello di sistema operativo nelle distribuzioni di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="2ec0e-217">Di seguito sono riportate le versioni minime in grado di supportare TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="2ec0e-218">Distribuire tutti gli aggiornamenti dei prerequisiti in ogni server Skype for business nell'ambiente prima di iniziare a disabilitare TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="2ec0e-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([aggiornamento 2018 marzo](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="2ec0e-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="2ec0e-220">[.NET Framework 4,7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) o versione successiva con SchUseStrongCrypto abilitato nel registro di sistema (disponibile di seguito)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="2ec0e-221">SQL deve essere aggiornato in tutti i server e i backend di Skype for business 2015.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="2ec0e-222">Aggiornare i backend SQL per il pool di Enterprise Edition prima di tutto, quindi i rispettivi FEs.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="2ec0e-223">SQL Server 2014 SP1 + CU5 ([collegamento](https://support.microsoft.com/help/3130926)) o superiore/sql Server 2012 SP2 + CU16 o superiore/sql Server 2014 RTM + CU12 ([collegamento](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) o superiore/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="2ec0e-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="2ec0e-224">SQL Server Native Client per SQL Server 2012 ([collegamento](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="2ec0e-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="2ec0e-225">Driver Microsoft ODBC 11 per SQL Server ([collegamento](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ec0e-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="2ec0e-226">Oggetti di gestione condivisi per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="2ec0e-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="2ec0e-227">SQLSysClrTypes per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="2ec0e-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="2ec0e-228">Procedura di base per installare i prerequisiti, in ordine delle operazioni consigliato</span><span class="sxs-lookup"><span data-stu-id="2ec0e-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="2ec0e-229">Installare l'aggiornamento di Skype for Business Server CU6HF2 (6.0.9319.516) in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="2ec0e-230">Installare l'aggiornamento ai componenti usando l'Updater.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="2ec0e-231">Aggiornare i database in base alle procedure documentate.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="2ec0e-232">Le istruzioni sono documentate in [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="2ec0e-233">Convalidare la funzionalità prodotto nella distribuzione prima di procedere con altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="2ec0e-234">Scarica il programma di installazione offline di .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="2ec0e-235">Riferimento[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="2ec0e-236">Assicurarsi che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="2ec0e-237">Riferimento[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="2ec0e-238">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="2ec0e-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="2ec0e-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="2ec0e-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="2ec0e-240">Eseguire il pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-240">Run the installer package.</span></span>
    7. <span data-ttu-id="2ec0e-241">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-241">Reboot the server.</span></span>
3. <span data-ttu-id="2ec0e-242">Aggiornare SQL Express 2014 in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="2ec0e-243">Riferimento[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="2ec0e-244">Scaricare SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="2ec0e-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="2ec0e-245">Riferimento[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="2ec0e-246">Copiare il supporto di installazione in una cartella nel server (es: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="2ec0e-247">Verificare che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end</span><span class="sxs-lookup"><span data-stu-id="2ec0e-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="2ec0e-248">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2ec0e-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="2ec0e-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2ec0e-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="2ec0e-250">Aprire un prompt dei comandi di amministrazione e aggiornare tutti i componenti e le istanze installati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="2ec0e-251">Esempio: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="2ec0e-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="2ec0e-252">Aggiornare SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="2ec0e-253">Riferimento: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="2ec0e-254">Scarica da[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="2ec0e-255">Verificare che i servizi di 2015 di Skype for Business Server vengano arrestati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="2ec0e-256">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="2ec0e-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="2ec0e-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2ec0e-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="2ec0e-258">Arrestare l'installazione delle istanze di SQL in uso</span><span class="sxs-lookup"><span data-stu-id="2ec0e-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="2ec0e-259">Ex: Get-Service ' MSSQL $ RTCLOCAL ' | Stop-servic</span><span class="sxs-lookup"><span data-stu-id="2ec0e-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="2ec0e-260">Ex: Get-Service ' MSSQL $ LYNCLOCAL ' | Stop-servic</span><span class="sxs-lookup"><span data-stu-id="2ec0e-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="2ec0e-261">Ex (solo Standard Edition): Get-Service ' MSSQL $ RTC ' | Stop-servic</span><span class="sxs-lookup"><span data-stu-id="2ec0e-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="2ec0e-262">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-262">Install the update.</span></span>
5. <span data-ttu-id="2ec0e-263">Aggiornare il driver ODBC 11 per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="2ec0e-264">Riferimento: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="2ec0e-265">Scarica da[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="2ec0e-266">Verificare che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end</span><span class="sxs-lookup"><span data-stu-id="2ec0e-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="2ec0e-267">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2ec0e-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="2ec0e-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2ec0e-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="2ec0e-269">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-269">Install the update.</span></span>
6. <span data-ttu-id="2ec0e-270">Distribuire le chiavi del registro di sistema prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="2ec0e-271">Chiavi del registro di sistema pre-richieste</span><span class="sxs-lookup"><span data-stu-id="2ec0e-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="2ec0e-272">Copiare/incollare il test seguente in blocco note e rinominare TLSPreReq. reg o un nome a scelta, quindi importare:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="2ec0e-273">Per i backend SQL per i pool Enterprise, i prerequisiti e la Disabilitazione TLS devono essere trattati come qualsiasi aggiornamento di SQL o OS; vedere:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="2ec0e-274">Mentre è possibile combinare sia la procedura per la disabilitazione dell'applicazione prerequisito che quella TLS, consigliamo vivamente di applicare tutti i prerequisiti prima di procedere con la disabilitazione di TLS 1,0 e 1,1 a livello di sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="2ec0e-275">L'approccio per la procedura consigliata consiste nel preparare l'ambiente distribuendo tutti i prerequisiti, convalidando che tutti i carichi di lavoro funzionino correttamente e come previsto e quindi procedendo con la Disabilitazione TLS 1.0/1.1 in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="2ec0e-276">Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2ec0e-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="2ec0e-277">Prima di procedere con i passaggi successivi, verificare di *aver completato tutti i prerequisiti e i server Skype for business aggiornati*.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="2ec0e-278">Copiare il testo seguente in un file di blocco note e rinominarlo **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="2ec0e-279">Importare il file con estensione reg in ogni server che si vuole disabilitare TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="2ec0e-280">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-280">Reboot the server.</span></span> <span data-ttu-id="2ec0e-281">Dopo che i servizi sono tornati online, passare al server successivo.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="2ec0e-282">L'approccio per i pool Enterprise Edition è lo stesso che si può fare per qualsiasi aggiornamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="2ec0e-283">Potresti aver notato che stiamo facendo molto di più che disabilitare solo TLS 1,0 e 1,1 qui.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="2ec0e-284">Stiamo supportando il riordino di Cipher Suite (come illustrato sopra) e la disattivazione di alcuni cifrari deboli meno recenti.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="2ec0e-285">Questa è la prima volta che abbiamo ufficialmente supportato queste modifiche all'API SCHANNEL e Crypto in Skype for Business Server ed è importante notare che queste modifiche sono le uniche supportate e testate in questo momento.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="2ec0e-286">Potremmo prendere in considerazione altre configurazioni in futuro, ma per il momento, non modificare il file di importazione del registro di sistema nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="2ec0e-287">Verificare che i carichi di lavoro funzionino come previsto</span><span class="sxs-lookup"><span data-stu-id="2ec0e-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="2ec0e-288">Dopo aver disabilitato TLS 1,0 e 1,1 nell'ambiente, verificare che tutti i carichi di lavoro principali funzionino come previsto, ad esempio messaggistica istantanea & presenza, chiamate P2P, VoIP aziendale e così via.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="2ec0e-289">**Convalidare solo TLS 1,2 viene usato**</span><span class="sxs-lookup"><span data-stu-id="2ec0e-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="2ec0e-290">Fai in modo che il tuo team di sicurezza esegua un nuovo controllo del traffico Skype for business per assicurarti che i protocolli meno recenti TLS 1,0 e 1,1 non siano più in uso.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="2ec0e-291">In alternativa, è possibile usare Internet Explorer per testare le connessioni TLS ai servizi Web da Skype for Business Server 2015 dopo la disattivazione di TLS 1,0 e TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="2ec0e-292">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="2ec0e-293">Selezionare **strumenti** > **Internet Options**.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="2ec0e-294">Selezionare la scheda **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="2ec0e-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="2ec0e-295">In **Impostazioni**scorrere fino alla fine.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="2ec0e-296">Verificare che TLS 1,0, TLS 1,1 e TLS 1,2 siano abilitati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="2ec0e-297">Esplorare l'URL del servizio Web interno del pool di SfB 2015 (deve connettersi correttamente).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="2ec0e-298">Tornare in Internet Explorer e disabilitare l'opzione per l' **uso solo di TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="2ec0e-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="2ec0e-299">Esplorare di nuovo l'URL del servizio Web interno del pool di SfB 2015 (non riesce a connettersi).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opzioni Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="2ec0e-301">Scenari di distribuzione avanzati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="2ec0e-302">Poiché sono necessari alcuni prerequisiti di dipendenza per supportare TLS 1,2 in Skype for business ser 2015, l'installazione da supporto RTM non riesce in qualsiasi sistema in cui TLS 1,0 e 1,1 sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="2ec0e-303">**Distribuzione di nuovi server Standard Edition o pool di Enterprise Edition dopo la disattivazione di TLS 1,0 e 1,1 nell'ambiente.**</span><span class="sxs-lookup"><span data-stu-id="2ec0e-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="2ec0e-304">**Opzione 1:** Usare [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="2ec0e-305">Tieni presente che stiamo aggiornando SmartSetup per adattare i file binari SQL aggiornati in un futuro CU e aggiorniamo questo articolo in futuro.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="2ec0e-306">**Opzione 2:** Pre-installare istanze locali di SQL (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="2ec0e-307">Scaricare e copiare SQL Express 2014 SP2 (SQLEXPR_x64. exe) nella cartella locale in FE.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="2ec0e-308">Supponiamo che il percorso della cartella <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="2ec0e-309">Avviare PowerShell o prompt dei comandi e passare a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="2ec0e-310">Creare l'istanza di SQL RTCLOCAL eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2ec0e-311">Attendere che SQLEXPR_x64. exe finisca prima di procedere:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="2ec0e-312">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "BUILTIN \ \ Administrators "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="2ec0e-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="2ec0e-313">Creare l'istanza di SQL LYNCLOCAL eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2ec0e-314">Attendere che SQLEXPR_x64. exe finisca prima di procedere con il passaggio successivo:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="2ec0e-315">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "BUILTIN \ \ Administrators "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="2ec0e-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="2ec0e-316">Eseguire la configurazione RTM di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="2ec0e-317">Seguire i passaggi rimanenti della sezione Prerequisiti precedente.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="2ec0e-318">**Opzione 3:** È anche possibile sostituire manualmente i file binari in una directory multimediale di installazione locale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="2ec0e-319">Installare prerequisiti per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ec0e-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="2ec0e-320">Installare .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="2ec0e-321">**Nota:** Per la prima volta è stato introdotto il supporto per .NET 4,7 in Skype for Business Server 2015 CU5 + (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="2ec0e-322">Pertanto, nei passaggi successivi di seguito verranno aggiornati i componenti principali prima dell'installazione principale.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="2ec0e-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="2ec0e-324">Riferimento: [software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="2ec0e-325">Copiare file/cartelle ISO:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="2ec0e-326">Con l'ISO di Skype for Business Server 2015 allegato, aprire la directory radice dell'unità in cui è collegata (es: D:\) in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="2ec0e-327">Copiare tutte le cartelle e i file in una cartella in un disco locale (es: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="2ec0e-328">**Nota:** Prima di installare i componenti, sarà necessario aggiornare alcuni file per il supporto di TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="2ec0e-329">Sostituire i pacchetti MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="2ec0e-330">Sostituire i pacchetti MSI e EXE esistenti nella cartella/Setup/amd64/del supporto di installazione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="2ec0e-331">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="2ec0e-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="2ec0e-332">Rinominare in SQLEXPR_x64 nel computer locale e sostituire il file esistente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2ec0e-333">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="2ec0e-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="2ec0e-334">**Nota:** Rinominare questo elemento, se necessario, in sqlncli. msi e quindi sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2ec0e-335">Oggetti di gestione SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2ec0e-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2ec0e-336">**Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2ec0e-337">Selezionare questa pagina per scaricare solo SharedManagementObjects. msi.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="2ec0e-338">**Nota:** Sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2ec0e-339">Tipi CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2ec0e-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2ec0e-340">**Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2ec0e-341">Selezionare per scaricare solo CQLSysClrTypes. msi</span><span class="sxs-lookup"><span data-stu-id="2ec0e-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="2ec0e-342">**Nota**: sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="2ec0e-343">Installare componenti principali:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-343">Install Core Components:</span></span> 
    - <span data-ttu-id="2ec0e-344">Eseguire Setup. exe dalla cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="2ec0e-345">Seguire le istruzioni per installare i componenti principali</span><span class="sxs-lookup"><span data-stu-id="2ec0e-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="2ec0e-346">Chiudere i componenti principali.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-346">Close Core Components.</span></span>
6. <span data-ttu-id="2ec0e-347">Aggiornare i componenti principali:</span><span class="sxs-lookup"><span data-stu-id="2ec0e-347">Update Core Components:</span></span> 
    - <span data-ttu-id="2ec0e-348">Scaricare il programma di installazione di Skype for Business Update.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="2ec0e-349">Eseguire il programma di installazione per aggiornare i componenti principali e installare i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="2ec0e-350">**Nota:** A partire dal rilascio di CU6HF2, la caratteristica di aggiornamento automatico attualmente viene installata solo fino a CU6.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="2ec0e-351">Di conseguenza, l'Updater deve essere eseguito separatamente per aggiornare i componenti principali in 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="2ec0e-352">Riferimentohttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="2ec0e-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="2ec0e-353">Installare strumenti amministrativi (facoltativo):</span><span class="sxs-lookup"><span data-stu-id="2ec0e-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="2ec0e-354">In questo modo verranno installati Microsoft SQL Server 2012 Native client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types per SQL Server 2014 (x64) con i file aggiornati.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="2ec0e-355">Inoltre, il generatore di topologie e il pannello di controllo di Skype for Business Server 2015 saranno disponibili nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="2ec0e-356">Installare lo Store di configurazione locale (passaggio 1):</span><span class="sxs-lookup"><span data-stu-id="2ec0e-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="2ec0e-357">Aprire la distribuzione guidata, fare clic su Installa o Aggiorna Skype for Business Server System, quindi fare clic su **Esegui** al passaggio 1: installare l'archivio configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="2ec0e-358">Fare clic su **Avanti** nella finestra di dialogo **Installa archivio configurazione locale** .</span><span class="sxs-lookup"><span data-stu-id="2ec0e-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="2ec0e-359">![Finestra di dialogo Installa archivio configurazione locale](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="2ec0e-360">Esaminare i risultati e verificare che lo stato dell'attività sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="2ec0e-361">Esaminare il file di log risultante facendo clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="2ec0e-362">![Lo stato delle attività viene visualizzato come completato](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="2ec0e-363">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-363">Click **Finish**.</span></span>
9. <span data-ttu-id="2ec0e-364">Configurare o rimuovere componenti di Skype for Business Server (passaggio 2):</span><span class="sxs-lookup"><span data-stu-id="2ec0e-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="2ec0e-365">Aprire la distribuzione guidata, fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Esegui** al passaggio 2: configurare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ec0e-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="2ec0e-366">Fare clic su **Avanti** nella finestra di dialogo Configura componenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="2ec0e-367">![finestra Configura componenti di Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="2ec0e-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="2ec0e-368">Rivedere il log usando il log della visualizzazione e verificare che il programma di installazione sia stato completato senza problemi.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="2ec0e-369">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="2ec0e-369">Click **Finish**.</span></span>
10. <span data-ttu-id="2ec0e-370">Procedere con l'installazione e la configurazione aggiuntive necessarie (è possibile riprendere le normali procedure di installazione a questo punto).</span><span class="sxs-lookup"><span data-stu-id="2ec0e-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
