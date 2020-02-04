---
title: 'Lync Server 2013: riepilogo del certificato-individuazione automatica'
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
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="7b58c-102">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b58c-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b58c-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="7b58c-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="7b58c-104">Il servizio di individuazione automatica di Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere usato dai client Lync per individuare i servizi server e utente.</span><span class="sxs-lookup"><span data-stu-id="7b58c-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="7b58c-105">Se si esegue l'aggiornamento da Lync Server 2010 e non si distribuisce la mobilità, prima che i client possano usare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato in qualsiasi Director e front end server in cui è in uso il servizio di rilevamento automatico.</span><span class="sxs-lookup"><span data-stu-id="7b58c-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="7b58c-106">Può essere inoltre necessario modificare gli elenchi di nomi alternativi oggetto nei certificati usati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="7b58c-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="7b58c-107">La decisione relativa all'uso di elenchi di nomi alternativi oggetto nei proxy inversi si basa sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="7b58c-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="7b58c-108">**Pubblicato sulla porta 80**   non sono necessarie modifiche al certificato se la query iniziale per il servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="7b58c-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="7b58c-109">Il motivo è che i dispositivi mobili che utilizzano Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi saranno ponticellati a un amministratore o a un server front-end sulla porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="7b58c-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="7b58c-110">Per informazioni dettagliate, vedere la sezione "procedura di individuazione automatica tramite la porta 80" [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="7b58c-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="7b58c-111">**Pubblicato in porta 443**   l'elenco dei nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un \*lyncdiscover.\< SipDomain\> \* voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b58c-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7b58c-112">Ti consigliamo vivamente di usare HTTPS tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="7b58c-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="7b58c-113">HTTPS usa i certificati per crittografare il traffico.</span><span class="sxs-lookup"><span data-stu-id="7b58c-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="7b58c-114">HTTP non prevede la crittografia e tutti i dati inviati saranno testo normale.</span><span class="sxs-lookup"><span data-stu-id="7b58c-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="7b58c-115">La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="7b58c-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="7b58c-116">Ma per i certificati pubblici usati nella regola di pubblicazione del servizio Web, l'aggiunta di più voci di nomi alternativi soggetto può diventare costosa.</span><span class="sxs-lookup"><span data-stu-id="7b58c-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="7b58c-117">Per risolvere il problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="7b58c-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b58c-118">Se l'infrastruttura di Lync Server 2013 USA certificati interni emessi da un'autorità di certificazione (CA) interna e si prevede di supportare i dispositivi mobili che si connettono in modalità wireless, è necessario che la catena di certificati radice della CA interna sia installata nei dispositivi mobili o è necessario passare a un certificato pubblico nell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b58c-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="7b58c-119">In questo argomento vengono descritti i nomi alternativi oggetto aggiunti necessari per il Director, Front End Server e proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7b58c-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="7b58c-120">Viene fatto riferimento solo ai nomi alternativi oggetto aggiunti (SAN).</span><span class="sxs-lookup"><span data-stu-id="7b58c-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="7b58c-121">Fare riferimento alle sezioni pianificazione per informazioni sulle altre voci sui certificati.</span><span class="sxs-lookup"><span data-stu-id="7b58c-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="7b58c-122">Per informazioni dettagliate, vedere [scenari per il Director in Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [scenari per il proxy inverso in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="7b58c-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="7b58c-123">Le tabelle seguenti definiscono le voci SAN di individuazione automatica per il pool di Director, il pool Front end e il proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="7b58c-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="7b58c-124">Requisiti dei certificati del pool di Director</span><span class="sxs-lookup"><span data-stu-id="7b58c-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b58c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b58c-125">Description</span></span></th>
<th><span data-ttu-id="7b58c-126">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="7b58c-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b58c-127">URL del servizio di individuazione automatica interno</span><span class="sxs-lookup"><span data-stu-id="7b58c-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7b58c-128">SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b58c-129">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="7b58c-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7b58c-130">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b58c-131">Si assegna il certificato appena aggiornato con la nuova voce SAN al certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="7b58c-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="7b58c-132">In alternativa, è possibile usare SAN = \*. &lt;SipDomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="7b58c-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="7b58c-133">Requisiti del certificato del pool Front-End</span><span class="sxs-lookup"><span data-stu-id="7b58c-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b58c-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b58c-134">Description</span></span></th>
<th><span data-ttu-id="7b58c-135">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="7b58c-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b58c-136">URL del servizio di individuazione automatica interno</span><span class="sxs-lookup"><span data-stu-id="7b58c-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7b58c-137">SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b58c-138">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="7b58c-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7b58c-139">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b58c-140">Si assegna il certificato appena aggiornato con la nuova voce SAN al certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="7b58c-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="7b58c-141">In alternativa, è possibile usare SAN = \*. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="7b58c-142">Requisiti dei certificati reverse proxy (public CA)</span><span class="sxs-lookup"><span data-stu-id="7b58c-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b58c-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b58c-143">Description</span></span></th>
<th><span data-ttu-id="7b58c-144">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="7b58c-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b58c-145">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="7b58c-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7b58c-146">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7b58c-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b58c-147">Si assegna il certificato appena aggiornato con la nuova voce SAN al listener SSL nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7b58c-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

