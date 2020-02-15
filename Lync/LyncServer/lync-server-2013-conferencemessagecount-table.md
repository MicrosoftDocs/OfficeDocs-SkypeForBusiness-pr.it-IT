---
title: 'Lync Server 2013: tabella ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e13f45936f210085361624a0d884f507a88e0d35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="eb35b-102">Tabella ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb35b-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb35b-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eb35b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eb35b-104">Ogni record di questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="eb35b-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="eb35b-105">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="eb35b-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb35b-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="eb35b-106">Column</span></span></th>
<th><span data-ttu-id="eb35b-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="eb35b-107">Data Type</span></span></th>
<th><span data-ttu-id="eb35b-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="eb35b-108">Key/Index</span></span></th>
<th><span data-ttu-id="eb35b-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="eb35b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb35b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb35b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb35b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="eb35b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="eb35b-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="eb35b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb35b-113">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb35b-113">Time of conference instance.</span></span> <span data-ttu-id="eb35b-114">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb35b-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="eb35b-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="eb35b-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb35b-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eb35b-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eb35b-117">int</span><span class="sxs-lookup"><span data-stu-id="eb35b-117">int</span></span></p></td>
<td><p><span data-ttu-id="eb35b-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="eb35b-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb35b-119">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb35b-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="eb35b-120">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb35b-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="eb35b-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="eb35b-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb35b-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="eb35b-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="eb35b-123">int</span><span class="sxs-lookup"><span data-stu-id="eb35b-123">int</span></span></p></td>
<td><p><span data-ttu-id="eb35b-124">Stranieri</span><span class="sxs-lookup"><span data-stu-id="eb35b-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb35b-125">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eb35b-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb35b-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="eb35b-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="eb35b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="eb35b-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb35b-128">Il numero di messaggi inviati dall'utente durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb35b-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

