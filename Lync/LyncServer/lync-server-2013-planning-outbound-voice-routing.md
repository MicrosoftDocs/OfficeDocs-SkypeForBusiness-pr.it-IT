---
title: 'Lync Server 2013: Pianificazione del routing vocale in uscita'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d33fbe8d15b78bed9dd651cd7facf35a8249f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="c24a5-102">Pianificazione del routing vocale in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c24a5-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c24a5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c24a5-104">Il routing delle chiamate in uscita si applica alle chiamate destinate a un gateway PSTN (Public Switched Telephone Network), trunk o PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="c24a5-104">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX).</span></span> <span data-ttu-id="c24a5-105">Quando un utente effettua una chiamata, il server normalizza il numero di telefono in formato E. 164, se necessario, e tenta di associarlo a un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="c24a5-105">When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="c24a5-106">Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di chiamata fornita.</span><span class="sxs-lookup"><span data-stu-id="c24a5-106">If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string.</span></span> <span data-ttu-id="c24a5-107">La logica viene definita configurando le impostazioni del server descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c24a5-107">You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="c24a5-108">Impostazioni di routing delle chiamate in uscita di Lync Server</span><span class="sxs-lookup"><span data-stu-id="c24a5-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c24a5-109">Oggetto</span><span class="sxs-lookup"><span data-stu-id="c24a5-109">Object</span></span></th>
<th><span data-ttu-id="c24a5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c24a5-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c24a5-111">Dial Plan</span><span class="sxs-lookup"><span data-stu-id="c24a5-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="c24a5-112">Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c24a5-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c24a5-113">Regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="c24a5-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="c24a5-114">Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="c24a5-114">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="c24a5-115">La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui è stata chiamata e della persona o dell'oggetto contatto che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c24a5-115">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call.</span></span> <span data-ttu-id="c24a5-116">Un set di regole di normalizzazione associato a una determinata posizione costituisce un dial plan.</span><span class="sxs-lookup"><span data-stu-id="c24a5-116">A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c24a5-117">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="c24a5-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="c24a5-118">Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="c24a5-118">A voice policy associates one or more PSTN usage records with one user or a group of users.</span></span> <span data-ttu-id="c24a5-119">Un criterio vocale offre anche un elenco delle funzionalità di chiamata che è possibile abilitare o disabilitare.</span><span class="sxs-lookup"><span data-stu-id="c24a5-119">A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c24a5-120">Record utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="c24a5-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="c24a5-121">Un record di utilizzo PSTN specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c24a5-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c24a5-122">Route chiamata</span><span class="sxs-lookup"><span data-stu-id="c24a5-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="c24a5-123">Una route di chiamata associa i numeri di telefono di destinazione con tronchi particolari e record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="c24a5-123">A call route associates destination phone numbers with particular trunks and PSTN usage records.</span></span> <span data-ttu-id="c24a5-124">Un gateway PSTN è considerato un trunk.</span><span class="sxs-lookup"><span data-stu-id="c24a5-124">A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="c24a5-125">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c24a5-125">In This Section</span></span>

<span data-ttu-id="c24a5-126">Questa sezione contiene linee guida per la configurazione delle impostazioni del server di routing delle chiamate in uscita seguenti:</span><span class="sxs-lookup"><span data-stu-id="c24a5-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="c24a5-127">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="c24a5-128">Criteri vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="c24a5-129">Record utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="c24a5-130">Route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c24a5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c24a5-131">See Also</span></span>


[<span data-ttu-id="c24a5-132">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="c24a5-133">Connessioni SIP dirette in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24a5-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

