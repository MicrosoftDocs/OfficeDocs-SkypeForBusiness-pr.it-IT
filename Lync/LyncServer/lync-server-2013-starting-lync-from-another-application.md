---
title: "Lync Server 2013: avvio di Lync da un'altra applicazione"
description: "Lync Server 2013: avvio di Lync da un'altra applicazione."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd64b8b9f335638b54a0bf6473b5d159c97a0e7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562702"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="01168-103">Avvio di Lync da un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="01168-103">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01168-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="01168-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="01168-105">È possibile utilizzare i parametri della riga di comando per avviare rapidamente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="01168-105">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="01168-106">Ad esempio, se un utente fa clic su un numero di telefono in un'altra applicazione, l'applicazione può avviare un'istanza di Lync 2013 e avviare una chiamata a tale numero.</span><span class="sxs-lookup"><span data-stu-id="01168-106">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="01168-107">Lync 2013 è inoltre in grado di riconoscere un elenco delimitato da punti e virgola dei nomi di contatto per le conferenze con più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="01168-107">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="01168-108">Se Lync 2013 è configurato per l'accesso automatico all'avvio, l'avvio di Lync 2013 con i parametri della riga di comando consente di aprire la finestra principale di Lync.</span><span class="sxs-lookup"><span data-stu-id="01168-108">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="01168-109">Se Lync non è configurato per l'accesso automatico all'avvio, verrà visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="01168-109">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="01168-110">Nella tabella seguente vengono descritti i parametri disponibili.</span><span class="sxs-lookup"><span data-stu-id="01168-110">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="01168-111">Parametri Command-Line di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="01168-111">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01168-112">Extension</span><span class="sxs-lookup"><span data-stu-id="01168-112">Extension</span></span></th>
<th><span data-ttu-id="01168-113">Formato dei dati</span><span class="sxs-lookup"><span data-stu-id="01168-113">Format of Data</span></span></th>
<th><span data-ttu-id="01168-114">Azione</span><span class="sxs-lookup"><span data-stu-id="01168-114">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01168-115">Tel</span><span class="sxs-lookup"><span data-stu-id="01168-115">tel:</span></span></p></td>
<td><p><span data-ttu-id="01168-116">URI TEL</span><span class="sxs-lookup"><span data-stu-id="01168-116">tel URI</span></span></p></td>
<td><p><span data-ttu-id="01168-117">Apre la finestra di conversazione per una chiamata audio, ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="01168-117">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01168-118">CALLTO</span><span class="sxs-lookup"><span data-stu-id="01168-118">callto:</span></span></p></td>
<td><p><span data-ttu-id="01168-119">tel:, sip: o URI TEL digitabile</span><span class="sxs-lookup"><span data-stu-id="01168-119">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="01168-120">Apre la finestra di conversazione per una chiamata audio, ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="01168-120">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01168-121">SIP</span><span class="sxs-lookup"><span data-stu-id="01168-121">sip:</span></span></p></td>
<td><p><span data-ttu-id="01168-122">URI SIP</span><span class="sxs-lookup"><span data-stu-id="01168-122">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="01168-123">Apre la finestra di conversazione con l'URI (Uniform Resource Identifier) SIP specificato nell'elenco dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="01168-123">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01168-124">Sorsi</span><span class="sxs-lookup"><span data-stu-id="01168-124">Sips:</span></span></p></td>
<td><p><span data-ttu-id="01168-125">URI SIP</span><span class="sxs-lookup"><span data-stu-id="01168-125">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="01168-126">Se Lync 2013 è configurato per l'utilizzo del protocollo TLS (Transport Layer Security), funziona esattamente come SIP:.</span><span class="sxs-lookup"><span data-stu-id="01168-126">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="01168-127">Se non si utilizza TLS, viene visualizzata una finestra di dialogo per informare l'utente che è necessario un livello di sicurezza più elevato.</span><span class="sxs-lookup"><span data-stu-id="01168-127">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01168-128">conf</span><span class="sxs-lookup"><span data-stu-id="01168-128">conf:</span></span></p></td>
<td><p><span data-ttu-id="01168-129">URI SIP della conferenza a cui partecipare</span><span class="sxs-lookup"><span data-stu-id="01168-129">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="01168-p104">Se l'URI è self, crea un'istanza del componente Focus e attiva la visualizzazione solo dell'elenco dei partecipanti. In caso contrario, attiva la visualizzazione dell'elenco dei partecipanti ma non invia una richiesta INVITE.</span><span class="sxs-lookup"><span data-stu-id="01168-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01168-132">im</span><span class="sxs-lookup"><span data-stu-id="01168-132">im:</span></span></p></td>
<td><p><span data-ttu-id="01168-133">URI SIP</span><span class="sxs-lookup"><span data-stu-id="01168-133">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="01168-134">Visualizza una finestra di conversazione solo per la messaggistica istantanea con l'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="01168-134">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="01168-135">Accetta più URI SIP specificati all'interno delle parentesi angolari ( &lt; &gt; ) senza alcun separatore.</span><span class="sxs-lookup"><span data-stu-id="01168-135">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="01168-136">Nella tabella seguente sono disponibili esempi di questi parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="01168-136">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="01168-137">Esempi di parametri della riga di comando</span><span class="sxs-lookup"><span data-stu-id="01168-137">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01168-138">Istanza</span><span class="sxs-lookup"><span data-stu-id="01168-138">Instance</span></span></th>
<th><span data-ttu-id="01168-139">Risultati</span><span class="sxs-lookup"><span data-stu-id="01168-139">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01168-140">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="01168-140">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="01168-141">Apre una visualizzazione solo telefonica con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="01168-141">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01168-142">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="01168-142">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="01168-143">Apre una visualizzazione solo telefonica con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="01168-143">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01168-144">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="01168-144">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="01168-145">Apre una visualizzazione solo telefonica con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="01168-145">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01168-146">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="01168-146">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="01168-147">Apre una finestra di conversazione con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="01168-147">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01168-148">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="01168-148">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="01168-149">Apre una finestra di conversazione e visualizza le opzioni di partecipazione all'audio della riunione.</span><span class="sxs-lookup"><span data-stu-id="01168-149">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

