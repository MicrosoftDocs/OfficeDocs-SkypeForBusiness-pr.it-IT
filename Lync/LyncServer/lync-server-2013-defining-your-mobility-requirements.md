---
title: 'Lync Server 2013: definizione dei requisiti per dispositivi mobili'
description: 'Lync Server 2013: definizione dei requisiti per dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545542"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="6ab07-103">Definizione dei requisiti per dispositivi mobili per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-103">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab07-104">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="6ab07-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="6ab07-105">Durante la fase di pianificazione per la funzionalità di mobilità di Lync Server 2013, quando si utilizzano i client mobili Lync 2010 mobile e Lync 2013, è possibile prendere decisioni che determinano i passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6ab07-105">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="6ab07-106">Di seguito sono riportate le decisioni che è necessario prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="6ab07-106">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="6ab07-107">**Utilizzo dell'individuazione automatica per i client mobili di Lync**</span><span class="sxs-lookup"><span data-stu-id="6ab07-107">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="6ab07-108">Se si desidera supportare l'individuazione automatica, è necessario creare nuovi record DNS (Domain Name System) interni ed esterni, aggiungere nomi alternativi del soggetto ai certificati nei Front End Server, ai direttori e al proxy inverso e modificare le regole di pubblicazione esistenti sul proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6ab07-108">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="6ab07-109">Per informazioni dettagliate, vedere [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="6ab07-109">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="6ab07-110">Con l'individuazione automatica, gli utenti possono individuare automaticamente i servizi Web di Lync Server 2013 da qualsiasi posizione all'interno o all'esterno della rete aziendale, senza immettere gli URL nelle impostazioni dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="6ab07-110">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="6ab07-111">Se si utilizzano le impostazioni manuali invece dell'individuazione automatica, gli utenti mobili devono immettere manualmente gli URL seguenti nei propri dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="6ab07-111">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="6ab07-112">\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root https://per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6ab07-112">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="6ab07-113">https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice. svc/root per l'accesso interno</span><span class="sxs-lookup"><span data-stu-id="6ab07-113">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="6ab07-p102">È consigliabile utilizzare l'individuazione automatica. Le impostazioni manuali devono essere utilizzate principalmente per attività di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="6ab07-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="6ab07-116">**Se si decide di supportare l'individuazione automatica, aggiornamento dei certificati nel proxy inverso con nomi alternativi soggetto per ogni dominio SIP**</span><span class="sxs-lookup"><span data-stu-id="6ab07-116">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="6ab07-117">In presenza di numerosi domini SIP, l'aggiornamento dei certificati pubblici nel proxy inverso può diventare molto oneroso.</span><span class="sxs-lookup"><span data-stu-id="6ab07-117">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="6ab07-118">In caso affermativo, è possibile scegliere di implementare l'individuazione automatica in modo che la richiesta di servizio di Autodiscover iniziale utilizzi HTTP sulla porta 80, anziché utilizzare HTTPS sulla porta 443.</span><span class="sxs-lookup"><span data-stu-id="6ab07-118">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="6ab07-119">Tuttavia, questo non è l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="6ab07-119">However, this is not the recommended approach.</span></span> <span data-ttu-id="6ab07-120">Se si decide di scegliere questa alternativa, non è necessario aggiornare i certificati per il proxy inverso, ma è necessario creare una regola di pubblicazione Web per HTTP sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="6ab07-120">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="6ab07-121">Per ulteriori informazioni, vedere [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="6ab07-121">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="6ab07-122">**Supporto di client mobili di Lync sia all'interno che all'esterno della rete aziendale o solo all'interno**</span><span class="sxs-lookup"><span data-stu-id="6ab07-122">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="6ab07-p104">Se si desidera supportare client mobili interni ed esterni alla rete, i dispositivi mobili possono accedere alle funzionalità di mobilità da qualsiasi posizione. La configurazione predefinita prevede il supporto di client sia all'interno che all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="6ab07-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="6ab07-125">Sebbene la configurazione predefinita consenta il trasferimento del traffico client mobile al sito esterno, è possibile limitare questo traffico alla rete aziendale interna.</span><span class="sxs-lookup"><span data-stu-id="6ab07-125">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="6ab07-126">In questo caso, gli utenti possono utilizzare le applicazioni mobili di Lync nei dispositivi mobili solo quando si trovano all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="6ab07-126">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="6ab07-127">Per le distribuzioni che supportano la mobilità tramite il servizio per dispositivi mobili MCX e Lync 2010 mobile, è possibile eseguire il cmdlet **Set-CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6ab07-127">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="6ab07-128">Per impostare la mobilità solo per uso interno, è necessario utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6ab07-128">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ab07-129">Per UCWA non sono necessarie ulteriori configurazioni.</span><span class="sxs-lookup"><span data-stu-id="6ab07-129">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="6ab07-130">UCWA non dispone di una configurazione equivalente solo interna.</span><span class="sxs-lookup"><span data-stu-id="6ab07-130">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6ab07-131">Se si utilizza un server front-end di Lync Server 2013 &nbsp; o pool Front end e <STRONG>non si dispone</STRONG> di Lync Server 2010 &nbsp; front end server o pool Front End, non <STRONG>vi sono requisiti per la persistenza basata su cookie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6ab07-131">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="6ab07-132">Se è necessario mantenere tutti &nbsp; i server front end o i pool Front-End di Lync server 2010, le stesse regole vengono ancora applicate come in Lync Server 2010 per la persistenza basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="6ab07-132">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="6ab07-133">**Supporto delle notifiche push per dispositivi Apple iOS e Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="6ab07-133">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="6ab07-134">Se si supportano notifiche push, i dispositivi Apple iOS e Windows Phone supportati riceveranno una notifica degli eventi che si verificano quando l'applicazione mobile è inattiva.</span><span class="sxs-lookup"><span data-stu-id="6ab07-134">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="6ab07-135">È necessario configurare il server perimetrale in modo che disponga di una relazione di federazione con il servizio di notifica push di Lync Server basato sul cloud, che si trova nel centro dati di Lync Online, ed esegua un cmdlet per abilitare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="6ab07-135">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="6ab07-136">Se si desidera supportare le notifiche push tramite la rete di Wi-Fi, oltre a supportare le notifiche push tramite i provider di dispositivi mobili o le reti di dati, è necessario aprire la porta 5223 in uscita sulla rete aziendale Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="6ab07-136">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="6ab07-137">L'utilizzo delle notifiche push sulla rete Wi-Fi consente di supportare dispositivi mobili che utilizzano solo Wi-Fi e dispositivi mobili con una ricezione di scarsa qualità in ambienti chiusi.</span><span class="sxs-lookup"><span data-stu-id="6ab07-137">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6ab07-138">La porta di apertura TCP 5223 è necessaria solo quando si supportano i dispositivi Apple che eseguono il client per dispositivi mobili Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="6ab07-138">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="6ab07-139">Se non si supportano le notifiche push, gli utenti di dispositivi mobili Apple e Windows Phone non troveranno gli eventi, ad esempio gli inviti di messaggi istantanei o i messaggi mancati, che si verificano quando l'applicazione per dispositivi mobili non è attiva.</span><span class="sxs-lookup"><span data-stu-id="6ab07-139">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ab07-140">I client Lync 2013 mobile nei dispositivi Apple non richiedono notifiche push.</span><span class="sxs-lookup"><span data-stu-id="6ab07-140">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="6ab07-141">I client Lync 2013 per dispositivi mobili su Windows Phone utilizzano la notifica push.</span><span class="sxs-lookup"><span data-stu-id="6ab07-141">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="6ab07-142">La pianificazione della notifica push e la compensazione notifiche push rimangono invariate per Lync mobile nei dispositivi Windows Phone e Apple che non sono in grado di eseguire il client di telefonia mobile Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6ab07-142">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="6ab07-143">**Si desidera consentire a tutti gli utenti di accedere alle funzionalità per dispositivi mobili oppure si desidera specificare quali utenti possono accedere a queste funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="6ab07-143">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="6ab07-144">La tabella descrive le funzionalità disponibili per gli utenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ab07-144">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="6ab07-145">Le impostazioni predefinite consentono la chiamata tramite lavoro, consentono la funzionalità VoIP (Voice over IP) e consentono la mobilità.</span><span class="sxs-lookup"><span data-stu-id="6ab07-145">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="6ab07-146">Di seguito è indicato il set completo di opzioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="6ab07-146">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="6ab07-147">Caratteristica/nome parametro/ambito (i nomi di parametri dei criteri potrebbero non essere uguali)</span><span class="sxs-lookup"><span data-stu-id="6ab07-147">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="6ab07-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ab07-148">Description</span></span></th>
    <th><span data-ttu-id="6ab07-149">Introdotta</span><span class="sxs-lookup"><span data-stu-id="6ab07-149">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6ab07-150">Abilitare la mobilità</span><span class="sxs-lookup"><span data-stu-id="6ab07-150">Enable Mobility</span></span></p>
    <p><span data-ttu-id="6ab07-151">Nome del parametro: <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="6ab07-151">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="6ab07-152">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="6ab07-152">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-153">Impostazione amministrativa per controllare gli utenti in un determinato ambito in cui è installato Lync mobile, se il criterio è impostato su false, l'utente non sarà in grado di accedere al client.</span><span class="sxs-lookup"><span data-stu-id="6ab07-153">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="6ab07-154">L'impostazione predefinita è true.</span><span class="sxs-lookup"><span data-stu-id="6ab07-154">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-155">Aggiornamento cumulativo per Lync Server 2010: novembre 2011</span><span class="sxs-lookup"><span data-stu-id="6ab07-155">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ab07-156">Abilita voce esterna</span><span class="sxs-lookup"><span data-stu-id="6ab07-156">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="6ab07-157">Nome del parametro: <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="6ab07-157">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="6ab07-158">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="6ab07-158">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-159">Controlla la capacità di un utente di utilizzare la chiamata tramite il lavoro, caratteristica che consente agli utenti di effettuare e ricevere chiamate utilizzando il numero di lavoro invece del numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="6ab07-159">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="6ab07-160">Se il valore è impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate usando il proprio numero di lavoro dal proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6ab07-160">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="6ab07-161">L'impostazione predefinita è true</span><span class="sxs-lookup"><span data-stu-id="6ab07-161">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-162">Aggiornamento cumulativo per Lync Server 2010: novembre 2011</span><span class="sxs-lookup"><span data-stu-id="6ab07-162">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ab07-163">Abilitare l'audio e il video IP</span><span class="sxs-lookup"><span data-stu-id="6ab07-163">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="6ab07-164">Nome del parametro: <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="6ab07-164">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="6ab07-165">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="6ab07-165">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-166">Controlla se un utente può usare il VoIP per effettuare o ricevere chiamate vocali o video sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6ab07-166">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="6ab07-167">Se il valore è impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate video o VoIP sul proprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ab07-167">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="6ab07-168">L'impostazione predefinita è true.</span><span class="sxs-lookup"><span data-stu-id="6ab07-168">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-169">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-169">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6ab07-170">Richiedi WiFi per l'audio IP</span><span class="sxs-lookup"><span data-stu-id="6ab07-170">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="6ab07-171">Nome del parametro: <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="6ab07-171">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="6ab07-172">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="6ab07-172">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-173">Questa impostazione consente di definire se il client sarà tenuto a effettuare e ricevere chiamate tramite VoIP su WiFi anziché sulla rete di dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="6ab07-173">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="6ab07-174">Se impostato su true, l'utente può effettuare e ricevere chiamate VoIP solo quando si è connessi a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="6ab07-174">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="6ab07-175">L'impostazione predefinita è False.</span><span class="sxs-lookup"><span data-stu-id="6ab07-175">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-176">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-176">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6ab07-177">Richiedi il WiFi per IP video</span><span class="sxs-lookup"><span data-stu-id="6ab07-177">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="6ab07-178">Nome del parametro: <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="6ab07-178">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="6ab07-179">Ambito: globale/sito/utente</span><span class="sxs-lookup"><span data-stu-id="6ab07-179">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-180">Questa impostazione consente di definire se il client sarà tenuto a effettuare e ricevere chiamate video su Wi-Fi invece che sulla rete di dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="6ab07-180">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="6ab07-181">Se impostato su true, l'utente può effettuare e ricevere chiamate video solo quando si è connessi a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="6ab07-181">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="6ab07-182">L'impostazione predefinita è False.</span><span class="sxs-lookup"><span data-stu-id="6ab07-182">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="6ab07-183">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-183">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="6ab07-184">Per una descrizione delle impostazioni dei criteri che è possibile configurare e come gestire i criteri, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="6ab07-184">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="6ab07-185">**Partecipazione alle conferenze con un clic da parte degli utenti non abilitati per VoIP aziendale**</span><span class="sxs-lookup"><span data-stu-id="6ab07-185">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="6ab07-186">Per poter accedere alle funzionalità di mobilità e Chiama di ufficio, gli utenti devono essere abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6ab07-186">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="6ab07-187">Tuttavia, gli utenti che non sono abilitati per VoIP aziendale possono partecipare a conferenze facendo clic sul collegamento sul dispositivo mobile, se dispongono di un criterio vocale appropriato assegnato.</span><span class="sxs-lookup"><span data-stu-id="6ab07-187">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="6ab07-188">È possibile assegnare un criterio vocale specifico a questi utenti o verificare che esistano criteri globali o di criterio a livello di sito che si applicano a tali criteri.</span><span class="sxs-lookup"><span data-stu-id="6ab07-188">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="6ab07-189">Il criterio vocale assegnato deve disporre dei record di utilizzo della rete PSTN (Public Switched Telephone Network) e delle route che definiscono le aree in cui gli utenti possono effettuare chiamate in uscita per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="6ab07-189">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="6ab07-190">Per informazioni dettagliate sull'impostazione di criteri vocali, record di utilizzo PSTN e route, vedere [configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="6ab07-190">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ab07-191">Gli utenti mobili che desiderano utilizzare fare clic su join richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, in quanto facendo clic sul collegamento sul dispositivo mobile si produce una chiamata in uscita da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ab07-191">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ab07-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ab07-192">See Also</span></span>


[<span data-ttu-id="6ab07-193">Requisiti tecnici per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-193">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="6ab07-194">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab07-194">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

