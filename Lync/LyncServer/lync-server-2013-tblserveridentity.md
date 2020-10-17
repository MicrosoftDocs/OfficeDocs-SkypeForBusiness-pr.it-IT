---
title: 'Lync Server 2013: tabella tblServerIdentity'
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
ms.openlocfilehash: 206efe412712d2acb311b951bd0554bed3c9f650
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536233"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="f6e3c-102">Tabella tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6e3c-102">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6e3c-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f6e3c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f6e3c-104">Tabella tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="f6e3c-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="f6e3c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e3c-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="f6e3c-106">Column</span></span></th>
<th><span data-ttu-id="f6e3c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f6e3c-107">Type</span></span></th>
<th><span data-ttu-id="f6e3c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6e3c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e3c-109">serverID</span><span class="sxs-lookup"><span data-stu-id="f6e3c-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f6e3c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-111">ID del server.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-111">Server ID.</span></span> <span data-ttu-id="f6e3c-112">Corrisponde all'ID istanza dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e3c-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="f6e3c-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="f6e3c-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-115">Indirizzo del server che usa l'indirizzo di Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e3c-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="f6e3c-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-117">datetime</span><span class="sxs-lookup"><span data-stu-id="f6e3c-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-118">Ora dell'ultimo aggiornamento di questa riga eseguito dal Channel Server per confermare che è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f6e3c-119">Chiave</span><span class="sxs-lookup"><span data-stu-id="f6e3c-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e3c-120">Colonna</span><span class="sxs-lookup"><span data-stu-id="f6e3c-120">Column</span></span></th>
<th><span data-ttu-id="f6e3c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6e3c-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e3c-122">serverID</span><span class="sxs-lookup"><span data-stu-id="f6e3c-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="f6e3c-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f6e3c-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

