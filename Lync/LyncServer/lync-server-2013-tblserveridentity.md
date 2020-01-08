---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bdd939f838a9f72191d3aae27b9a4a56d26be3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="bbdd6-102">tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbdd6-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbdd6-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bbdd6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bbdd6-104">tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="bbdd6-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="bbdd6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbdd6-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="bbdd6-106">Column</span></span></th>
<th><span data-ttu-id="bbdd6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="bbdd6-107">Type</span></span></th>
<th><span data-ttu-id="bbdd6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbdd6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbdd6-109">serverID</span><span class="sxs-lookup"><span data-stu-id="bbdd6-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="bbdd6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-111">ID server.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-111">Server ID.</span></span> <span data-ttu-id="bbdd6-112">Corrisponde all'ID istanza di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbdd6-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="bbdd6-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="bbdd6-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-115">Indirizzo del server tramite l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbdd6-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="bbdd6-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-117">DateTime</span><span class="sxs-lookup"><span data-stu-id="bbdd6-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-118">L'ultima volta che il Channel Server ha aggiornato questa riga per dare prova che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bbdd6-119">Chiave</span><span class="sxs-lookup"><span data-stu-id="bbdd6-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbdd6-120">Colonna</span><span class="sxs-lookup"><span data-stu-id="bbdd6-120">Column</span></span></th>
<th><span data-ttu-id="bbdd6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbdd6-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbdd6-122">serverID</span><span class="sxs-lookup"><span data-stu-id="bbdd6-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="bbdd6-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="bbdd6-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

