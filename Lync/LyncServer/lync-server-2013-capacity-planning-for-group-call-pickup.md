---
title: 'Lync Server 2013: pianificazione della capacità per il ritiro delle chiamate di gruppo'
description: 'Lync Server 2013: pianificazione della capacità per il prelievo delle chiamate di gruppo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544532"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="049c8-103">Pianificazione della capacità per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="049c8-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="049c8-104">_**Ultimo argomento modificato:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="049c8-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="049c8-105">Nella tabella seguente viene descritto il modello utente di prelievo delle chiamate di gruppo che è possibile utilizzare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="049c8-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="049c8-106">Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="049c8-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="049c8-107">Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi del parcheggio di chiamata, incluso il prelievo delle chiamate di gruppo, in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="049c8-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="049c8-108">Modello utente di prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="049c8-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="049c8-109">Metrica</span><span class="sxs-lookup"><span data-stu-id="049c8-109">Metric</span></span></th>
<th><span data-ttu-id="049c8-110">Per pool Front End (con 8 Front End Server)</span><span class="sxs-lookup"><span data-stu-id="049c8-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="049c8-111">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="049c8-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="049c8-112">Numero consigliato di utenti per gruppo</span><span class="sxs-lookup"><span data-stu-id="049c8-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="049c8-113">50</span><span class="sxs-lookup"><span data-stu-id="049c8-113">50</span></span></p></td>
<td><p><span data-ttu-id="049c8-114">50</span><span class="sxs-lookup"><span data-stu-id="049c8-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049c8-115">Numero consigliato di gruppi</span><span class="sxs-lookup"><span data-stu-id="049c8-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="049c8-116">500</span><span class="sxs-lookup"><span data-stu-id="049c8-116">500</span></span></p></td>
<td><p><span data-ttu-id="049c8-117">60</span><span class="sxs-lookup"><span data-stu-id="049c8-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049c8-118">Numero massimo di utenti per pool abilitato per il prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="049c8-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="049c8-119">25.000</span><span class="sxs-lookup"><span data-stu-id="049c8-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="049c8-120">3.000</span><span class="sxs-lookup"><span data-stu-id="049c8-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049c8-121">Velocità massima delle chiamate in arrivo per il numero totale di utenti abilitati per il prelievo delle chiamate di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="049c8-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="049c8-122">500</span><span class="sxs-lookup"><span data-stu-id="049c8-122">500</span></span></p></td>
<td><p><span data-ttu-id="049c8-123">60</span><span class="sxs-lookup"><span data-stu-id="049c8-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049c8-124">Velocità massima delle chiamate recuperate dagli utenti con il prelievo di chiamata di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="049c8-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="049c8-125">200</span><span class="sxs-lookup"><span data-stu-id="049c8-125">200</span></span></p></td>
<td><p><span data-ttu-id="049c8-126">25</span><span class="sxs-lookup"><span data-stu-id="049c8-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="049c8-127">Per i pool Front end con meno di otto Front End Server, calcolare le metriche linearmente.</span><span class="sxs-lookup"><span data-stu-id="049c8-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="049c8-128">Ad esempio, se il pool Front End ha un front end server, calcolare il carico massimo come 1/8 dei valori riportati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="049c8-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="049c8-129">È possibile aumentare o diminuire il numero consigliato di utenti per gruppo e numero di gruppi finché non si supera il numero massimo di utenti per pool.</span><span class="sxs-lookup"><span data-stu-id="049c8-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="049c8-130">Ad esempio, il server Standard Edition può avere 120 gruppi con 25 utenti per gruppo, perché il numero di utenti abilitati per il prelievo delle chiamate di gruppo è ancora all'interno del massimo modello utente (ovvero 120 gruppi per 25 utenti è 3.000 utenti abilitati per il ritiro delle chiamate di gruppo).</span><span class="sxs-lookup"><span data-stu-id="049c8-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

