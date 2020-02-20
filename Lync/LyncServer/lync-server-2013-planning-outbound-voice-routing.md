---
title: 'Lync Server 2013: pianificazione del routing vocale in uscita'
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
ms.openlocfilehash: 4e912a3934ae7262c85cfb7b47c62abf6bc70b5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="c9e2d-102">Pianificazione del routing vocale in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e2d-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c9e2d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c9e2d-p101">Il routing delle chiamate in uscita viene applicato alle chiamate destinate a un gateway PSTN (Public Switched Telephone Network), al trunk o a un PBX (Private Branch Exchange). Quando un utente effettua una chiamata, il server normalizza il numero di telefono convertendolo nel formato E.164, se necessario, e tenta di associarlo a un URI SIP. Se il server non riesce a trovare una corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di composizione fornita. È possibile definire tale logica configurando le impostazioni del server descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="c9e2d-108">Impostazioni del server di routing delle chiamate in uscita Lync Server</span><span class="sxs-lookup"><span data-stu-id="c9e2d-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e2d-109">Oggetto</span><span class="sxs-lookup"><span data-stu-id="c9e2d-109">Object</span></span></th>
<th><span data-ttu-id="c9e2d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9e2d-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9e2d-111">Dial plan</span><span class="sxs-lookup"><span data-stu-id="c9e2d-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="c9e2d-112">Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e2d-113">Regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="c9e2d-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="c9e2d-p102">Le regole di normalizzazione definiscono come devono essere instradati numeri di telefono espressi in formati diversi per ogni località, utente oppure oggetto contatto specificato. La stessa stringa di composizione può essere interpretata e convertita in modo diverso a seconda della località da cui viene composta e della persona o dell'oggetto contatto che effettua la chiamata. Un insieme di regole di normalizzazione associate a una determinata località costituisce un dial plan.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e2d-117">Criterio vocale</span><span class="sxs-lookup"><span data-stu-id="c9e2d-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="c9e2d-p103">Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti. Un criterio vocale fornisce inoltre un elenco di funzionalità di chiamata che è possibile abilitare o disabilitare.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e2d-120">Record di utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="c9e2d-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="c9e2d-121">Un record di utilizzo PSTN specifica un tipo di chiamata (ad esempio interna, locale o interurbana) che può essere effettuata da diversi utenti o gruppi di utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e2d-122">Route di chiamata</span><span class="sxs-lookup"><span data-stu-id="c9e2d-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="c9e2d-p104">Una route di chiamata associa i numeri di telefono di destinazione a trunk e record di utilizzo PSTN specifici. Un gateway PSTN viene considerato un trunk.</span><span class="sxs-lookup"><span data-stu-id="c9e2d-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="c9e2d-125">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c9e2d-125">In This Section</span></span>

<span data-ttu-id="c9e2d-126">In questa sezione vengono fornite le linee guida per la configurazione delle impostazioni seguenti del server di routing delle chiamate in uscita:</span><span class="sxs-lookup"><span data-stu-id="c9e2d-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="c9e2d-127">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="c9e2d-128">Criteri vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="c9e2d-129">Record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="c9e2d-130">Route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9e2d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e2d-131">See Also</span></span>


[<span data-ttu-id="c9e2d-132">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="c9e2d-133">Connessioni SIP dirette in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e2d-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

