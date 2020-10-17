---
title: 'Lync Server 2013: riepilogo del certificato-proxy inverso'
description: 'Lync Server 2013: riepilogo del certificato-proxy inverso.'
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
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572302"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="d4484-103">Riepilogo del certificato-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4484-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4484-104">_**Ultimo argomento modificato:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="d4484-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="d4484-105">I requisiti dei certificati per il proxy inverso sono molto più semplici rispetto ai server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="d4484-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="d4484-106">Il diagramma di flusso descrive i requisiti necessari.</span><span class="sxs-lookup"><span data-stu-id="d4484-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="d4484-107">La tabella di accompagnamento presenta il nome soggetto e i nomi alternativi del soggetto del certificato tipici in relazione agli scenari che sono stati esaminati nelle discussioni sui server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="d4484-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="d4484-108">Per ulteriori informazioni sugli scenari del server perimetrale, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d4484-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="d4484-109">**Diagramma di flusso dei certificati per proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="d4484-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="d4484-110">![Diagramma di flusso dei certificati per i server perimetrali](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramma di flusso dei certificati per i server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="d4484-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="d4484-111">Proxy inverso: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="d4484-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4484-112">Componente</span><span class="sxs-lookup"><span data-stu-id="d4484-112">Component</span></span></th>
<th><span data-ttu-id="d4484-113">Nome soggetto</span><span class="sxs-lookup"><span data-stu-id="d4484-113">Subject name</span></span></th>
<th><span data-ttu-id="d4484-114">Ordine/nome alternativo soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="d4484-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="d4484-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="d4484-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4484-116">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="d4484-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="d4484-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d4484-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d4484-124">(Facoltativo):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4484-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d4484-125">Il certificato deve essere emesso da una CA pubblica e con utilizzo chiavi avanzato del server.</span><span class="sxs-lookup"><span data-stu-id="d4484-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="d4484-126">I servizi includono il servizio Rubrica, l'espansione del gruppo di distribuzione Office Web Apps per le conferenze e le regole di pubblicazione del dispositivo IP di Lync.</span><span class="sxs-lookup"><span data-stu-id="d4484-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="d4484-127">Il nome alternativo del soggetto include:</span><span class="sxs-lookup"><span data-stu-id="d4484-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4484-128">FQDN dei servizi Web esterni per Front End Server o pool Front End</span><span class="sxs-lookup"><span data-stu-id="d4484-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="d4484-129">FQDN dei servizi Web esterni per il pool di server Director o Director</span><span class="sxs-lookup"><span data-stu-id="d4484-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="d4484-130">Conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d4484-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="d4484-131">Regola di pubblicazione per riunioni online</span><span class="sxs-lookup"><span data-stu-id="d4484-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="d4484-132">Office Web Apps per le conferenze</span><span class="sxs-lookup"><span data-stu-id="d4484-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="d4484-133">Lyncdiscover (individuazione automatica)</span><span class="sxs-lookup"><span data-stu-id="d4484-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="d4484-134">Il carattere jolly facoltativo sostituisce il nome alternativo del soggetto meet e dialin</span><span class="sxs-lookup"><span data-stu-id="d4484-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

