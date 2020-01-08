---
title: "Lync Server 2013: avvio di Lync da un'altra applicazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="f5f18-102">Avvio di Lync da un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="f5f18-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f18-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f5f18-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f5f18-104">È possibile usare i parametri della riga di comando per avviare rapidamente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f5f18-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="f5f18-105">Ad esempio, se un utente fa clic su un numero di telefono in un'altra applicazione, l'applicazione può avviare un'istanza di Lync 2013 e avviare una chiamata a tale numero.</span><span class="sxs-lookup"><span data-stu-id="f5f18-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="f5f18-106">Lync 2013 può anche riconoscere un elenco delimitato da punti e virgola di nomi di contatti per i servizi di conferenza multiparte.</span><span class="sxs-lookup"><span data-stu-id="f5f18-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="f5f18-107">Se Lync 2013 è configurato per l'accesso automatico all'avvio, l'avvio di Lync 2013 con i parametri della riga di comando consente di aprire la finestra principale di Lync.</span><span class="sxs-lookup"><span data-stu-id="f5f18-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="f5f18-108">Se Lync non è configurato per l'accesso automatico all'avvio, viene visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="f5f18-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="f5f18-109">La tabella seguente mostra i parametri disponibili.</span><span class="sxs-lookup"><span data-stu-id="f5f18-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="f5f18-110">Parametri della riga di comando di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f5f18-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f18-111">Estensione</span><span class="sxs-lookup"><span data-stu-id="f5f18-111">Extension</span></span></th>
<th><span data-ttu-id="f5f18-112">Formato dei dati</span><span class="sxs-lookup"><span data-stu-id="f5f18-112">Format of Data</span></span></th>
<th><span data-ttu-id="f5f18-113">Azione</span><span class="sxs-lookup"><span data-stu-id="f5f18-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-114">Tel</span><span class="sxs-lookup"><span data-stu-id="f5f18-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-115">URI tel</span><span class="sxs-lookup"><span data-stu-id="f5f18-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="f5f18-116">Apre la finestra di conversazione per una chiamata audio ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="f5f18-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f18-117">CALLTO</span><span class="sxs-lookup"><span data-stu-id="f5f18-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-118">Tel:, SIP: o URI di tipo Tel</span><span class="sxs-lookup"><span data-stu-id="f5f18-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="f5f18-119">Apre la finestra di conversazione per una chiamata audio ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="f5f18-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-120">SIP</span><span class="sxs-lookup"><span data-stu-id="f5f18-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-121">URI SIP</span><span class="sxs-lookup"><span data-stu-id="f5f18-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="f5f18-122">Apre la finestra di conversazione con l'URI (Uniform Resource Identifier) SIP specificato nell'elenco dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f5f18-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f18-123">Sorsi</span><span class="sxs-lookup"><span data-stu-id="f5f18-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-124">URI SIP</span><span class="sxs-lookup"><span data-stu-id="f5f18-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="f5f18-125">Se Lync 2013 è configurato per l'uso del protocollo Transport Layer Security (TLS), funziona esattamente come SIP:.</span><span class="sxs-lookup"><span data-stu-id="f5f18-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="f5f18-126">Se TLS non viene usato, Visualizza una finestra di dialogo che informa l'utente che è necessario un livello di sicurezza più elevato.</span><span class="sxs-lookup"><span data-stu-id="f5f18-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-127">conf</span><span class="sxs-lookup"><span data-stu-id="f5f18-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-128">URI SIP della conferenza a cui partecipare</span><span class="sxs-lookup"><span data-stu-id="f5f18-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="f5f18-129">Se URI è autonomo, crea un'istanza dello stato attiva e visualizza la visualizzazione solo elenco.</span><span class="sxs-lookup"><span data-stu-id="f5f18-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="f5f18-130">In caso contrario, porta in alto la visualizzazione roster ma non invia INVITE.</span><span class="sxs-lookup"><span data-stu-id="f5f18-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f18-131">messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="f5f18-131">im:</span></span></p></td>
<td><p><span data-ttu-id="f5f18-132">URI SIP</span><span class="sxs-lookup"><span data-stu-id="f5f18-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="f5f18-133">Consente di visualizzare una finestra di conversazione solo messaggistica istantanea con l'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="f5f18-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="f5f18-134">Accetta più URI SIP specificati all'interno di parentesi angolari (&lt;&gt;) senza alcun separatore.</span><span class="sxs-lookup"><span data-stu-id="f5f18-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5f18-135">La tabella seguente contiene alcuni esempi di questi parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f5f18-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="f5f18-136">Esempi di parametri della riga di comando</span><span class="sxs-lookup"><span data-stu-id="f5f18-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f18-137">Istanza</span><span class="sxs-lookup"><span data-stu-id="f5f18-137">Instance</span></span></th>
<th><span data-ttu-id="f5f18-138">Risultati</span><span class="sxs-lookup"><span data-stu-id="f5f18-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="f5f18-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="f5f18-140">Apre una visualizzazione solo telefono con + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="f5f18-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f18-141">Callto: Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="f5f18-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="f5f18-142">Apre una visualizzazione solo telefono con + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="f5f18-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5f18-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="f5f18-144">Apre una visualizzazione solo telefono con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5f18-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f18-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5f18-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="f5f18-146">Apre una finestra di conversazione con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5f18-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f18-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="f5f18-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="f5f18-148">Apre una finestra di conversazione e visualizza le opzioni di partecipazione audio della riunione.</span><span class="sxs-lookup"><span data-stu-id="f5f18-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

