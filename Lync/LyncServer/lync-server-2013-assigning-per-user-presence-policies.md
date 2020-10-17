---
title: 'Lync Server 2013: assegnazione dei criteri di presenza per utente'
description: 'Lync Server 2013: assegnazione dei criteri di presenza per utente.'
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
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563372"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="9296f-103">Assegnazione di criteri di presenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9296f-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9296f-104">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="9296f-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="9296f-105">Per criteri di presenza si intende un insieme di limiti e restrizioni che influiscono sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="9296f-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="9296f-106">Nella tabella seguente vengono descritte le impostazioni dei criteri di presenza disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9296f-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="9296f-107">Impostazioni dei criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="9296f-107">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="9296f-108">Nome XML</span><span class="sxs-lookup"><span data-stu-id="9296f-108">XML name</span></span></th>
<th><span data-ttu-id="9296f-109">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="9296f-109">Display name</span></span></th>
<th><span data-ttu-id="9296f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9296f-110">Description</span></span></th>
<th><span data-ttu-id="9296f-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="9296f-111">Type</span></span></th>
<th><span data-ttu-id="9296f-112">Valore</span><span class="sxs-lookup"><span data-stu-id="9296f-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9296f-113">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="9296f-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="9296f-114">Numero massimo di sottoscrizioni di categoria dei sottoscrittori</span><span class="sxs-lookup"><span data-stu-id="9296f-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="9296f-p102">Limita il numero di sottoscrizioni di categoria dei sottoscrittori. Ad esempio, quando Communicator sottoscrive la presenza di un utente, ottiene una sottoscrizione di categoria per ogni categoria scheda contatto, dati del calendario, note, servizi e stato.</span><span class="sxs-lookup"><span data-stu-id="9296f-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="9296f-117">Un valore 0 indica che l'utente o l'oggetto contatto non può essere sottoscritto da altri.</span><span class="sxs-lookup"><span data-stu-id="9296f-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9296f-118">Questa impostazione può avere un impatto notevole sulle prestazioni se è impostata su un valore elevato e l'utente medio presenta un numero elevato di utenti che sottoscrivono la sua presenza.</span><span class="sxs-lookup"><span data-stu-id="9296f-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="9296f-119">Numero intero</span><span class="sxs-lookup"><span data-stu-id="9296f-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="9296f-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="9296f-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9296f-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="9296f-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="9296f-122">Numero massimo di avvisi di sottoscrizione presenza in coda</span><span class="sxs-lookup"><span data-stu-id="9296f-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="9296f-p103">Limita il numero di voci nella tabella dei sottoscrittori richiedenti che possono essere accodati per un dato utente. Ad esempio, quando l'utente A sottoscrive la presenza dell'utente B, l'utente B riceve una richiesta che indica che l'utente A ha sottoscritto l'utente B e viene creata una richiesta di accettazione nella tabella dei sottoscrittori richiedenti dell'utente B. Dopo che l'utente B accetta la sottoscrizione, la richiesta di accettazione viene rimossa dalla tabella dei sottoscrittori richiedenti dell'utente B.</span><span class="sxs-lookup"><span data-stu-id="9296f-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="9296f-127">Un valore 0 indica che all'utente non viene inviata alcuna richiesta quando qualcuno sottoscrive la sua presenza.</span><span class="sxs-lookup"><span data-stu-id="9296f-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="9296f-128">Numero intero o token</span><span class="sxs-lookup"><span data-stu-id="9296f-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="9296f-129">0-500</span><span class="sxs-lookup"><span data-stu-id="9296f-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9296f-130">Per impostazione predefinita, i **criteri** e il servizio predefiniti: i criteri di presenza **media** vengono installati quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9296f-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="9296f-131">Nella tabella seguente sono descritte le impostazioni specifiche dei due criteri di presenza.</span><span class="sxs-lookup"><span data-stu-id="9296f-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="9296f-132">Criterio di presenza</span><span class="sxs-lookup"><span data-stu-id="9296f-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9296f-133">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="9296f-133">Policy name</span></span></th>
<th><span data-ttu-id="9296f-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9296f-134">Description</span></span></th>
<th><span data-ttu-id="9296f-135">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="9296f-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="9296f-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="9296f-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9296f-137">Criterio predefinito</span><span class="sxs-lookup"><span data-stu-id="9296f-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="9296f-p105">Criterio per gli utenti tipici. Si tratta del criterio di presenza predefinito.</span><span class="sxs-lookup"><span data-stu-id="9296f-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="9296f-140">1000</span><span class="sxs-lookup"><span data-stu-id="9296f-140">1000</span></span></p></td>
<td><p><span data-ttu-id="9296f-141">200</span><span class="sxs-lookup"><span data-stu-id="9296f-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9296f-142">Servizio: Medio</span><span class="sxs-lookup"><span data-stu-id="9296f-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="9296f-143">Criterio per le applicazioni che richiedono più utenti che sottoscrivano la presenza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9296f-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="9296f-144">1000</span><span class="sxs-lookup"><span data-stu-id="9296f-144">1000</span></span></p></td>
<td><p><span data-ttu-id="9296f-145">0</span><span class="sxs-lookup"><span data-stu-id="9296f-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

