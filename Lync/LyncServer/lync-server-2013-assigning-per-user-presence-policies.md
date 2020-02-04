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
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="a9a5d-102">Assegnazione di criteri di presenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a5d-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a5d-103">_**Argomento Ultima modifica:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a9a5d-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="a9a5d-104">Un criterio di presenza è un insieme di limiti e restrizioni che influiscono sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="a9a5d-105">La tabella seguente descrive le impostazioni dei criteri di presenza disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="a9a5d-106">Impostazioni dei criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="a9a5d-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="a9a5d-107">Nome XML</span><span class="sxs-lookup"><span data-stu-id="a9a5d-107">XML name</span></span></th>
<th><span data-ttu-id="a9a5d-108">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="a9a5d-108">Display name</span></span></th>
<th><span data-ttu-id="a9a5d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9a5d-109">Description</span></span></th>
<th><span data-ttu-id="a9a5d-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="a9a5d-110">Type</span></span></th>
<th><span data-ttu-id="a9a5d-111">Valore</span><span class="sxs-lookup"><span data-stu-id="a9a5d-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9a5d-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="a9a5d-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-113">Numero massimo di abbonamenti alle categorie del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="a9a5d-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-114">Limita il numero di abbonamenti alle categorie di abbonati.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="a9a5d-115">Ad esempio, quando Communicator sottoscrive la presenza di un utente, ottiene un abbonamento a categoria per ogni scheda contatto, dati del calendario, note, servizi e categorie di stato.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="a9a5d-116">Un'impostazione pari a 0 indica che l'utente o l'oggetto contatto non può essere sottoscritto da altri.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a9a5d-117">Questa impostazione può avere un impatto significativo sulle prestazioni se è impostata su un numero alto e l'utente medio ha un numero elevato di utenti che si abbonano alla propria presenza.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="a9a5d-118">Numero intero</span><span class="sxs-lookup"><span data-stu-id="a9a5d-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="a9a5d-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a5d-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="a9a5d-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-121">Numero massimo di avvisi per gli abbonamenti alla presenza in coda</span><span class="sxs-lookup"><span data-stu-id="a9a5d-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-122">Limita il numero di voci nella tabella abbonati richiesto.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="a9a5d-123">Questa impostazione determina il numero massimo di richieste che possono essere accodate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="a9a5d-124">Ad esempio, quando un utente sottoscrive la presenza dell'utente B, l'utente B riceverà una richiesta di conferma che l'utente a è ora abbonato all'utente B e viene creata una richiesta di conferma nella tabella sottoscrittori richiesto dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="a9a5d-125">Dopo che l'utente B accetta o riconosce l'abbonamento, la richiesta di conferma viene rimossa dalla tabella sottoscrittori richiesta dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="a9a5d-126">Un'impostazione pari a 0 indica che l'utente non viene visualizzato quando qualcuno sottoscrive la propria presenza.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-127">Numero intero o token</span><span class="sxs-lookup"><span data-stu-id="a9a5d-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-128">0-500</span><span class="sxs-lookup"><span data-stu-id="a9a5d-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9a5d-129">Per impostazione predefinita, i **criteri** e il servizio predefiniti: i criteri di presenza **media** vengono installati quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="a9a5d-130">La tabella seguente descrive le impostazioni specifiche dei due criteri di presenza.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="a9a5d-131">Criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="a9a5d-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9a5d-132">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="a9a5d-132">Policy name</span></span></th>
<th><span data-ttu-id="a9a5d-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9a5d-133">Description</span></span></th>
<th><span data-ttu-id="a9a5d-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="a9a5d-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="a9a5d-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="a9a5d-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9a5d-136">Criteri predefiniti</span><span class="sxs-lookup"><span data-stu-id="a9a5d-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-137">Criteri per gli utenti tipici.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-137">Policy for typical users.</span></span> <span data-ttu-id="a9a5d-138">Questo è il criterio di presenza predefinito.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-139">1000</span><span class="sxs-lookup"><span data-stu-id="a9a5d-139">1000</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-140">200</span><span class="sxs-lookup"><span data-stu-id="a9a5d-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a5d-141">Servizio: media</span><span class="sxs-lookup"><span data-stu-id="a9a5d-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-142">Criteri per le applicazioni che richiedono ad altri utenti di sottoscrivere la presenza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a9a5d-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-143">1000</span><span class="sxs-lookup"><span data-stu-id="a9a5d-143">1000</span></span></p></td>
<td><p><span data-ttu-id="a9a5d-144">0</span><span class="sxs-lookup"><span data-stu-id="a9a5d-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

