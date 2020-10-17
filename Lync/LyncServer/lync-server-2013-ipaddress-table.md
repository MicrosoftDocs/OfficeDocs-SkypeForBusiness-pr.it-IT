---
title: 'Lync Server 2013: Tabella IPAddress'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d23e9aba844cb03779b220ed8d898a2e7664891
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514173"
---
# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="3399f-102">Tabella IPAddress in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3399f-102">IPAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3399f-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="3399f-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="3399f-104">La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="3399f-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3399f-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3399f-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3399f-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3399f-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3399f-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3399f-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3399f-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3399f-111">int</span><span class="sxs-lookup"><span data-stu-id="3399f-111">int</span></span></p></td>
<td><p><span data-ttu-id="3399f-112">Principale</span><span class="sxs-lookup"><span data-stu-id="3399f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3399f-113">Identificatore univoco per l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="3399f-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3399f-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3399f-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3399f-115">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="3399f-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="3399f-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="3399f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="3399f-p102">Indirizzo IP univoco (ad esempio, 189.168.1.1) mappato a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="3399f-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

