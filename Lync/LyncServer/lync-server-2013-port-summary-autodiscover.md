---
title: 'Lync Server 2013: riepilogo delle porte-individuazione automatica'
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
ms.openlocfilehash: 635f8fca3b267fa2366b66b990ec0621f58f58e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="9364c-102">Riepilogo delle porte-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9364c-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9364c-103">_**Ultimo argomento modificato:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="9364c-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="9364c-104">Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, quando viene pubblicato `lyncdiscover.<domain>` in `lyncdiscoverinternal.<domain>` DNS utilizzando i record host e e, può essere utilizzato dai client per individuare le funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9364c-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="9364c-105">Per consentire ai dispositivi mobili che eseguono Lync mobile di utilizzare l'individuazione automatica, è possibile che sia necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi server Director e front end che esegue il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="9364c-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="9364c-106">Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="9364c-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="9364c-107">La decisione sull'eventuale utilizzo degli elenchi di nomi alternativi del soggetto nei proxy inversi è basata sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="9364c-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="9364c-108">**Pubblicati sulla porta 80**   per i dispositivi mobili, non sono necessarie modifiche ai certificati se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="9364c-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="9364c-109">Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un server Director o front end su porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="9364c-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="9364c-110">**Pubblicati sulla porta 443**   l'elenco dei nomi alternativi del soggetto sui certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni `lyncdiscover.<sipdomain>` deve contenere una voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9364c-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9364c-111">Per le nuove installazioni o gli aggiornamenti da Lync Server 2010 in cui è stata distribuita la funzionalità di mobilità, è stata utilizzata la porta 80 per l'individuazione automatica del servizio per dispositivi mobili o i certificati riemessi con il nome soggetto e i nomi alternativi del soggetto corretti.</span><span class="sxs-lookup"><span data-stu-id="9364c-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="9364c-112">Esaminare i certificati nel server Director e front end per confermare il percorso scelto.</span><span class="sxs-lookup"><span data-stu-id="9364c-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="9364c-113">Dettagli del firewall per il server proxy inverso: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="9364c-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9364c-114">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9364c-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9364c-115">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9364c-115">Source IP Address</span></span></th>
<th><span data-ttu-id="9364c-116">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9364c-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="9364c-117">Notes</span><span class="sxs-lookup"><span data-stu-id="9364c-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9364c-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9364c-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9364c-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9364c-119">Any</span></span></p></td>
<td><p><span data-ttu-id="9364c-120">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9364c-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="9364c-121">Optional Reindirizzamento a HTTPS se l'utente immette http://&lt;publishedSiteFQDN.&gt;</span><span class="sxs-lookup"><span data-stu-id="9364c-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="9364c-122">Necessario anche se si utilizza Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="9364c-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9364c-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9364c-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9364c-124">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9364c-124">Any</span></span></p></td>
<td><p><span data-ttu-id="9364c-125">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9364c-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="9364c-126">Download della Rubrica, servizio query Web della Rubrica, individuazione automatica, aggiornamenti dei client, contenuto delle riunioni, aggiornamenti dei dispositivi, espansione di gruppi, Office Web Apps per le conferenze, conferenze telefoniche con accesso esterno e riunioni.</span><span class="sxs-lookup"><span data-stu-id="9364c-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="9364c-127">Dettagli del firewall per il server proxy inverso: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="9364c-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9364c-128">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9364c-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9364c-129">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9364c-129">Source IP Address</span></span></th>
<th><span data-ttu-id="9364c-130">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9364c-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="9364c-131">Notes</span><span class="sxs-lookup"><span data-stu-id="9364c-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9364c-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="9364c-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="9364c-133">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9364c-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="9364c-134">Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="9364c-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="9364c-135">Obbligatorio se si utilizza il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="9364c-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="9364c-136">Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso, in modo che il pool di servizi Web possa distinguerlo dal traffico della rete interna.</span><span class="sxs-lookup"><span data-stu-id="9364c-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9364c-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9364c-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9364c-138">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9364c-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="9364c-139">Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="9364c-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="9364c-140">Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso, in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</span><span class="sxs-lookup"><span data-stu-id="9364c-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

