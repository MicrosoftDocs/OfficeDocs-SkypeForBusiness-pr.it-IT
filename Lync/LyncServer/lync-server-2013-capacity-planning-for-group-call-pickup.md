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
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="0487b-102">Pianificazione della capacità per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0487b-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0487b-103">_**Argomento Ultima modifica:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="0487b-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="0487b-104">La tabella seguente descrive il modello di utente di prelievo delle chiamate di gruppo che puoi usare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="0487b-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0487b-105">Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="0487b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="0487b-106">Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park, incluso il ritiro delle chiamate di gruppo, in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="0487b-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="0487b-107">Modello utente di raccolta chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="0487b-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0487b-108">Metrica</span><span class="sxs-lookup"><span data-stu-id="0487b-108">Metric</span></span></th>
<th><span data-ttu-id="0487b-109">Per pool Front-End (con 8 server front-end)</span><span class="sxs-lookup"><span data-stu-id="0487b-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="0487b-110">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0487b-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0487b-111">Numero di utenti consigliati per gruppo</span><span class="sxs-lookup"><span data-stu-id="0487b-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="0487b-112">50</span><span class="sxs-lookup"><span data-stu-id="0487b-112">50</span></span></p></td>
<td><p><span data-ttu-id="0487b-113">50</span><span class="sxs-lookup"><span data-stu-id="0487b-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0487b-114">Numero consigliato di gruppi</span><span class="sxs-lookup"><span data-stu-id="0487b-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="0487b-115">500</span><span class="sxs-lookup"><span data-stu-id="0487b-115">500</span></span></p></td>
<td><p><span data-ttu-id="0487b-116">60</span><span class="sxs-lookup"><span data-stu-id="0487b-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0487b-117">Numero massimo di utenti per pool abilitato per il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="0487b-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="0487b-118">25.000</span><span class="sxs-lookup"><span data-stu-id="0487b-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="0487b-119">3.000</span><span class="sxs-lookup"><span data-stu-id="0487b-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0487b-120">Tasso massimo delle chiamate in arrivo per il totale degli utenti abilitati per il ritiro delle chiamate di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="0487b-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="0487b-121">500</span><span class="sxs-lookup"><span data-stu-id="0487b-121">500</span></span></p></td>
<td><p><span data-ttu-id="0487b-122">60</span><span class="sxs-lookup"><span data-stu-id="0487b-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0487b-123">Tasso massimo delle chiamate recuperate dagli utenti con il ritiro delle chiamate di gruppo per pool al minuto</span><span class="sxs-lookup"><span data-stu-id="0487b-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="0487b-124">200</span><span class="sxs-lookup"><span data-stu-id="0487b-124">200</span></span></p></td>
<td><p><span data-ttu-id="0487b-125">25</span><span class="sxs-lookup"><span data-stu-id="0487b-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="0487b-126">Per i pool Front-end con meno di otto server front-end, calcolare le metriche linearmente.</span><span class="sxs-lookup"><span data-stu-id="0487b-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="0487b-127">Ad esempio, se il pool Front-End ha un server front-end, calcolare il carico massimo come 1/8 dei valori visualizzati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0487b-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="0487b-128">È possibile aumentare o ridurre il numero di utenti consigliati per ogni gruppo e numero di gruppi purché non venga superato il numero massimo di utenti per pool.</span><span class="sxs-lookup"><span data-stu-id="0487b-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="0487b-129">Ad esempio, il server Standard Edition può avere gruppi di 120 con 25 utenti per gruppo, perché il numero di utenti abilitati per il ritiro delle chiamate di gruppo è ancora all'interno del massimo del modello utente (ovvero 120 gruppi per 25 utenti è consentito agli utenti di 3.000 per il ritiro delle chiamate di gruppo).</span><span class="sxs-lookup"><span data-stu-id="0487b-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

