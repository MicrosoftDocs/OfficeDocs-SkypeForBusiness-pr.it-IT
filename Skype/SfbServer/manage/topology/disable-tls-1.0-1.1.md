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
ms.openlocfilehash: ce158aeaa84e00367b265404fe3d3407606f4759
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077439"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="62d96-103">Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="62d96-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="62d96-104">Lo scopo di questo articolo è di specificare le indicazioni necessarie per preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti.</span><span class="sxs-lookup"><span data-stu-id="62d96-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="62d96-105">Questo processo richiede pianificazione e preparazione estese.</span><span class="sxs-lookup"><span data-stu-id="62d96-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="62d96-106">Esaminare attentamente tutte le informazioni contenute in questo articolo mentre si imposta il piano per disabilitare TLS 1,0 e 1,1 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="62d96-107">Tieni presente che esistono molte dipendenze esterne e condizioni di connettività che potrebbero essere interessate dalla disabilitazione di TLS 1.0/1.1, in modo da garantire un'ampia pianificazione e test.</span><span class="sxs-lookup"><span data-stu-id="62d96-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="62d96-108">In questo articolo</span><span class="sxs-lookup"><span data-stu-id="62d96-108">In this article</span></span>

- [<span data-ttu-id="62d96-109">Sfondo e ambito</span><span class="sxs-lookup"><span data-stu-id="62d96-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="62d96-110">Prerequisiti e processi</span><span class="sxs-lookup"><span data-stu-id="62d96-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="62d96-111">Scenari di distribuzione avanzati</span><span class="sxs-lookup"><span data-stu-id="62d96-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="62d96-112">Sfondo</span><span class="sxs-lookup"><span data-stu-id="62d96-112">Background</span></span>

<span data-ttu-id="62d96-113">I driver principali per la fornitura di TLS 1,0 e 1,1 disabilitano il supporto per Skype for Business Server locale sono i requisiti per gli standard di sicurezza del Consiglio e per l'elaborazione delle informazioni federali.</span><span class="sxs-lookup"><span data-stu-id="62d96-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="62d96-114">Altre informazioni sui requisiti PCI sono disponibili [qui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="62d96-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="62d96-115">Microsoft non è in grado di specificare se l'organizzazione deve o meno essere tenuta a rispettare questi o altri requisiti.</span><span class="sxs-lookup"><span data-stu-id="62d96-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="62d96-116">Devi determinare se è necessario disabilitare TLS 1,0 e/o 1,1 negli ambienti.</span><span class="sxs-lookup"><span data-stu-id="62d96-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="62d96-117">Microsoft ha prodotto un white paper su TLS disponibile [qui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e consigliamo anche la lettura in background disponibile in questo [Blog di Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="62d96-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="62d96-118">Ambito di supporto</span><span class="sxs-lookup"><span data-stu-id="62d96-118">Supportability Scope</span></span>

<span data-ttu-id="62d96-119">L' *ambito* si riferisce ai limiti di supporto.</span><span class="sxs-lookup"><span data-stu-id="62d96-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="62d96-120">I mezzi *completamente testati e supportati* supportano completamente e hanno testato la disabilitazione di TLS 1,0 e 1,1 per le versioni di prodotto elencate.</span><span class="sxs-lookup"><span data-stu-id="62d96-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="62d96-121">*Attualmente in fase di analisi* significa solo questo; Stiamo esaminando attivamente l'opportunità di portare questi prodotti nell'ambito del supporto per disabilitare TLS.</span><span class="sxs-lookup"><span data-stu-id="62d96-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="62d96-122">*Fuori ambito* significa che queste versioni di prodotto non supportano la disabilitazione di TLS 1,0 o 1,1 e non funzionano, con le eccezioni note.</span><span class="sxs-lookup"><span data-stu-id="62d96-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="62d96-123">Server completamente testati e supportati</span><span class="sxs-lookup"><span data-stu-id="62d96-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="62d96-124">Skype for Business Server 2019 CU1 17.0.2046.123 (giugno 2019) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="62d96-125">Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versione successiva in Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo), 2012 R2 o 2016.</span><span class="sxs-lookup"><span data-stu-id="62d96-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="62d96-126">Sul posto è stato aggiornato Skype for Business Server 2015, con CU9 6.0.9319.548 (maggio 2019) o versioni successive in Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo) o 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="62d96-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="62d96-127">Connettività di Exchange e Outlook Web App con Exchange Server 2010 SP3 RU19 o versioni successive, indicazioni [qui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="62d96-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="62d96-128">Survivable Branch Appliance (SBA) con Skype for Business Server 2015 CU6 HF2 o versioni successive (confermare con il fornitore che ha immesso gli aggiornamenti di giuste e che sono stati resi disponibili per l'appliance)</span><span class="sxs-lookup"><span data-stu-id="62d96-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="62d96-129">Survivable Branch Server (SBS) con Skype for Business Server 2015 CU6 HF2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="62d96-130">**Solo ruolo Edge**di Lync Server 2013, perché il ruolo Edge non ha una dipendenza dal tessuto Windows 1,0.</span><span class="sxs-lookup"><span data-stu-id="62d96-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="62d96-131">Client completamente testati e supportati</span><span class="sxs-lookup"><span data-stu-id="62d96-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="62d96-132">Client desktop di Lync 2013 (Skype for business), MSI e C2R, inclusi i 15.0.5023.1000 di base [o versioni successive](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="62d96-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="62d96-133">Client desktop di Skype for business 2016, MSI [16.0.4678.1000 o versioni successive](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluso Basic</span><span class="sxs-lookup"><span data-stu-id="62d96-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="62d96-134">Skype for business 2016 fare clic su Esegui per richiedere gli aggiornamenti di [aprile 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="62d96-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="62d96-135">Mirati mensilmente e semestrale, 16\.0\.9126\.2152 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="62d96-136">Semi-annuale e Deferred Channel, 16\.0\.8431\.2242 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="62d96-137">Skype for business per Mac 16,15 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="62d96-138">Skype for business per iOS e Android 6,19 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="62d96-139">Microsoft teams Rooms (precedentemente noto come Skype room System V2 SRS v2) 4.0.64.0 (2018 dicembre) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="62d96-140">Aggiornamento di Surface hub per Team Edition basato su KB4499162 (2019 maggio, Build 15063,1835 OS) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="62d96-141">Skype Web App 2015 CU6 HF2 o versioni successive (navi con Server)</span><span class="sxs-lookup"><span data-stu-id="62d96-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="62d96-142">Attualmente in fase di analisi</span><span class="sxs-lookup"><span data-stu-id="62d96-142">Currently being investigated</span></span>

- <span data-ttu-id="62d96-143">Dashboard qualità chiamata (nuova installazione dopo la disattivazione di TLS 1,0, 1,1, vedere di seguito) \*</span><span class="sxs-lookup"><span data-stu-id="62d96-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="62d96-144">Fuori ambito</span><span class="sxs-lookup"><span data-stu-id="62d96-144">Out of scope</span></span>

<span data-ttu-id="62d96-145">Eccetto dove indicato, i prodotti seguenti non sono nell'ambito del supporto di Disabilitazione TLS 1.0/1.1 e non funzioneranno in un ambiente in cui TLS 1,0 e 1,1 sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="62d96-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="62d96-146">Significato: se si usano ancora server o client fuori ambito, è necessario aggiornarli o rimuoverli se è necessario disabilitare TLS 1.0/1.1 in qualsiasi punto della distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="62d96-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="62d96-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d96-147">Lync Server 2013</span></span>
- <span data-ttu-id="62d96-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="62d96-148">Lync Server 2010</span></span>
- <span data-ttu-id="62d96-149">Windows Server 2008 o inferiore</span><span class="sxs-lookup"><span data-stu-id="62d96-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="62d96-150">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="62d96-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="62d96-151">Lync 2013 per dispositivi mobili-iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="62d96-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="62d96-152">Client di Windows Store "MX" di Lync</span><span class="sxs-lookup"><span data-stu-id="62d96-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="62d96-153">Lync room System (alias</span><span class="sxs-lookup"><span data-stu-id="62d96-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="62d96-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="62d96-154">SRSv1).</span></span> <span data-ttu-id="62d96-155">LRS ha raggiunto la fine del supporto il 9 ottobre 2018 e non verrà aggiornato per supportare TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="62d96-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="62d96-156">Tutti i client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="62d96-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="62d96-157">Lync Phone Edition-istruzioni aggiornate [qui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="62d96-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="62d96-158">2013 basato su Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="62d96-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="62d96-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="62d96-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="62d96-160">Skype for business per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="62d96-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="62d96-161">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="62d96-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="62d96-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d96-162">Lync Server 2013</span></span>

<span data-ttu-id="62d96-163">Lync Server 2013 assume una dipendenza da Windows Fabric versione 1,0.</span><span class="sxs-lookup"><span data-stu-id="62d96-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="62d96-164">In fase di progettazione per Lync Server 2013, Windows Fabric 1,0 è stato scelto per la sua convincente e nuova architettura distribuita per consentire la replica, la disponibilità elevata e la tolleranza di errore.</span><span class="sxs-lookup"><span data-stu-id="62d96-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="62d96-165">Nel corso del tempo, sia Skype for Business Server che Windows Fabric hanno notevolmente migliorato questa architettura comune con una riprogettazione significativa nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="62d96-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="62d96-166">Il server Skype for business 2015 corrente usa il tessuto Windows 3,0, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="62d96-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="62d96-167">Purtroppo, Windows Fabric 1,0 non **supporta TLS 1,2.  Verrà tuttavia aggiornato Lync Server 2013 per l'utilizzo con TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="62d96-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="62d96-168">Verrà disponibile il prossimo aggiornamento cumulativo per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62d96-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="62d96-169">Stiamo fornendo il supporto di TLS 1,2 per consentire la coesistenza, la migrazione, la Federazione e gli scenari ibridi.</span><span class="sxs-lookup"><span data-stu-id="62d96-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="62d96-170">Se è necessaria l'organizzazione per disabilitare TLS 1,0 e 1,1 e attualmente si usa Lync Server 2013, è consigliabile iniziare il processo di pianificazione, con la possibilità di eseguire l'aggiornamento sul posto o la migrazione affiancata (nuovi pool, spostare gli utenti) in Skype for Business Server 2015 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="62d96-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="62d96-171">In alternativa, puoi accelerare la migrazione a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="62d96-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="62d96-172">Dashboard qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="62d96-172">Call Quality Dashboard</span></span>

<span data-ttu-id="62d96-173">Il dashboard di qualità delle chiamate locali ha attualmente una dipendenza da TLS 1,0 durante la nuova installazione (prima volta che si installa in ambienti locali).</span><span class="sxs-lookup"><span data-stu-id="62d96-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="62d96-174">Stiamo attualmente esaminando il problema e intendiamo rilasciare una correzione in un prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="62d96-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="62d96-175">Se si prevede di installare Call Quality dashboard e disabilitare anche TLS 1,0, è consigliabile completare prima di tutto l'installazione di Call Quality dashboard e quindi procedere con la disabilitazione di TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="62d96-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="62d96-176">Dispositivi di terze parti</span><span class="sxs-lookup"><span data-stu-id="62d96-176">Third-party devices</span></span>

<span data-ttu-id="62d96-177">Nei dispositivi di terze parti, ad esempio telefoni 3PIP, videoconferenze, proxy inverso e servizi di bilanciamento del carico, assicurarsi di convalidare la supportabilità di TLS 1,2, verificare attentamente e contattare il fornitore, se necessario.</span><span class="sxs-lookup"><span data-stu-id="62d96-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="62d96-178">Considerazioni sulla Federazione quando si disabilita TLS 1.0/1.1 in Edge Server</span><span class="sxs-lookup"><span data-stu-id="62d96-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="62d96-179">È necessario pianificare attentamente e valutare l'impatto della disabilitazione di TLS 1.0/1.1 nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="62d96-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="62d96-180">Dopo aver disabilitato TLS 1,0 e 1,1, è possibile che altre organizzazioni non siano più in grado di eseguire la Federazione con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="62d96-181">Si può scegliere di mantenere TLS 1.0/1.1 abilitato in Edge Server per mantenere la compatibilità con le versioni precedenti di sistemi esterni (SfB 2015, Lync 2013) o versioni precedenti (2010).</span><span class="sxs-lookup"><span data-stu-id="62d96-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="62d96-182">Microsoft non è in grado di fornire consigli o raccomandazioni per verificare se la rete Edge (o qualsiasi rete) rientra in standard PCI; Questo deve essere determinato dalla singola società.</span><span class="sxs-lookup"><span data-stu-id="62d96-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="62d96-183">Skype for business online è attualmente in grado di TLS 1,2, quindi non è previsto alcun impatto sull'ibrido/Federazione con online.</span><span class="sxs-lookup"><span data-stu-id="62d96-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="62d96-184">PIC (connettività per messaggistica istantanea pubblica) a Skype Consumer Service: non prevediamo la disabilitazione di TLS 1.0/1.1 per l'impatto della [connettività Skype](../../deploy/deploy-skype-connectivity.md); I gateway Microsoft PIC sono già in grado di TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="62d96-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="62d96-185">Prerequisiti e processi</span><span class="sxs-lookup"><span data-stu-id="62d96-185">Prerequisites and process</span></span>

<span data-ttu-id="62d96-186">Eccetto dove indicato sopra, una volta che i server TLS 1,0 e 1,1 sono disabilitati, i client e i dispositivi non verranno più funzionanti correttamente o a tutti.</span><span class="sxs-lookup"><span data-stu-id="62d96-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="62d96-187">Ciò significa che è necessario sospendere e attendere le indicazioni aggiornate da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62d96-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="62d96-188">Quando si è soddisfatti di soddisfare tutti i requisiti e si ha un piano per affrontare le lacune, procedere.</span><span class="sxs-lookup"><span data-stu-id="62d96-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="62d96-189">Ad alto livello, mentre Skype for Business Server 2019 è pronto per la procedura di installazione, Skype for Business Server 2015 richiederà di installare CU9, applicando gli aggiornamenti prerequisiti a .NET e SQL, distribuendo le chiavi del registro di sistema e infine un separato ciclo di aggiornamenti della configurazione del sistema operativo (ad esempio disabilitazione di TLS 1,0 e 1,1 tramite l'importazione di file del registro).</span><span class="sxs-lookup"><span data-stu-id="62d96-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="62d96-190">È fondamentale completare l'installazione di tutti i prerequisiti, incluso Skype for Business Server 2015 CU6 HF2, prima della disabilitazione di TLS 1,0 e 1,1 in qualsiasi server dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="62d96-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="62d96-191">Ogni server Skype for business, inclusi i backend per il ruolo Edge e SQL, richiede gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="62d96-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="62d96-192">Verificare inoltre che tutti i client supportati (in ambito) siano stati aggiornati alle versioni minime richieste.</span><span class="sxs-lookup"><span data-stu-id="62d96-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="62d96-193">Non dimenticare di aggiornare anche le workstation di gestione.</span><span class="sxs-lookup"><span data-stu-id="62d96-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="62d96-194">Vogliamo seguire l'ordine usuale delle operazioni di "Inside out" per l'aggiornamento dei server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="62d96-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="62d96-195">Trattare i pool di Director, la chat persistente e i pool di coppie nello stesso modo in cui si farebbe normalmente.</span><span class="sxs-lookup"><span data-stu-id="62d96-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="62d96-196">L'ordine e i metodi per l'aggiornamento sono coperti [qui](topology.md) e [qui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="62d96-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="62d96-197">Processo di alto livello</span><span class="sxs-lookup"><span data-stu-id="62d96-197">High-level process</span></span>

1. <span data-ttu-id="62d96-198">Testare tutti i passaggi del Lab prima di configurare i server di produzione.</span><span class="sxs-lookup"><span data-stu-id="62d96-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="62d96-199">Eseguire il backup e mantenere una copia del registro di sistema esportato su ogni singolo server da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="62d96-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="62d96-200">Non è possibile condividere i registri tra server, contengono chiavi esclusive basate su computer.</span><span class="sxs-lookup"><span data-stu-id="62d96-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="62d96-201">Aggiornare tutti i server di Skype for business 2015 in CU9 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="62d96-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="62d96-202">Per Skype for Business Server 2019, eseguire l'aggiornamento a CU1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="62d96-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="62d96-203">Installare tutti i prerequisiti per tutti i server.</span><span class="sxs-lookup"><span data-stu-id="62d96-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="62d96-204">Distribuire le chiavi del registro di sistema prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="62d96-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="62d96-205">Assicurarsi che tutti i client in ambito vengano aggiornati.</span><span class="sxs-lookup"><span data-stu-id="62d96-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="62d96-206">Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="62d96-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="62d96-207">Verificare che i carichi di lavoro funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="62d96-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="62d96-208">Se vengono rilevati problemi, risoluzione dei problemi e Risolvi o</span><span class="sxs-lookup"><span data-stu-id="62d96-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="62d96-209">Ripristinare il registro di sistema dal passaggio 2 per riattivare TLS 1,0 e 1,1</span><span class="sxs-lookup"><span data-stu-id="62d96-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="62d96-210">Verificare che venga usato solo TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="62d96-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="62d96-211">Installare prerequisiti per tutti i server</span><span class="sxs-lookup"><span data-stu-id="62d96-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="62d96-212">È necessario un ampio aggiornamento delle dipendenze prima di iniziare a disabilitare TLS 1,0 e 1,1 a livello di sistema operativo nelle distribuzioni di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="62d96-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="62d96-213">Di seguito sono riportate le versioni minime in grado di supportare TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="62d96-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="62d96-214">Distribuire tutti gli aggiornamenti dei prerequisiti in ogni server Skype for business nell'ambiente prima di iniziare a disabilitare TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="62d96-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="62d96-215">Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="62d96-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o versione successiva con SchUseStrongCrypto abilitato nel registro di sistema (disponibile di seguito)</span><span class="sxs-lookup"><span data-stu-id="62d96-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="62d96-217">SQL deve essere aggiornato in tutti i server e i backend di Skype for business 2015.</span><span class="sxs-lookup"><span data-stu-id="62d96-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="62d96-218">Aggiornare i backend SQL per il pool di Enterprise Edition prima di tutto, quindi i rispettivi FEs.</span><span class="sxs-lookup"><span data-stu-id="62d96-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="62d96-219">SQL Server 2014 SP1 + CU5 ([collegamento](https://support.microsoft.com/help/3130926)) o superiore/sql Server 2012 SP2 + CU16 o superiore/sql Server 2014 RTM + CU12 ([collegamento](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) o superiore/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="62d96-219">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
     - <span data-ttu-id="62d96-220">SQL Server Native Client per SQL Server 2012 ([collegamento](https://www.microsoft.com/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="62d96-220">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/download/details.aspx?id=50402))</span></span>
     - <span data-ttu-id="62d96-221">Driver Microsoft ODBC 11 per SQL Server ([collegamento](https://www.microsoft.com/download/details.aspx?id=36434)) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="62d96-221">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/download/details.aspx?id=36434)), or higher</span></span>
     - <span data-ttu-id="62d96-222">Oggetti di gestione condivisi per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="62d96-222">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))</span></span>
     - <span data-ttu-id="62d96-223">SQLSysClrTypes per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="62d96-223">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="62d96-224">Procedura di base per installare i prerequisiti, in ordine delle operazioni consigliato</span><span class="sxs-lookup"><span data-stu-id="62d96-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="62d96-225">Installare l'aggiornamento di CU9 per Skype for Business Server in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="62d96-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="62d96-226">Installare l'aggiornamento ai componenti usando l'Updater.</span><span class="sxs-lookup"><span data-stu-id="62d96-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="62d96-227">Aggiornare i database in base alle procedure documentate.</span><span class="sxs-lookup"><span data-stu-id="62d96-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="62d96-228">Per Skype for Business Server 2015, vedere KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="62d96-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="62d96-229">Convalidare la funzionalità prodotto nella distribuzione prima di procedere con altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="62d96-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="62d96-230">Scarica il programma di installazione offline di .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="62d96-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="62d96-231">Riferimento[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="62d96-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="62d96-232">Assicurarsi che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="62d96-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="62d96-233">Riferimento[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="62d96-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="62d96-234">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="62d96-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="62d96-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="62d96-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="62d96-236">Eseguire il pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-236">Run the installer package.</span></span>
    7. <span data-ttu-id="62d96-237">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="62d96-237">Reboot the server.</span></span>
3. <span data-ttu-id="62d96-238">Aggiornare SQL Express 2014 in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="62d96-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="62d96-239">Riferimento[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="62d96-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="62d96-240">Scaricare SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="62d96-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="62d96-241">Riferimento[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="62d96-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="62d96-242">Copiare il supporto di installazione in una cartella nel server (ad esempio: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="62d96-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="62d96-243">Verificare che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end</span><span class="sxs-lookup"><span data-stu-id="62d96-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="62d96-244">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="62d96-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="62d96-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="62d96-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="62d96-246">Aprire un prompt dei comandi di amministrazione e aggiornare tutti i componenti e le istanze installati</span><span class="sxs-lookup"><span data-stu-id="62d96-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="62d96-247">Esempio: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="62d96-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="62d96-248">Aggiornare SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="62d96-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="62d96-249">Riferimento: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="62d96-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="62d96-250">Scarica da[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="62d96-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="62d96-251">Verificare che i servizi di 2015 di Skype for Business Server vengano arrestati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="62d96-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="62d96-252">Ex (Standard Edition):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="62d96-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="62d96-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="62d96-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="62d96-254">Arrestare l'installazione delle istanze di SQL in uso</span><span class="sxs-lookup"><span data-stu-id="62d96-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="62d96-255">Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="62d96-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="62d96-256">Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="62d96-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="62d96-257">Ex (solo Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="62d96-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="62d96-258">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="62d96-258">Install the update.</span></span>
5. <span data-ttu-id="62d96-259">Aggiornare il driver ODBC 11 per SQL Server per includere il supporto per TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="62d96-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="62d96-260">Scaricare il [driver ODBC 11 per SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="62d96-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="62d96-261">Assicurarsi che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="62d96-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="62d96-262">Esempio (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="62d96-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="62d96-263">Esempio (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="62d96-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="62d96-264">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="62d96-264">Install the update.</span></span>
6. <span data-ttu-id="62d96-265">Distribuire le chiavi del registro di sistema prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="62d96-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="62d96-266">Chiavi del registro di sistema pre-richieste</span><span class="sxs-lookup"><span data-stu-id="62d96-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="62d96-267">Copiare/incollare il test seguente in blocco note e rinominare TLSPreReq. reg o un nome a scelta, quindi importare:</span><span class="sxs-lookup"><span data-stu-id="62d96-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="62d96-268">Per i backend SQL per i pool Enterprise, i prerequisiti e la Disabilitazione TLS devono essere trattati come qualsiasi aggiornamento di SQL o OS; vedere:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="62d96-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="62d96-269">Mentre è possibile combinare sia la procedura per la disabilitazione dell'applicazione prerequisito che quella TLS, consigliamo vivamente di applicare tutti i prerequisiti prima di procedere con la disabilitazione di TLS 1,0 e 1,1 a livello di sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="62d96-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="62d96-270">L'approccio per la procedura consigliata consiste nel preparare l'ambiente distribuendo tutti i prerequisiti, convalidando che tutti i carichi di lavoro funzionino correttamente e come previsto e quindi procedendo con la Disabilitazione TLS 1.0/1.1 in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="62d96-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="62d96-271">Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema</span><span class="sxs-lookup"><span data-stu-id="62d96-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="62d96-272">Prima di procedere con i passaggi successivi, verificare di *aver completato tutti i prerequisiti e i server Skype for business aggiornati*.</span><span class="sxs-lookup"><span data-stu-id="62d96-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="62d96-273">Copiare il testo seguente in un file di blocco note e rinominarlo **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="62d96-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="62d96-274">Importare il file con estensione reg in ogni server che si vuole disabilitare TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="62d96-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="62d96-275">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="62d96-275">Reboot the server.</span></span> <span data-ttu-id="62d96-276">Dopo che i servizi sono tornati online, passare al server successivo.</span><span class="sxs-lookup"><span data-stu-id="62d96-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="62d96-277">L'approccio per i pool Enterprise Edition è lo stesso che si può fare per qualsiasi aggiornamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="62d96-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="62d96-278">Potresti aver notato che stiamo facendo molto di più che disabilitare solo TLS 1,0 e 1,1 qui.</span><span class="sxs-lookup"><span data-stu-id="62d96-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="62d96-279">Stiamo supportando il riordino di Cipher Suite (come illustrato sopra) e la disattivazione di alcuni cifrari deboli meno recenti.</span><span class="sxs-lookup"><span data-stu-id="62d96-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="62d96-280">Questa è la prima volta che abbiamo ufficialmente supportato queste modifiche all'API SCHANNEL e Crypto in Skype for Business Server ed è importante notare che queste modifiche sono le uniche supportate e testate in questo momento.</span><span class="sxs-lookup"><span data-stu-id="62d96-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="62d96-281">Potremmo prendere in considerazione altre configurazioni in futuro, ma per il momento, non modificare il file di importazione del registro di sistema nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="62d96-282">Verificare che i carichi di lavoro funzionino come previsto</span><span class="sxs-lookup"><span data-stu-id="62d96-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="62d96-283">Dopo aver disabilitato TLS 1,0 e 1,1 nell'ambiente, verificare che tutti i carichi di lavoro principali funzionino come previsto, ad esempio messaggistica istantanea & presenza, chiamate P2P, VoIP aziendale e così via.</span><span class="sxs-lookup"><span data-stu-id="62d96-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="62d96-284">**Convalidare solo TLS 1,2 viene usato**</span><span class="sxs-lookup"><span data-stu-id="62d96-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="62d96-285">Fai in modo che il tuo team di sicurezza esegua un nuovo controllo del traffico Skype for business per assicurarti che i protocolli meno recenti TLS 1,0 e 1,1 non siano più in uso.</span><span class="sxs-lookup"><span data-stu-id="62d96-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="62d96-286">In alternativa, è possibile usare Internet Explorer per testare le connessioni TLS ai servizi Web da Skype for Business Server 2015 dopo la disattivazione di TLS 1,0 e TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="62d96-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="62d96-287">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="62d96-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="62d96-288">Selezionare **strumenti** > **Internet Options**.</span><span class="sxs-lookup"><span data-stu-id="62d96-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="62d96-289">Selezionare la scheda **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="62d96-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="62d96-290">In **Impostazioni**scorrere fino alla fine.</span><span class="sxs-lookup"><span data-stu-id="62d96-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="62d96-291">Verificare che TLS 1,0, TLS 1,1 e TLS 1,2 siano abilitati.</span><span class="sxs-lookup"><span data-stu-id="62d96-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="62d96-292">Esplorare l'URL del servizio Web interno del pool di SfB 2015 (deve connettersi correttamente).</span><span class="sxs-lookup"><span data-stu-id="62d96-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="62d96-293">Tornare in Internet Explorer e disabilitare l'opzione per l' **uso solo di TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="62d96-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="62d96-294">Esplorare di nuovo l'URL del servizio Web interno del pool di SfB 2015 (non riesce a connettersi).</span><span class="sxs-lookup"><span data-stu-id="62d96-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opzioni Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="62d96-296">Scenari di distribuzione avanzati</span><span class="sxs-lookup"><span data-stu-id="62d96-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="62d96-297">Poiché sono necessari alcuni prerequisiti di dipendenza per supportare TLS 1,2 in Skype for business ser 2015, l'installazione da supporto RTM non riesce in qualsiasi sistema in cui TLS 1,0 e 1,1 sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="62d96-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="62d96-298">**Distribuzione di nuovi server Standard Edition o pool di Enterprise Edition dopo la disattivazione di TLS 1,0 e 1,1 nell'ambiente.**</span><span class="sxs-lookup"><span data-stu-id="62d96-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="62d96-299">**Opzione 1:** Usare [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="62d96-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="62d96-300">Tieni presente che stiamo aggiornando SmartSetup per adattare i file binari SQL aggiornati in un futuro CU e aggiorniamo questo articolo in futuro.</span><span class="sxs-lookup"><span data-stu-id="62d96-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="62d96-301">**Opzione 2:** Pre-installare istanze locali di SQL (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="62d96-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="62d96-302">Scaricare e copiare SQL Express 2014 SP2 (SQLEXPR_x64. exe) nella cartella locale in FE.</span><span class="sxs-lookup"><span data-stu-id="62d96-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="62d96-303">Supponiamo che il percorso della cartella <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="62d96-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="62d96-304">Avviare PowerShell o prompt dei comandi e passare a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="62d96-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="62d96-305">Creare l'istanza di SQL RTCLOCAL eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="62d96-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="62d96-306">Attendere che SQLEXPR_x64. exe finisca prima di procedere:</span><span class="sxs-lookup"><span data-stu-id="62d96-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="62d96-307">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="62d96-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="62d96-308">Creare l'istanza di SQL LYNCLOCAL eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="62d96-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="62d96-309">Attendere che SQLEXPR_x64. exe finisca prima di procedere con il passaggio successivo:</span><span class="sxs-lookup"><span data-stu-id="62d96-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="62d96-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="62d96-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="62d96-311">Eseguire la configurazione RTM di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="62d96-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="62d96-312">Seguire i passaggi rimanenti della sezione Prerequisiti precedente.</span><span class="sxs-lookup"><span data-stu-id="62d96-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="62d96-313">**Opzione 3:** È anche possibile sostituire manualmente i file binari in una directory multimediale di installazione locale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="62d96-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="62d96-314">Installare prerequisiti per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="62d96-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="62d96-315">Installare .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="62d96-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="62d96-316">**Nota:** Per la prima volta è stato introdotto il supporto per .NET 4,7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="62d96-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="62d96-317">Pertanto, nei passaggi successivi di seguito verranno aggiornati i componenti principali prima dell'installazione principale.</span><span class="sxs-lookup"><span data-stu-id="62d96-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="62d96-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="62d96-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="62d96-319">Riferimento: [software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="62d96-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="62d96-320">Copiare file/cartelle ISO:</span><span class="sxs-lookup"><span data-stu-id="62d96-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="62d96-321">Con l'ISO di Skype for Business Server 2015 allegato, aprire la directory radice dell'unità in cui è collegata (es: D:\) in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="62d96-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="62d96-322">Copiare tutte le cartelle e i file in una cartella in un disco locale (es: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="62d96-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="62d96-323">**Nota:** Prima di installare i componenti, sarà necessario aggiornare alcuni file per il supporto di TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="62d96-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="62d96-324">Sostituire i pacchetti MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="62d96-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="62d96-325">Sostituire i pacchetti MSI e EXE esistenti nella cartella/Setup/amd64/del supporto di installazione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="62d96-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="62d96-326">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="62d96-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="62d96-327">Rinominare in SQLEXPR_x64 nel computer locale e sostituire il file esistente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="62d96-328">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="62d96-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="62d96-329">**Nota:** Rinominare questo elemento, se necessario, in sqlncli. msi e quindi sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="62d96-330">Oggetti di gestione SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="62d96-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="62d96-331">**Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati.</span><span class="sxs-lookup"><span data-stu-id="62d96-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="62d96-332">Selezionare questa pagina per scaricare solo SharedManagementObjects. msi.</span><span class="sxs-lookup"><span data-stu-id="62d96-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="62d96-333">**Nota:** Sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="62d96-334">Tipi CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="62d96-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="62d96-335">**Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati.</span><span class="sxs-lookup"><span data-stu-id="62d96-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="62d96-336">Selezionare per scaricare solo CQLSysClrTypes. msi</span><span class="sxs-lookup"><span data-stu-id="62d96-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="62d96-337">**Nota**: sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="62d96-338">Installare componenti principali:</span><span class="sxs-lookup"><span data-stu-id="62d96-338">Install Core Components:</span></span> 
    - <span data-ttu-id="62d96-339">Eseguire Setup. exe dalla cartella Setup/amd64/del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="62d96-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="62d96-340">Seguire le istruzioni per installare i componenti principali</span><span class="sxs-lookup"><span data-stu-id="62d96-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="62d96-341">Chiudere i componenti principali.</span><span class="sxs-lookup"><span data-stu-id="62d96-341">Close Core Components.</span></span>
6. <span data-ttu-id="62d96-342">Aggiornare i componenti principali:</span><span class="sxs-lookup"><span data-stu-id="62d96-342">Update Core Components:</span></span> 
    - <span data-ttu-id="62d96-343">Scaricare il programma di installazione di Skype for Business Update.</span><span class="sxs-lookup"><span data-stu-id="62d96-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="62d96-344">Eseguire il programma di installazione per aggiornare i componenti principali e installare i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="62d96-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="62d96-345">**Nota:** A partire dal rilascio di CU6HF2, la caratteristica di aggiornamento automatico attualmente viene installata solo fino a CU6.</span><span class="sxs-lookup"><span data-stu-id="62d96-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="62d96-346">Di conseguenza, l'Updater deve essere eseguito separatamente per aggiornare i componenti principali in 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="62d96-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="62d96-347">Riferimentohttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="62d96-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="62d96-348">Installare strumenti amministrativi (facoltativo):</span><span class="sxs-lookup"><span data-stu-id="62d96-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="62d96-349">In questo modo verranno installati Microsoft SQL Server 2012 Native client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types per SQL Server 2014 (x64) con i file aggiornati.</span><span class="sxs-lookup"><span data-stu-id="62d96-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="62d96-350">Inoltre, il generatore di topologie e il pannello di controllo di Skype for Business Server 2015 saranno disponibili nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="62d96-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="62d96-351">Installare lo Store di configurazione locale (passaggio 1):</span><span class="sxs-lookup"><span data-stu-id="62d96-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="62d96-352">Aprire la distribuzione guidata, fare clic su Installa o Aggiorna Skype for Business Server System, quindi fare clic su **Esegui** al passaggio 1: installare l'archivio configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="62d96-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="62d96-353">Fare clic su **Avanti** nella finestra di dialogo **Installa archivio configurazione locale** .</span><span class="sxs-lookup"><span data-stu-id="62d96-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="62d96-354">![Finestra di dialogo Installa archivio configurazione locale](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="62d96-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="62d96-355">Esaminare i risultati e verificare che lo stato dell'attività sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="62d96-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="62d96-356">Esaminare il file di log risultante facendo clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="62d96-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="62d96-357">![Lo stato delle attività viene visualizzato come completato](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="62d96-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="62d96-358">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="62d96-358">Click **Finish**.</span></span>
9. <span data-ttu-id="62d96-359">Configurare o rimuovere componenti di Skype for Business Server (passaggio 2):</span><span class="sxs-lookup"><span data-stu-id="62d96-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="62d96-360">Aprire la distribuzione guidata, fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Esegui** al passaggio 2: configurare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="62d96-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="62d96-361">Fare clic su **Avanti** nella finestra di dialogo Configura componenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="62d96-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="62d96-362">![finestra Configura componenti di Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="62d96-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="62d96-363">Rivedere il log usando il log della visualizzazione e verificare che il programma di installazione sia stato completato senza problemi.</span><span class="sxs-lookup"><span data-stu-id="62d96-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="62d96-364">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="62d96-364">Click **Finish**.</span></span>
10. <span data-ttu-id="62d96-365">Procedere con l'installazione e la configurazione aggiuntive necessarie (è possibile riprendere le normali procedure di installazione a questo punto).</span><span class="sxs-lookup"><span data-stu-id="62d96-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
