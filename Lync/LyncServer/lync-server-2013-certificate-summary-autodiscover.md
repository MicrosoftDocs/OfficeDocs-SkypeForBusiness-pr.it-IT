---
title: 'Lync Server 2013: riepilogo del certificato-individuazione automatica'
description: 'Lync Server 2013: riepilogo del certificato-individuazione automatica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574712"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="79bb1-103">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79bb1-103">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79bb1-104">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="79bb1-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="79bb1-105">Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, quando viene pubblicato in DNS, può essere utilizzato dai client Lync per individuare i servizi utente e server.</span><span class="sxs-lookup"><span data-stu-id="79bb1-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="79bb1-106">Se si esegue l'aggiornamento da Lync Server 2010 e non è stata distribuita la funzionalità di mobilità, prima che i client possano utilizzare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi Director e front end server che esegue il servizio Autodiscover.</span><span class="sxs-lookup"><span data-stu-id="79bb1-106">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="79bb1-107">Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="79bb1-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="79bb1-108">La decisione sull'eventuale utilizzo degli elenchi di nomi alternativi del soggetto nei proxy inversi è basata sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="79bb1-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="79bb1-109">**Pubblicati sulla porta 80**     Non sono necessarie modifiche ai certificati se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="79bb1-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="79bb1-110">Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno ponticellati su un server Director o front end su porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="79bb1-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="79bb1-111">Per informazioni dettagliate, vedere la sezione "processo di individuazione automatica iniziale tramite la porta 80" [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="79bb1-111">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="79bb1-112">**Pubblicati sulla porta 443**     L'elenco dei nomi alternativi del soggetto nei certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un \*lyncdiscover. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="79bb1-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="79bb1-113">voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79bb1-113">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="79bb1-114">Si consiglia vivamente di utilizzare HTTPS su HTTP.</span><span class="sxs-lookup"><span data-stu-id="79bb1-114">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="79bb1-115">HTTPS utilizza i certificati per crittografare il traffico.</span><span class="sxs-lookup"><span data-stu-id="79bb1-115">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="79bb1-116">HTTP non fornisce la crittografia e tutti i dati inviati diventeranno di testo normale.</span><span class="sxs-lookup"><span data-stu-id="79bb1-116">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="79bb1-117">La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="79bb1-117">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="79bb1-118">Tuttavia, per i certificati pubblici utilizzati nella regola di pubblicazione dei servizi Web, l'aggiunta di più voci del nome alternativo soggetto può essere costosa.</span><span class="sxs-lookup"><span data-stu-id="79bb1-118">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="79bb1-119">Per ovviare a questo problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="79bb1-119">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79bb1-120">Se l'infrastruttura di Lync Server 2013 utilizza certificati interni emessi da un'autorità di certificazione (CA) interna e si prevede di supportare i dispositivi mobili che si connettono in modalità wireless, è necessario che la catena di certificati radice della CA interna sia installata nei dispositivi mobili o che sia necessario passare a un certificato pubblico nell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79bb1-120">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="79bb1-121">In questo argomento vengono descritti i nomi alternativi del soggetto aggiunti necessari per il server Director, front-end e il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="79bb1-121">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="79bb1-122">Si fa riferimento solo ai nomi alternativi del soggetto (SAN) aggiunti.</span><span class="sxs-lookup"><span data-stu-id="79bb1-122">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="79bb1-123">Fare riferimento alle sezioni di pianificazione per le indicazioni sulle altre voci sui certificati.</span><span class="sxs-lookup"><span data-stu-id="79bb1-123">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="79bb1-124">Per informazioni dettagliate, vedere [Scenarios for the Director in Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [scenari per il proxy inverso in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="79bb1-124">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="79bb1-125">Nelle tabelle riportate di seguito vengono definite le voci SAN di individuazione automatica per il pool di server Director, il pool Front end e il proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="79bb1-125">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="79bb1-126">Requisiti relativi ai certificati per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="79bb1-126">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79bb1-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79bb1-127">Description</span></span></th>
<th><span data-ttu-id="79bb1-128">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="79bb1-128">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79bb1-129">URL interno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79bb1-129">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="79bb1-130">SAN = LyncdiscoverInternal. &lt; nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-130">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79bb1-131">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79bb1-131">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="79bb1-132">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-132">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="79bb1-133">È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="79bb1-133">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="79bb1-134">In alternativa, è possibile utilizzare SAN = \*. &lt; SipDomain &gt; .</span><span class="sxs-lookup"><span data-stu-id="79bb1-134">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="79bb1-135">Requisiti relativi ai certificati per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="79bb1-135">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79bb1-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79bb1-136">Description</span></span></th>
<th><span data-ttu-id="79bb1-137">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="79bb1-137">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79bb1-138">URL interno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79bb1-138">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="79bb1-139">SAN = LyncdiscoverInternal. &lt; nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-139">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79bb1-140">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79bb1-140">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="79bb1-141">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-141">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="79bb1-142">È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="79bb1-142">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="79bb1-143">In alternativa, è possibile utilizzare SAN = \*. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-143">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="79bb1-144">Requisiti relativi ai certificati del proxy inverso (CA pubblica)</span><span class="sxs-lookup"><span data-stu-id="79bb1-144">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79bb1-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79bb1-145">Description</span></span></th>
<th><span data-ttu-id="79bb1-146">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="79bb1-146">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79bb1-147">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79bb1-147">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="79bb1-148">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="79bb1-148">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="79bb1-149">È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al listener SSL nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="79bb1-149">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

