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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="05876-102">Tabella SIPResponseMetaData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05876-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05876-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05876-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05876-104">SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici.</span><span class="sxs-lookup"><span data-stu-id="05876-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="05876-105">Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="05876-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="05876-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05876-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05876-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="05876-107">Column</span></span></th>
<th><span data-ttu-id="05876-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="05876-108">Data Type</span></span></th>
<th><span data-ttu-id="05876-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="05876-109">Key/Index</span></span></th>
<th><span data-ttu-id="05876-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="05876-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05876-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="05876-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="05876-112">int</span><span class="sxs-lookup"><span data-stu-id="05876-112">int</span></span></p></td>
<td><p><span data-ttu-id="05876-113">Principale</span><span class="sxs-lookup"><span data-stu-id="05876-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="05876-114">Valore numerico che rappresenta il codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="05876-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05876-115"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="05876-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="05876-116">int</span><span class="sxs-lookup"><span data-stu-id="05876-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05876-117">Classificazione generale per il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="05876-117">General classification for the response code.</span></span> <span data-ttu-id="05876-118">Le classificazioni includono:</span><span class="sxs-lookup"><span data-stu-id="05876-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="05876-119">1-risposte informative</span><span class="sxs-lookup"><span data-stu-id="05876-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="05876-120">2-risposte di successo</span><span class="sxs-lookup"><span data-stu-id="05876-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="05876-121">3-risposte di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="05876-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="05876-122">4-risposte di errore client</span><span class="sxs-lookup"><span data-stu-id="05876-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="05876-123">5--risposte di errore del server</span><span class="sxs-lookup"><span data-stu-id="05876-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="05876-124">6-risposta di errore globale</span><span class="sxs-lookup"><span data-stu-id="05876-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05876-125"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="05876-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="05876-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05876-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05876-127">Descrizione del codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="05876-127">Description of the SIP response code.</span></span> <span data-ttu-id="05876-128">Ad esempio, il codice di risposta 181 ha la seguente descrizione:</span><span class="sxs-lookup"><span data-stu-id="05876-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="05876-129">Chiamata inoltrata</span><span class="sxs-lookup"><span data-stu-id="05876-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

