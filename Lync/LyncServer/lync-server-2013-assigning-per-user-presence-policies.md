---
title: 'Lync Server 2013: assegnazione dei criteri di presenza per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527123"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="fdba7-102">Assegnazione di criteri di presenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdba7-102">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdba7-103">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="fdba7-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="fdba7-104">Per criteri di presenza si intende un insieme di limiti e restrizioni che influiscono sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="fdba7-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="fdba7-105">Nella tabella seguente vengono descritte le impostazioni dei criteri di presenza disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdba7-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="fdba7-106">Impostazioni dei criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="fdba7-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdba7-107">Nome XML</span><span class="sxs-lookup"><span data-stu-id="fdba7-107">XML name</span></span></th>
<th><span data-ttu-id="fdba7-108">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="fdba7-108">Display name</span></span></th>
<th><span data-ttu-id="fdba7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdba7-109">Description</span></span></th>
<th><span data-ttu-id="fdba7-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="fdba7-110">Type</span></span></th>
<th><span data-ttu-id="fdba7-111">Valore</span><span class="sxs-lookup"><span data-stu-id="fdba7-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdba7-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="fdba7-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="fdba7-113">Numero massimo di sottoscrizioni di categoria dei sottoscrittori</span><span class="sxs-lookup"><span data-stu-id="fdba7-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="fdba7-p102">Limita il numero di sottoscrizioni di categoria dei sottoscrittori. Ad esempio, quando Communicator sottoscrive la presenza di un utente, ottiene una sottoscrizione di categoria per ogni categoria scheda contatto, dati del calendario, note, servizi e stato.</span><span class="sxs-lookup"><span data-stu-id="fdba7-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="fdba7-116">Un valore 0 indica che l'utente o l'oggetto contatto non può essere sottoscritto da altri.</span><span class="sxs-lookup"><span data-stu-id="fdba7-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fdba7-117">Questa impostazione può avere un impatto notevole sulle prestazioni se è impostata su un valore elevato e l'utente medio presenta un numero elevato di utenti che sottoscrivono la sua presenza.</span><span class="sxs-lookup"><span data-stu-id="fdba7-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="fdba7-118">Numero intero</span><span class="sxs-lookup"><span data-stu-id="fdba7-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="fdba7-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="fdba7-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdba7-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="fdba7-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="fdba7-121">Numero massimo di avvisi di sottoscrizione presenza in coda</span><span class="sxs-lookup"><span data-stu-id="fdba7-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="fdba7-p103">Limita il numero di voci nella tabella dei sottoscrittori richiedenti che possono essere accodati per un dato utente. Ad esempio, quando l'utente A sottoscrive la presenza dell'utente B, l'utente B riceve una richiesta che indica che l'utente A ha sottoscritto l'utente B e viene creata una richiesta di accettazione nella tabella dei sottoscrittori richiedenti dell'utente B. Dopo che l'utente B accetta la sottoscrizione, la richiesta di accettazione viene rimossa dalla tabella dei sottoscrittori richiedenti dell'utente B.</span><span class="sxs-lookup"><span data-stu-id="fdba7-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="fdba7-126">Un valore 0 indica che all'utente non viene inviata alcuna richiesta quando qualcuno sottoscrive la sua presenza.</span><span class="sxs-lookup"><span data-stu-id="fdba7-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="fdba7-127">Numero intero o token</span><span class="sxs-lookup"><span data-stu-id="fdba7-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="fdba7-128">0-500</span><span class="sxs-lookup"><span data-stu-id="fdba7-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fdba7-129">Per impostazione predefinita, i **criteri** e il servizio predefiniti: i criteri di presenza **media** vengono installati quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdba7-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="fdba7-130">Nella tabella seguente sono descritte le impostazioni specifiche dei due criteri di presenza.</span><span class="sxs-lookup"><span data-stu-id="fdba7-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="fdba7-131">Criterio di presenza</span><span class="sxs-lookup"><span data-stu-id="fdba7-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdba7-132">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="fdba7-132">Policy name</span></span></th>
<th><span data-ttu-id="fdba7-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdba7-133">Description</span></span></th>
<th><span data-ttu-id="fdba7-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="fdba7-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="fdba7-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="fdba7-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdba7-136">Criterio predefinito</span><span class="sxs-lookup"><span data-stu-id="fdba7-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="fdba7-p105">Criterio per gli utenti tipici. Si tratta del criterio di presenza predefinito.</span><span class="sxs-lookup"><span data-stu-id="fdba7-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="fdba7-139">1000</span><span class="sxs-lookup"><span data-stu-id="fdba7-139">1000</span></span></p></td>
<td><p><span data-ttu-id="fdba7-140">200</span><span class="sxs-lookup"><span data-stu-id="fdba7-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdba7-141">Servizio: Medio</span><span class="sxs-lookup"><span data-stu-id="fdba7-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="fdba7-142">Criterio per le applicazioni che richiedono più utenti che sottoscrivano la presenza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fdba7-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="fdba7-143">1000</span><span class="sxs-lookup"><span data-stu-id="fdba7-143">1000</span></span></p></td>
<td><p><span data-ttu-id="fdba7-144">0</span><span class="sxs-lookup"><span data-stu-id="fdba7-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

