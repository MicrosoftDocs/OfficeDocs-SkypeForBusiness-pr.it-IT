---
title: "Lync Server 2013: controllare l'ambiente fisico"
description: "Lync Server 2013: controllare l'ambiente fisico."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d963485b109e0afdf21b3a9085fa28884dfc3100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543552"
---
# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="c4895-103">Esecuzione di controlli ambientali fisici</span><span class="sxs-lookup"><span data-stu-id="c4895-103">Performing physical environmental checks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4895-104">_**Ultimo argomento modificato:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="c4895-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="c4895-105">Prima di verificare le prestazioni, la disponibilità e la funzionalità della distribuzione di Lync Server 2013, è necessario controllare l'ambiente fisico.</span><span class="sxs-lookup"><span data-stu-id="c4895-105">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="c4895-106">Ad esempio, potrebbe essere necessario abbassare la temperatura ambiente del server o potrebbe essere necessario sostituire un cavo di rete.</span><span class="sxs-lookup"><span data-stu-id="c4895-106">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="c4895-107">Per ottenere risultati ottimali, eseguire i seguenti controlli fisici sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="c4895-107">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="c4895-108">Misure di sicurezza **fisica**     La protezione della sicurezza fisica, ad esempio blocchi, porte e sale con accesso limitato, deve essere protetta.</span><span class="sxs-lookup"><span data-stu-id="c4895-108">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="c4895-109">Controllare eventuali accessi forzati non autorizzati e segni di danni alle attrezzature.</span><span class="sxs-lookup"><span data-stu-id="c4895-109">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="c4895-110">**Temperatura e umidità**     Temperature elevate, scarso flusso d'aria e umidità possono causare il surriscaldamento del componente hardware.</span><span class="sxs-lookup"><span data-stu-id="c4895-110">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="c4895-111">Controllare la temperatura e l'umidità per contribuire a garantire che i sistemi ambientali come il riscaldamento e l'aria condizionata possano mantenere le condizioni e le funzioni accettabili all'interno delle specifiche del produttore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="c4895-111">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="c4895-112">Quando sono state installate nuove apparecchiature, controllare anche che il flusso dell'aria sia da e verso i server sia senza ostacoli e soddisfi le specifiche del produttore.</span><span class="sxs-lookup"><span data-stu-id="c4895-112">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="c4895-113">**Dispositivi e componenti**     L'organizzazione Lync Server 2013 si basa su una rete fisica funzionante e sull'hardware correlato.</span><span class="sxs-lookup"><span data-stu-id="c4895-113">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="c4895-114">Verificare che i router, gli interruttori, gli hub, i cavi fisici e i connettori siano operativi.</span><span class="sxs-lookup"><span data-stu-id="c4895-114">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="c4895-115">Le specifiche su come eseguire questi controlli dipendono notevolmente dal sito di installazione e dall'hardware del server scelto.</span><span class="sxs-lookup"><span data-stu-id="c4895-115">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="c4895-116">La prima volta che si esegue questa verifica, fare riferimento alla documentazione relativa all'hardware e prendere nota dei parametri desiderati per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="c4895-116">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="c4895-117">Ambiente server Space desiderato</span><span class="sxs-lookup"><span data-stu-id="c4895-117">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4895-118">Parametro</span><span class="sxs-lookup"><span data-stu-id="c4895-118">Parameter</span></span></th>
<th><span data-ttu-id="c4895-119">Valore o intervallo desiderato</span><span class="sxs-lookup"><span data-stu-id="c4895-119">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4895-120">Temperatura</span><span class="sxs-lookup"><span data-stu-id="c4895-120">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4895-121">Umidità</span><span class="sxs-lookup"><span data-stu-id="c4895-121">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4895-122">Fronte delle facce del server</span><span class="sxs-lookup"><span data-stu-id="c4895-122">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="c4895-123">Navata calda/navata fredda</span><span class="sxs-lookup"><span data-stu-id="c4895-123">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4895-124">Spazio di scarico senza ostacoli</span><span class="sxs-lookup"><span data-stu-id="c4895-124">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

