---
title: 'Lync Server 2013: tabella SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="d2104-102">Tabella SIPResponseMetaData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2104-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2104-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d2104-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d2104-p101">Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.</span><span class="sxs-lookup"><span data-stu-id="d2104-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="d2104-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2104-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2104-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="d2104-107">Column</span></span></th>
<th><span data-ttu-id="d2104-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d2104-108">Data Type</span></span></th>
<th><span data-ttu-id="d2104-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="d2104-109">Key/Index</span></span></th>
<th><span data-ttu-id="d2104-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d2104-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2104-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d2104-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d2104-112">int</span><span class="sxs-lookup"><span data-stu-id="d2104-112">int</span></span></p></td>
<td><p><span data-ttu-id="d2104-113">Principale</span><span class="sxs-lookup"><span data-stu-id="d2104-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d2104-114">Valore numerico che rappresenta il codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="d2104-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2104-115"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="d2104-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="d2104-116">int</span><span class="sxs-lookup"><span data-stu-id="d2104-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2104-p102">Classifica generale del codice di risposta. Sono incluse le classifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2104-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="d2104-119">1: risposte informali</span><span class="sxs-lookup"><span data-stu-id="d2104-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="d2104-120">2: risposte con esito positivo</span><span class="sxs-lookup"><span data-stu-id="d2104-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="d2104-121">3: risposte di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="d2104-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="d2104-122">4: risposte di errore client</span><span class="sxs-lookup"><span data-stu-id="d2104-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="d2104-123">5-risposte di errore del server</span><span class="sxs-lookup"><span data-stu-id="d2104-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="d2104-124">6: risposta di errore globale</span><span class="sxs-lookup"><span data-stu-id="d2104-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2104-125"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d2104-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="d2104-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d2104-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2104-p103">Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:</span><span class="sxs-lookup"><span data-stu-id="d2104-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="d2104-129">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="d2104-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

