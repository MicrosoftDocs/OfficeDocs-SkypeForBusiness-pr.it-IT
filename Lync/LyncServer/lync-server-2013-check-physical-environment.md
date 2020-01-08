---
title: "Lync Server 2013: controllare l'ambiente fisico"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07335046dc4b37d0e5327ded0a12293657f5fe43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="32710-102">Esecuzione di controlli ambientali fisici</span><span class="sxs-lookup"><span data-stu-id="32710-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32710-103">_**Argomento Ultima modifica:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="32710-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="32710-104">Prima di verificare le prestazioni, la disponibilità e la funzionalità della distribuzione di Lync Server 2013, è necessario controllare l'ambiente fisico.</span><span class="sxs-lookup"><span data-stu-id="32710-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="32710-105">Ad esempio, potrebbe essere necessario abbassare la temperatura ambiente del server oppure sostituire un cavo di rete.</span><span class="sxs-lookup"><span data-stu-id="32710-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="32710-106">Per ottenere risultati ottimali, eseguire i controlli ambientali fisici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32710-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="32710-107">**Misure di sicurezza fisica**   la protezione della sicurezza fisica, ad esempio blocchi, porte e sale con accesso limitato, deve essere protetta.</span><span class="sxs-lookup"><span data-stu-id="32710-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="32710-108">Verificare che non siano presenti voci non autorizzate e forzate e segni di danni alle attrezzature.</span><span class="sxs-lookup"><span data-stu-id="32710-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="32710-109">**Temperatura e umidità**   la temperatura elevata, il flusso d'aria scadente e l'umidità possono causare il surriscaldamento del componente hardware.</span><span class="sxs-lookup"><span data-stu-id="32710-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="32710-110">Verificare la temperatura e l'umidità per garantire che i sistemi ambientali come il riscaldamento e l'aria condizionata possano mantenere condizioni e funzioni accettabili nelle specifiche del produttore hardware.</span><span class="sxs-lookup"><span data-stu-id="32710-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="32710-111">Quando è stata installata una nuova apparecchiatura, verificare anche che il flusso d'aria sia da e verso i server sia senza ostacoli e soddisfi le specifiche del produttore.</span><span class="sxs-lookup"><span data-stu-id="32710-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="32710-112">**Dispositivi e componenti**   l'organizzazione di Lync Server 2013 si basa su una rete fisica funzionante e un hardware correlato.</span><span class="sxs-lookup"><span data-stu-id="32710-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="32710-113">Verificare che i router, gli interruttori, gli hub, i cavi fisici e i connettori siano operativi.</span><span class="sxs-lookup"><span data-stu-id="32710-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="32710-114">Le informazioni specifiche su come eseguire questi controlli dipendono molto dal sito di installazione e dall'hardware del server scelto.</span><span class="sxs-lookup"><span data-stu-id="32710-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="32710-115">La prima volta che si esegue questo controllo, vedere la documentazione hardware e prendere nota dei parametri desiderati per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="32710-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="32710-116">Ambiente di spazio server desiderato</span><span class="sxs-lookup"><span data-stu-id="32710-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32710-117">Parametro</span><span class="sxs-lookup"><span data-stu-id="32710-117">Parameter</span></span></th>
<th><span data-ttu-id="32710-118">Valore o intervallo desiderato</span><span class="sxs-lookup"><span data-stu-id="32710-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32710-119">Temperatura</span><span class="sxs-lookup"><span data-stu-id="32710-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32710-120">Umidità</span><span class="sxs-lookup"><span data-stu-id="32710-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32710-121">Fronte alle facce del server</span><span class="sxs-lookup"><span data-stu-id="32710-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="32710-122">Corridoio caldo/corridoio freddo</span><span class="sxs-lookup"><span data-stu-id="32710-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32710-123">Spazio di scarico senza ostacoli</span><span class="sxs-lookup"><span data-stu-id="32710-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

