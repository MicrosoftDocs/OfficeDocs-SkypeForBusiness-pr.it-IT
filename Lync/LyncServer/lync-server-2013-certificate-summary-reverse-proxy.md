---
title: 'Lync Server 2013: Riepilogo dei certificati - proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="0f86e-102">Riepilogo dei certificati - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f86e-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f86e-103">_**Argomento Ultima modifica:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="0f86e-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="0f86e-104">I requisiti di certificato per il proxy inverso sono molto più semplici di quelli per gli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0f86e-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="0f86e-105">Il diagramma di flusso fornito presenta i requisiti necessari.</span><span class="sxs-lookup"><span data-stu-id="0f86e-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="0f86e-106">La tabella associata presenta il nome del soggetto del certificato tipico e i nomi alternativi oggetto in relazione agli scenari che sono stati esaminati nelle discussioni su Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0f86e-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="0f86e-107">Per altre informazioni sugli scenari di Edge Server, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0f86e-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="0f86e-108">**Diagramma di flusso certificati per proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="0f86e-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="0f86e-109">![Diagramma di flusso Certificati per Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramma di flusso Certificati per Edge Server")</span><span class="sxs-lookup"><span data-stu-id="0f86e-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="0f86e-110">Proxy inverso: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="0f86e-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f86e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0f86e-111">Component</span></span></th>
<th><span data-ttu-id="0f86e-112">Nome oggetto</span><span class="sxs-lookup"><span data-stu-id="0f86e-112">Subject name</span></span></th>
<th><span data-ttu-id="0f86e-113">Nome alternativo oggetto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="0f86e-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="0f86e-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="0f86e-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f86e-115">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0f86e-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="0f86e-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f86e-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="0f86e-123">(Facoltativo):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f86e-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f86e-124">Il certificato deve essere emesso da un'autorità di certificazione pubblica e con il server EKU.</span><span class="sxs-lookup"><span data-stu-id="0f86e-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="0f86e-125">I servizi includono servizio Rubrica, espansione gruppi di distribuzione Office Web Apps per le conferenze e regole di pubblicazione di Lync per dispositivi IP.</span><span class="sxs-lookup"><span data-stu-id="0f86e-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="0f86e-126">Il nome alternativo soggetto include:</span><span class="sxs-lookup"><span data-stu-id="0f86e-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f86e-127">FQDN dei servizi Web esterni per Front End Server o pool Front-End</span><span class="sxs-lookup"><span data-stu-id="0f86e-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="0f86e-128">FQDN dei servizi Web esterni per il pool di Director o Director</span><span class="sxs-lookup"><span data-stu-id="0f86e-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="0f86e-129">Chiamate in conferenza</span><span class="sxs-lookup"><span data-stu-id="0f86e-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="0f86e-130">Regola di pubblicazione delle riunioni online</span><span class="sxs-lookup"><span data-stu-id="0f86e-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="0f86e-131">Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="0f86e-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="0f86e-132">Lyncdiscover (individuazione automatica)</span><span class="sxs-lookup"><span data-stu-id="0f86e-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="0f86e-133">Il carattere jolly facoltativo sostituisce sia la riunione che la chiamata SAN</span><span class="sxs-lookup"><span data-stu-id="0f86e-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

