---
title: 'Lync Server 2013: riepilogo delle porte-individuazione automatica'
description: 'Lync Server 2013: riepilogo delle porte-individuazione automatica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543142"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="ab153-103">Riepilogo delle porte-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab153-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab153-104">_**Ultimo argomento modificato:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="ab153-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="ab153-105">Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, quando viene pubblicato in DNS utilizzando i `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` record host e e, può essere utilizzato dai client per individuare le funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab153-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="ab153-106">Per consentire ai dispositivi mobili che eseguono Lync mobile di utilizzare l'individuazione automatica, è possibile che sia necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi server Director e front end che esegue il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="ab153-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ab153-107">Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="ab153-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ab153-108">La decisione sull'eventuale utilizzo degli elenchi di nomi alternativi del soggetto nei proxy inversi è basata sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="ab153-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ab153-109">**Pubblicati sulla porta 80**     Per i dispositivi mobili, non sono necessarie modifiche ai certificati se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="ab153-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ab153-110">Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un server Director o front end su porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="ab153-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="ab153-111">**Pubblicati sulla porta 443**     L'elenco dei nomi alternativi del soggetto nei certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere una `lyncdiscover.<sipdomain>` voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab153-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ab153-112">Per le nuove installazioni o gli aggiornamenti da Lync Server 2010 in cui è stata distribuita la funzionalità di mobilità, è stata utilizzata la porta 80 per l'individuazione automatica del servizio per dispositivi mobili o i certificati riemessi con il nome soggetto e i nomi alternativi del soggetto corretti.</span><span class="sxs-lookup"><span data-stu-id="ab153-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="ab153-113">Esaminare i certificati nel server Director e front end per confermare il percorso scelto.</span><span class="sxs-lookup"><span data-stu-id="ab153-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="ab153-114">Dettagli del firewall per il server proxy inverso: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="ab153-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab153-115">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ab153-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ab153-116">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ab153-116">Source IP Address</span></span></th>
<th><span data-ttu-id="ab153-117">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ab153-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="ab153-118">Note</span><span class="sxs-lookup"><span data-stu-id="ab153-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab153-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ab153-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ab153-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ab153-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ab153-121">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab153-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ab153-122">Optional Reindirizzamento a HTTPS se l'utente immette http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="ab153-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="ab153-123">Necessario anche se si utilizza Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="ab153-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab153-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ab153-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ab153-125">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ab153-125">Any</span></span></p></td>
<td><p><span data-ttu-id="ab153-126">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab153-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ab153-127">Download della Rubrica, servizio query Web della Rubrica, individuazione automatica, aggiornamenti dei client, contenuto delle riunioni, aggiornamenti dei dispositivi, espansione di gruppi, Office Web Apps per le conferenze, conferenze telefoniche con accesso esterno e riunioni.</span><span class="sxs-lookup"><span data-stu-id="ab153-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="ab153-128">Dettagli del firewall per il server proxy inverso: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="ab153-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab153-129">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ab153-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ab153-130">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ab153-130">Source IP Address</span></span></th>
<th><span data-ttu-id="ab153-131">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ab153-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="ab153-132">Note</span><span class="sxs-lookup"><span data-stu-id="ab153-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab153-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="ab153-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="ab153-134">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab153-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ab153-135">Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="ab153-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ab153-136">Obbligatorio se si utilizza il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="ab153-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="ab153-137">Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso, in modo che il pool di servizi Web possa distinguerlo dal traffico della rete interna.</span><span class="sxs-lookup"><span data-stu-id="ab153-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab153-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ab153-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ab153-139">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab153-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ab153-140">Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="ab153-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ab153-141">Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso, in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</span><span class="sxs-lookup"><span data-stu-id="ab153-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

