---
title: 'Lync Server 2013: Definizione dei requisiti per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="b4a7f-102">Definizione dei requisiti per dispositivi mobili per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a7f-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b4a7f-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="b4a7f-104">Durante la fase di pianificazione della funzionalità di mobilità di Lync Server 2013, quando si usano client mobili Lync 2010 mobile e Lync 2013, è possibile prendere decisioni che determinano la procedura di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="b4a7f-105">Ecco le decisioni che devi prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="b4a7f-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="b4a7f-106">**Si vuole usare l'individuazione automatica per i client mobili Lync?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="b4a7f-107">Se si vuole supportare l'individuazione automatica, è necessario creare nuovi record DNS (Domain Name System) interni ed esterni, aggiungere nomi alternativi soggetti ai certificati nei server front-end, direttori e proxy inverso e modificare le regole di pubblicazione esistenti. nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="b4a7f-108">Per informazioni dettagliate, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="b4a7f-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="b4a7f-109">Con l'individuazione automatica, gli utenti possono individuare automaticamente i servizi Web di Lync Server 2013 ovunque all'interno o all'esterno della rete aziendale, senza immettere URL nelle impostazioni del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="b4a7f-110">Se si usano le impostazioni manuali anziché l'individuazione automatica, gli utenti mobili devono immettere manualmente gli URL seguenti nei propri dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="b4a7f-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="b4a7f-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="b4a7f-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="b4a7f-112">https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice. svc/root per l'accesso interno</span><span class="sxs-lookup"><span data-stu-id="b4a7f-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="b4a7f-113">Ti consigliamo vivamente di usare l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-113">We strongly recommend using automatic discovery.</span></span> <span data-ttu-id="b4a7f-114">L'uso principale delle impostazioni manuali è per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-114">The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="b4a7f-115">**Se si decide di supportare l'individuazione automatica, si è disposti ad aggiornare i certificati nel proxy inverso con i nomi alternativi oggetto per ogni dominio SIP?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="b4a7f-116">Se si hanno molti domini SIP, l'aggiornamento dei certificati pubblici al proxy inverso può diventare molto costoso.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="b4a7f-117">In questo caso, puoi scegliere di implementare il rilevamento automatico in modo che la richiesta di servizio di individuazione automatica usi HTTP sulla porta 80, invece di usare HTTPS sulla porta 443.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="b4a7f-118">Tuttavia, questo non è l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="b4a7f-119">Se si decide di scegliere questa alternativa, non è necessario aggiornare i certificati nel proxy inverso, ma è necessario creare una regola di pubblicazione Web per HTTP sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="b4a7f-120">Per altri dettagli, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="b4a7f-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="b4a7f-121">**Si desidera supportare i client di Lync mobile sia interni che esterni alla rete aziendale o supportare i client solo all'interno della rete aziendale?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="b4a7f-122">Se si vuole supportare i client mobili interni ed esterni alla rete, i dispositivi mobili possono accedere alle caratteristiche di mobilità da qualsiasi posizione.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-122">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location.</span></span> <span data-ttu-id="b4a7f-123">La configurazione predefinita consiste nel supportare i client interni ed esterni alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-123">The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="b4a7f-124">Anche se la configurazione predefinita consente al traffico client mobile di passare attraverso il sito esterno, è possibile limitare il traffico client per dispositivi mobili alla rete aziendale interna.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="b4a7f-125">Quando si limita il traffico alla rete interna, gli utenti possono usare le applicazioni mobili di Lync nei propri dispositivi mobili solo quando si trovano all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="b4a7f-126">Per le distribuzioni che supportano la mobilità tramite il servizio di mobilità MCX e Lync 2010 mobile, è possibile eseguire il cmdlet **Set-CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b4a7f-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="b4a7f-127">Per impostare la mobilità solo per uso interno, è possibile usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b4a7f-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a7f-128">Non sono necessarie altre configurazioni per UCWA.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="b4a7f-129">UCWA non ha una configurazione solo interna equivalente.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b4a7f-130">Se si usa un server front-end&nbsp;di lync Server 2013 o i pool Front-end e <STRONG>non si dispone</STRONG> di server&nbsp;front end o pool front-end di Lync Server 2010, non <STRONG>è necessario alcun requisito di persistenza basato su cookie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="b4a7f-131">Se è necessario mantenere tutti i server front end&nbsp;o i pool Front End di lync Server 2010, le stesse regole si applicano ancora come in Lync Server 2010 per la persistenza basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="b4a7f-132">**Si desidera supportare le notifiche push per i dispositivi Apple iOS e i telefoni Windows?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="b4a7f-133">Se si supportano le notifiche push, i dispositivi iOS Apple supportati e i telefoni Windows ricevono una notifica degli eventi che si verificano quando l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="b4a7f-134">È necessario configurare l'Edge Server per avere una relazione federativa con il servizio di notifica push di Lync Server basato su cloud, disponibile nel centro dati di Lync Online, ed eseguire un cmdlet per abilitare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="b4a7f-135">Se si vuole supportare le notifiche push tramite la rete Wi-Fi, oltre a supportare le notifiche push tramite le reti 3G o dati dei provider di dispositivi mobili, è necessario aprire la porta 5223 in uscita nella rete Wi-Fi aziendale.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="b4a7f-136">Il supporto delle notifiche push tramite la rete Wi-Fi supporta i dispositivi mobili che usano solo Wi-Fi e dispositivi mobili con scarsa ricezione interna.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b4a7f-137">La porta di apertura TCP 5223 è necessaria solo quando si supportano dispositivi Apple che gestiscono il client mobile Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="b4a7f-138">Se non si supportano le notifiche push, gli utenti dei dispositivi mobili Apple e i telefoni Windows non informano sugli eventi, ad esempio gli inviti di messaggi istantanei o i messaggi persi, che si verificano quando l'applicazione per dispositivi mobili non è attiva.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a7f-139">I client mobili Lync 2013 nei dispositivi Apple non richiedono notifiche push.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="b4a7f-140">I client per dispositivi mobili Lync 2013 in Windows Phone usano la notifica push.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="b4a7f-141">La pianificazione della notifica push e la funzione di compensazione delle notifiche push rimangono le stesse per Lync Mobile su dispositivi Windows Phone e Apple che non sono in grado di eseguire il client per dispositivi mobili Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="b4a7f-142">**Si vuole consentire a tutti gli utenti di accedere alle caratteristiche di mobilità oppure si vuole essere in grado di specificare quali utenti hanno accesso a queste funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="b4a7f-143">La tabella descrive le funzionalità disponibili per gli utenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="b4a7f-144">Le impostazioni predefinite consentono la chiamata tramite lavoro, Consenti VoIP (Voice over IP) e Abilita mobilità.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="b4a7f-145">Ecco il set completo di opzioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="b4a7f-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="b4a7f-146">Caratteristica/nome parametro/ambito (i nomi dei parametri di criteri potrebbero non essere uguali)</span><span class="sxs-lookup"><span data-stu-id="b4a7f-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="b4a7f-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4a7f-147">Description</span></span></th>
    <th><span data-ttu-id="b4a7f-148">Introdotto</span><span class="sxs-lookup"><span data-stu-id="b4a7f-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="b4a7f-149">Abilitare la mobilità</span><span class="sxs-lookup"><span data-stu-id="b4a7f-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="b4a7f-150">Nome parametro:<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="b4a7f-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="b4a7f-151">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="b4a7f-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-152">Impostazione amministrativa per controllare gli utenti in un ambito specifico in cui è installato Lync mobile, se il criterio è impostato su false, l'utente non potrà accedere al client.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="b4a7f-153">L'impostazione predefinita è true.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-154">Aggiornamento cumulativo per Lync Server 2010: novembre 2011</span><span class="sxs-lookup"><span data-stu-id="b4a7f-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b4a7f-155">Abilitare la voce esterna</span><span class="sxs-lookup"><span data-stu-id="b4a7f-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="b4a7f-156">Nome parametro:<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="b4a7f-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="b4a7f-157">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="b4a7f-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-158">Controlla la possibilità di un utente di usare la chiamata tramite il lavoro, una caratteristica che consente agli utenti di effettuare e ricevere chiamate usando il loro numero di lavoro anziché il numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="b4a7f-159">Se impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate usando il proprio numero di lavoro dal dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="b4a7f-160">L'impostazione predefinita è true</span><span class="sxs-lookup"><span data-stu-id="b4a7f-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-161">Aggiornamento cumulativo per Lync Server 2010: novembre 2011</span><span class="sxs-lookup"><span data-stu-id="b4a7f-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b4a7f-162">Abilitare l'audio e il video IP</span><span class="sxs-lookup"><span data-stu-id="b4a7f-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="b4a7f-163">Nome parametro:<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="b4a7f-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="b4a7f-164">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="b4a7f-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-165">Controlla se un utente può usare il VoIP per effettuare o ricevere chiamate vocali o video nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="b4a7f-166">Se impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate VoIP o video sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="b4a7f-167">L'impostazione predefinita è true.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b4a7f-169">Richiedi Wi-Fi per l'audio IP</span><span class="sxs-lookup"><span data-stu-id="b4a7f-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="b4a7f-170">Nome parametro:<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="b4a7f-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="b4a7f-171">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="b4a7f-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-172">Questa impostazione definisce se il client verrà richiesto di effettuare e ricevere chiamate tramite VoIP su WiFi invece della rete dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="b4a7f-173">Se impostato su true, l'utente può effettuare e ricevere chiamate VoIP solo quando si è connessi a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="b4a7f-174">L'impostazione predefinita è false.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b4a7f-176">Richiedi Wi-Fi per IP video</span><span class="sxs-lookup"><span data-stu-id="b4a7f-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="b4a7f-177">Nome parametro:<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="b4a7f-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="b4a7f-178">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="b4a7f-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-179">Questa impostazione definisce se il client sarà necessario per effettuare e ricevere videochiamate su Wi-Fi anziché sulla rete di dati del cellulare.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="b4a7f-180">Se impostato su true, l'utente può effettuare e ricevere videochiamate solo quando si è connessi a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="b4a7f-181">L'impostazione predefinita è false.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="b4a7f-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="b4a7f-183">Per una descrizione delle impostazioni dei criteri che è possibile configurare e come gestire i criteri, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="b4a7f-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="b4a7f-184">**Si desidera che gli utenti che non sono abilitati per VoIP aziendale possano usare il comando fai clic per partecipare alle conferenze?**</span><span class="sxs-lookup"><span data-stu-id="b4a7f-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="b4a7f-185">Per consentire agli utenti di accedere alle caratteristiche di mobilità e chiamarle tramite lavoro, è necessario che siano abilitate per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="b4a7f-186">Tuttavia, gli utenti non abilitati per VoIP aziendale possono partecipare a conferenze facendo clic sul collegamento nel dispositivo mobile, se hanno un criterio vocale appropriato assegnato.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="b4a7f-187">È possibile assegnare un criterio vocale specifico a questi utenti o verificare che esista un criterio globale o dei criteri a livello di sito che si applicano a tali criteri.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="b4a7f-188">Il criterio vocale assegnato deve avere record di utilizzo PSTN (Public Switched Telephone Network) e route che definiscono le aree a cui gli utenti possono effettuare la chiamata per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="b4a7f-189">Per informazioni dettagliate sull'impostazione di criteri vocali, record di utilizzo PSTN e route, vedere [configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="b4a7f-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a7f-190">Gli utenti di dispositivi mobili che vogliono usare click to join richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, perché fare clic sul collegamento nel dispositivo mobile comporta una chiamata in uscita da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4a7f-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4a7f-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4a7f-191">See Also</span></span>


[<span data-ttu-id="b4a7f-192">Requisiti tecnici per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="b4a7f-193">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7f-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

