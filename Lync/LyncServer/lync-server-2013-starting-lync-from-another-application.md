---
title: "Lync Server 2013: avvio di Lync da un'altra applicazione"
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
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519513"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="2fb7b-102">Avvio di Lync da un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="2fb7b-102">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fb7b-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2fb7b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2fb7b-104">È possibile utilizzare i parametri della riga di comando per avviare rapidamente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="2fb7b-105">Ad esempio, se un utente fa clic su un numero di telefono in un'altra applicazione, l'applicazione può avviare un'istanza di Lync 2013 e avviare una chiamata a tale numero.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="2fb7b-106">Lync 2013 è inoltre in grado di riconoscere un elenco delimitato da punti e virgola dei nomi di contatto per le conferenze con più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="2fb7b-107">Se Lync 2013 è configurato per l'accesso automatico all'avvio, l'avvio di Lync 2013 con i parametri della riga di comando consente di aprire la finestra principale di Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="2fb7b-108">Se Lync non è configurato per l'accesso automatico all'avvio, verrà visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="2fb7b-109">Nella tabella seguente vengono descritti i parametri disponibili.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="2fb7b-110">Parametri Command-Line di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2fb7b-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb7b-111">Extension</span><span class="sxs-lookup"><span data-stu-id="2fb7b-111">Extension</span></span></th>
<th><span data-ttu-id="2fb7b-112">Formato dei dati</span><span class="sxs-lookup"><span data-stu-id="2fb7b-112">Format of Data</span></span></th>
<th><span data-ttu-id="2fb7b-113">Azione</span><span class="sxs-lookup"><span data-stu-id="2fb7b-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-114">Tel</span><span class="sxs-lookup"><span data-stu-id="2fb7b-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-115">URI TEL</span><span class="sxs-lookup"><span data-stu-id="2fb7b-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-116">Apre la finestra di conversazione per una chiamata audio, ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb7b-117">CALLTO</span><span class="sxs-lookup"><span data-stu-id="2fb7b-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-118">tel:, sip: o URI TEL digitabile</span><span class="sxs-lookup"><span data-stu-id="2fb7b-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-119">Apre la finestra di conversazione per una chiamata audio, ma non compone il numero specificato.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-120">SIP</span><span class="sxs-lookup"><span data-stu-id="2fb7b-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-121">URI SIP</span><span class="sxs-lookup"><span data-stu-id="2fb7b-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-122">Apre la finestra di conversazione con l'URI (Uniform Resource Identifier) SIP specificato nell'elenco dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb7b-123">Sorsi</span><span class="sxs-lookup"><span data-stu-id="2fb7b-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-124">URI SIP</span><span class="sxs-lookup"><span data-stu-id="2fb7b-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-125">Se Lync 2013 è configurato per l'utilizzo del protocollo TLS (Transport Layer Security), funziona esattamente come SIP:.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="2fb7b-126">Se non si utilizza TLS, viene visualizzata una finestra di dialogo per informare l'utente che è necessario un livello di sicurezza più elevato.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-127">conf</span><span class="sxs-lookup"><span data-stu-id="2fb7b-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-128">URI SIP della conferenza a cui partecipare</span><span class="sxs-lookup"><span data-stu-id="2fb7b-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-p104">Se l'URI è self, crea un'istanza del componente Focus e attiva la visualizzazione solo dell'elenco dei partecipanti. In caso contrario, attiva la visualizzazione dell'elenco dei partecipanti ma non invia una richiesta INVITE.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb7b-131">im</span><span class="sxs-lookup"><span data-stu-id="2fb7b-131">im:</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-132">URI SIP</span><span class="sxs-lookup"><span data-stu-id="2fb7b-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-133">Visualizza una finestra di conversazione solo per la messaggistica istantanea con l'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="2fb7b-134">Accetta più URI SIP specificati all'interno delle parentesi angolari ( &lt; &gt; ) senza alcun separatore.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2fb7b-135">Nella tabella seguente sono disponibili esempi di questi parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="2fb7b-136">Esempi di parametri della riga di comando</span><span class="sxs-lookup"><span data-stu-id="2fb7b-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb7b-137">Istanza</span><span class="sxs-lookup"><span data-stu-id="2fb7b-137">Instance</span></span></th>
<th><span data-ttu-id="2fb7b-138">Risultati</span><span class="sxs-lookup"><span data-stu-id="2fb7b-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="2fb7b-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-140">Apre una visualizzazione solo telefonica con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb7b-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="2fb7b-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-142">Apre una visualizzazione solo telefonica con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2fb7b-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-144">Apre una visualizzazione solo telefonica con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb7b-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2fb7b-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-146">Apre una finestra di conversazione con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb7b-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="2fb7b-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="2fb7b-148">Apre una finestra di conversazione e visualizza le opzioni di partecipazione all'audio della riunione.</span><span class="sxs-lookup"><span data-stu-id="2fb7b-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

