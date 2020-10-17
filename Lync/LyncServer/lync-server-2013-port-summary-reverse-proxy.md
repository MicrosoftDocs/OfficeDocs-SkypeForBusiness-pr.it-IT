---
title: 'Lync Server 2013: riepilogo delle porte-proxy inverso'
description: 'Lync Server 2013: riepilogo delle porte-proxy inverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555252"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="36477-103">Riepilogo delle porte-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36477-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36477-104">_**Ultimo argomento modificato:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="36477-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="36477-105">Per il proxy inverso sono previsti requisiti minimi per il firewall, la porta e il protocollo.</span><span class="sxs-lookup"><span data-stu-id="36477-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="36477-106">I requisiti del firewall esterno sono HTTPS/TCP/443 e il protocollo HTTP/TCP/80 facoltativo.</span><span class="sxs-lookup"><span data-stu-id="36477-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="36477-107">HTTPS viene utilizzato per le comunicazioni protette SSL e TLS tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="36477-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="36477-108">HTTP viene utilizzato se si sceglie di consentire l'accesso al servizio di individuazione automatica quando si modificano i certificati potrebbe risultare difficile o non giustificato il costo.</span><span class="sxs-lookup"><span data-stu-id="36477-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="36477-109">I client prevedono di contattare il server Office Web Apps su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="36477-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="36477-110">Il server Office Web Apps prevede la comunicazione da client interni su HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="36477-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="36477-111">La configurazione consigliata consiste nel consentire HTTPS/TCP/443 dal proxy inverso al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="36477-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="36477-112">La porta 8080 viene utilizzata per instradare il traffico dall'interfaccia interna del proxy inverso al front end server, all'IP virtuale del pool Front End (VIP) o al VIP del pool di Director o Director facoltativo.</span><span class="sxs-lookup"><span data-stu-id="36477-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="36477-113">La porta TCP 8080 è obbligatoria per i dispositivi mobili che eseguono Lync per individuare il servizio di individuazione automatica in situazioni in cui la modifica del certificato della regola di pubblicazione dei servizi Web esterni è indesiderata (ad esempio, se si dispone di un numero elevato di domini SIP).</span><span class="sxs-lookup"><span data-stu-id="36477-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="36477-114">Se si sceglie di acquisire nuovi certificati con le voci SAN necessarie, la porta TCP 8080 non è necessaria ed è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="36477-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="36477-115">La porta 4443 viene utilizzata per il traffico dall'interfaccia interna del proxy inverso al front end server, all'IP virtuale del pool Front End (VIP) o al VIP del pool di Director o Director facoltativo</span><span class="sxs-lookup"><span data-stu-id="36477-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="36477-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="36477-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="36477-117">Non confondere l'4443 su TCP dal proxy inverso alla distribuzione interna per la porta 4443 su traffico TCP dal server Standard Edition o dal pool Front end che gestisce il ruolo dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="36477-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="36477-118">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="36477-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="36477-119">Dettagli del firewall per il server proxy inverso: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="36477-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36477-120">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="36477-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="36477-121">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="36477-121">Source IP Address</span></span></th>
<th><span data-ttu-id="36477-122">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="36477-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="36477-123">Note</span><span class="sxs-lookup"><span data-stu-id="36477-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36477-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="36477-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="36477-125">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="36477-125">Any</span></span></p></td>
<td><p><span data-ttu-id="36477-126">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="36477-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="36477-127">Optional Reindirizzamento a HTTPS se l'utente immette http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="36477-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="36477-128">Necessario anche se si utilizza Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="36477-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36477-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="36477-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="36477-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="36477-130">Any</span></span></p></td>
<td><p><span data-ttu-id="36477-131">Listener proxy inverso</span><span class="sxs-lookup"><span data-stu-id="36477-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="36477-132">Download della Rubrica, servizio query Web della Rubrica, individuazione automatica, aggiornamenti dei client, contenuto delle riunioni, aggiornamenti dei dispositivi, espansione di gruppi, Office Web Apps per le conferenze, conferenze telefoniche con accesso esterno e riunioni.</span><span class="sxs-lookup"><span data-stu-id="36477-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="36477-133">Dettagli del firewall per il server proxy inverso: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="36477-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36477-134">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="36477-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="36477-135">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="36477-135">Source IP Address</span></span></th>
<th><span data-ttu-id="36477-136">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="36477-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="36477-137">Note</span><span class="sxs-lookup"><span data-stu-id="36477-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36477-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="36477-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="36477-139">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="36477-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="36477-140">Front End Server, pool Front End, Director, pool di Director</span><span class="sxs-lookup"><span data-stu-id="36477-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="36477-141">Obbligatorio se si utilizza il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="36477-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="36477-142">Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso, in modo che il pool di servizi Web possa distinguerlo dal traffico della rete interna.</span><span class="sxs-lookup"><span data-stu-id="36477-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36477-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="36477-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="36477-144">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="36477-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="36477-145">Front End Server, pool Front End, Director, pool di Director</span><span class="sxs-lookup"><span data-stu-id="36477-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="36477-146">Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso, in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</span><span class="sxs-lookup"><span data-stu-id="36477-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36477-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="36477-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="36477-148">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="36477-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="36477-149">Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="36477-149">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

