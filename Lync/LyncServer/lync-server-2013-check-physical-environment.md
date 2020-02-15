---
title: "Lync Server 2013: controllare l'ambiente fisico"
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
ms.openlocfilehash: 6d8838336fbea4f901b763b7ca034f42e957de33
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="fcad4-102">Esecuzione di controlli ambientali fisici</span><span class="sxs-lookup"><span data-stu-id="fcad4-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcad4-103">_**Ultimo argomento modificato:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="fcad4-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="fcad4-104">Prima di verificare le prestazioni, la disponibilità e la funzionalità della distribuzione di Lync Server 2013, è necessario controllare l'ambiente fisico.</span><span class="sxs-lookup"><span data-stu-id="fcad4-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="fcad4-105">Ad esempio, potrebbe essere necessario abbassare la temperatura ambiente del server o potrebbe essere necessario sostituire un cavo di rete.</span><span class="sxs-lookup"><span data-stu-id="fcad4-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="fcad4-106">Per ottenere risultati ottimali, eseguire i seguenti controlli fisici sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="fcad4-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="fcad4-107">**Misure di sicurezza fisica**   è necessario proteggere la sicurezza fisica, ad esempio blocchi, porte e sale con accesso limitato.</span><span class="sxs-lookup"><span data-stu-id="fcad4-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="fcad4-108">Controllare eventuali accessi forzati non autorizzati e segni di danni alle attrezzature.</span><span class="sxs-lookup"><span data-stu-id="fcad4-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="fcad4-109">**Temperatura e umidità**   le temperature elevate, il flusso di aria scadente e l'umidità possono causare il surriscaldamento del componente hardware.</span><span class="sxs-lookup"><span data-stu-id="fcad4-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="fcad4-110">Controllare la temperatura e l'umidità per contribuire a garantire che i sistemi ambientali come il riscaldamento e l'aria condizionata possano mantenere le condizioni e le funzioni accettabili all'interno delle specifiche del produttore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="fcad4-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="fcad4-111">Quando sono state installate nuove apparecchiature, controllare anche che il flusso dell'aria sia da e verso i server sia senza ostacoli e soddisfi le specifiche del produttore.</span><span class="sxs-lookup"><span data-stu-id="fcad4-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="fcad4-112">**Dispositivi e componenti**   l'organizzazione di Lync Server 2013 si basa su una rete fisica funzionante e sull'hardware correlato.</span><span class="sxs-lookup"><span data-stu-id="fcad4-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="fcad4-113">Verificare che i router, gli interruttori, gli hub, i cavi fisici e i connettori siano operativi.</span><span class="sxs-lookup"><span data-stu-id="fcad4-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="fcad4-114">Le specifiche su come eseguire questi controlli dipendono notevolmente dal sito di installazione e dall'hardware del server scelto.</span><span class="sxs-lookup"><span data-stu-id="fcad4-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="fcad4-115">La prima volta che si esegue questa verifica, fare riferimento alla documentazione relativa all'hardware e prendere nota dei parametri desiderati per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="fcad4-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="fcad4-116">Ambiente server Space desiderato</span><span class="sxs-lookup"><span data-stu-id="fcad4-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcad4-117">Parametro</span><span class="sxs-lookup"><span data-stu-id="fcad4-117">Parameter</span></span></th>
<th><span data-ttu-id="fcad4-118">Valore o intervallo desiderato</span><span class="sxs-lookup"><span data-stu-id="fcad4-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcad4-119">Temperatura</span><span class="sxs-lookup"><span data-stu-id="fcad4-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcad4-120">Umidità</span><span class="sxs-lookup"><span data-stu-id="fcad4-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcad4-121">Fronte delle facce del server</span><span class="sxs-lookup"><span data-stu-id="fcad4-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="fcad4-122">Navata calda/navata fredda</span><span class="sxs-lookup"><span data-stu-id="fcad4-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcad4-123">Spazio di scarico senza ostacoli</span><span class="sxs-lookup"><span data-stu-id="fcad4-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

