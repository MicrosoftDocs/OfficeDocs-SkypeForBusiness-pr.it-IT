---
title: 'Lync Server 2013: Tabella Dialog'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="7d56e-102">Tabella Dialog in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d56e-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d56e-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7d56e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7d56e-104">La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="7d56e-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d56e-105"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7d56e-106"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7d56e-107"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7d56e-108"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d56e-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7d56e-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="7d56e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="7d56e-111">Principale</span><span class="sxs-lookup"><span data-stu-id="7d56e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="7d56e-112">Ora in cui l'agente QoE (Quality of Excellence) riceve il primo report da chiamante o chiamato.</span><span class="sxs-lookup"><span data-stu-id="7d56e-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="7d56e-113">Usato in combinazione con SessionSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="7d56e-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d56e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7d56e-115">int</span><span class="sxs-lookup"><span data-stu-id="7d56e-115">int</span></span></p></td>
<td><p><span data-ttu-id="7d56e-116">Principale</span><span class="sxs-lookup"><span data-stu-id="7d56e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7d56e-117">Numero di sequenza per distinguere le sessioni quando hanno lo stesso ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="7d56e-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d56e-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="7d56e-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d56e-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d56e-120">ID finestra di dialogo univoco globale.</span><span class="sxs-lookup"><span data-stu-id="7d56e-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d56e-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="7d56e-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="7d56e-122">int</span><span class="sxs-lookup"><span data-stu-id="7d56e-122">int</span></span></p></td>
<td><p><span data-ttu-id="7d56e-123">Indice</span><span class="sxs-lookup"><span data-stu-id="7d56e-123">index</span></span></p></td>
<td><p><span data-ttu-id="7d56e-124">Checksum dell'ID della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7d56e-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

