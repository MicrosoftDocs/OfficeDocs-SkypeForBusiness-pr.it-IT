---
title: 'Lync Server 2013: tabella tblServerIdentity'
description: 'Lync Server 2013: tabella tblServerIdentity.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564532"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="68955-103">Tabella tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68955-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68955-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="68955-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="68955-105">Tabella tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="68955-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="68955-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="68955-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68955-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="68955-107">Column</span></span></th>
<th><span data-ttu-id="68955-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="68955-108">Type</span></span></th>
<th><span data-ttu-id="68955-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68955-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68955-110">serverID</span><span class="sxs-lookup"><span data-stu-id="68955-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="68955-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="68955-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="68955-112">ID del server.</span><span class="sxs-lookup"><span data-stu-id="68955-112">Server ID.</span></span> <span data-ttu-id="68955-113">Corrisponde all'ID istanza dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="68955-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68955-114">serverAddress</span><span class="sxs-lookup"><span data-stu-id="68955-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="68955-115">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="68955-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="68955-116">Indirizzo del server che usa l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="68955-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68955-117">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="68955-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="68955-118">datetime</span><span class="sxs-lookup"><span data-stu-id="68955-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="68955-119">Ora dell'ultimo aggiornamento di questa riga eseguito dal Channel Server per confermare che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68955-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="68955-120">Chiave</span><span class="sxs-lookup"><span data-stu-id="68955-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68955-121">Colonna</span><span class="sxs-lookup"><span data-stu-id="68955-121">Column</span></span></th>
<th><span data-ttu-id="68955-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68955-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68955-123">serverID</span><span class="sxs-lookup"><span data-stu-id="68955-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="68955-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="68955-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

