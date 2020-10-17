---
title: 'Lync Server 2013: pianificazione della capacità per il ritiro delle chiamate di gruppo'
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
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512813"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f34f0-102">Pianificazione della capacità per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f34f0-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f34f0-103">_**Ultimo argomento modificato:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="f34f0-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f34f0-104">Nella tabella seguente viene descritto il modello utente di prelievo delle chiamate di gruppo che è possibile utilizzare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="f34f0-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f34f0-105">Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f34f0-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f34f0-106">Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi del parcheggio di chiamata, incluso il prelievo delle chiamate di gruppo, in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="f34f0-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="f34f0-107">Modello utente di prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="f34f0-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f34f0-108">Metrica</span><span class="sxs-lookup"><span data-stu-id="f34f0-108">Metric</span></span></th>
<th><span data-ttu-id="f34f0-109">Per pool Front End (con 8 Front End Server)</span><span class="sxs-lookup"><span data-stu-id="f34f0-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="f34f0-110">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f34f0-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f34f0-111">Numero consigliato di utenti per gruppo</span><span class="sxs-lookup"><span data-stu-id="f34f0-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="f34f0-112">50</span><span class="sxs-lookup"><span data-stu-id="f34f0-112">50</span></span></p></td>
<td><p><span data-ttu-id="f34f0-113">50</span><span class="sxs-lookup"><span data-stu-id="f34f0-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f34f0-114">Numero consigliato di gruppi</span><span class="sxs-lookup"><span data-stu-id="f34f0-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="f34f0-115">500</span><span class="sxs-lookup"><span data-stu-id="f34f0-115">500</span></span></p></td>
<td><p><span data-ttu-id="f34f0-116">60</span><span class="sxs-lookup"><span data-stu-id="f34f0-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f34f0-117">Numero massimo di utenti per pool abilitato per il prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="f34f0-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="f34f0-118">25.000</span><span class="sxs-lookup"><span data-stu-id="f34f0-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="f34f0-119">3.000</span><span class="sxs-lookup"><span data-stu-id="f34f0-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f34f0-120">Velocità massima delle chiamate in arrivo per il numero totale di utenti abilitati per il prelievo delle chiamate di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="f34f0-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f34f0-121">500</span><span class="sxs-lookup"><span data-stu-id="f34f0-121">500</span></span></p></td>
<td><p><span data-ttu-id="f34f0-122">60</span><span class="sxs-lookup"><span data-stu-id="f34f0-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f34f0-123">Velocità massima delle chiamate recuperate dagli utenti con il prelievo di chiamata di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="f34f0-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f34f0-124">200</span><span class="sxs-lookup"><span data-stu-id="f34f0-124">200</span></span></p></td>
<td><p><span data-ttu-id="f34f0-125">25</span><span class="sxs-lookup"><span data-stu-id="f34f0-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f34f0-126">Per i pool Front end con meno di otto Front End Server, calcolare le metriche linearmente.</span><span class="sxs-lookup"><span data-stu-id="f34f0-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="f34f0-127">Ad esempio, se il pool Front End ha un front end server, calcolare il carico massimo come 1/8 dei valori riportati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="f34f0-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="f34f0-128">È possibile aumentare o diminuire il numero consigliato di utenti per gruppo e numero di gruppi finché non si supera il numero massimo di utenti per pool.</span><span class="sxs-lookup"><span data-stu-id="f34f0-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="f34f0-129">Ad esempio, il server Standard Edition può avere 120 gruppi con 25 utenti per gruppo, perché il numero di utenti abilitati per il prelievo delle chiamate di gruppo è ancora all'interno del massimo modello utente (ovvero 120 gruppi per 25 utenti è 3.000 utenti abilitati per il ritiro delle chiamate di gruppo).</span><span class="sxs-lookup"><span data-stu-id="f34f0-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

