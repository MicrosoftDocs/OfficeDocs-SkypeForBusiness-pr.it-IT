---
title: 'Lync Server 2013: tabella SIPResponseMetaData'
description: 'Lync Server 2013: tabella SIPResponseMetaData.'
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
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558982"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="254a3-103">Tabella SIPResponseMetaData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="254a3-103">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="254a3-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="254a3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="254a3-p101">Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.</span><span class="sxs-lookup"><span data-stu-id="254a3-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="254a3-107">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="254a3-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="254a3-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="254a3-108">Column</span></span></th>
<th><span data-ttu-id="254a3-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="254a3-109">Data Type</span></span></th>
<th><span data-ttu-id="254a3-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="254a3-110">Key/Index</span></span></th>
<th><span data-ttu-id="254a3-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="254a3-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="254a3-112"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="254a3-112"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="254a3-113">int</span><span class="sxs-lookup"><span data-stu-id="254a3-113">int</span></span></p></td>
<td><p><span data-ttu-id="254a3-114">Principale</span><span class="sxs-lookup"><span data-stu-id="254a3-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="254a3-115">Valore numerico che rappresenta il codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="254a3-115">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254a3-116"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="254a3-116"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="254a3-117">int</span><span class="sxs-lookup"><span data-stu-id="254a3-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="254a3-p102">Classifica generale del codice di risposta. Sono incluse le classifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="254a3-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="254a3-120">1: risposte informali</span><span class="sxs-lookup"><span data-stu-id="254a3-120">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="254a3-121">2: risposte con esito positivo</span><span class="sxs-lookup"><span data-stu-id="254a3-121">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="254a3-122">3: risposte di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="254a3-122">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="254a3-123">4: risposte di errore client</span><span class="sxs-lookup"><span data-stu-id="254a3-123">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="254a3-124">5-risposte di errore del server</span><span class="sxs-lookup"><span data-stu-id="254a3-124">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="254a3-125">6: risposta di errore globale</span><span class="sxs-lookup"><span data-stu-id="254a3-125">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254a3-126"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="254a3-126"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="254a3-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="254a3-127">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="254a3-p103">Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:</span><span class="sxs-lookup"><span data-stu-id="254a3-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="254a3-130">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="254a3-130">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

