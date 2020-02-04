---
title: 'Lync Server 2013: report di diagnostica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="40be0-102">Report di diagnostica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40be0-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40be0-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="40be0-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="40be0-104">Il report di diagnostica fornisce informazioni di diagnostica e risoluzione dei problemi per una sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="40be0-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="40be0-105">Queste informazioni includono sia l'ID di diagnostica che l'intestazione di diagnostica segnalate quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="40be0-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="40be0-106">L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione associata per l'ID di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="40be0-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="40be0-107">Il report può anche contenere dettagli utili per la risoluzione dei problemi noti dal componente di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="40be0-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="40be0-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40be0-108">For example:</span></span>

  - <span data-ttu-id="40be0-109">Il codice di causa fornito dal gateway PSTN che ha generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="40be0-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="40be0-110">Quando una chiamata in uscita ha esito negativo nella rete PSTN, viene generato automaticamente un codice di causa ISDN User Part (ISUP).</span><span class="sxs-lookup"><span data-stu-id="40be0-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="40be0-111">Ad esempio, un gateway PSTN può inviare il codice di causa 34 per indicare che non è disponibile alcun circuito o canale per completare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="40be0-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="40be0-112">Errori di FQDN, porta e Winsock peer per i problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="40be0-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="40be0-113">Nomi cercati per gli errori di risoluzione DNS.</span><span class="sxs-lookup"><span data-stu-id="40be0-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="40be0-114">La risoluzione DNS viene applicata ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome del dispositivo specificato.</span><span class="sxs-lookup"><span data-stu-id="40be0-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="40be0-115">Accesso al report di diagnostica</span><span class="sxs-lookup"><span data-stu-id="40be0-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="40be0-116">È possibile accedere al report di diagnostica facendo clic sulla metrica rapporto di diagnostica (dettaglio) nel [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o nel report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="40be0-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="40be0-117">Filtri</span><span class="sxs-lookup"><span data-stu-id="40be0-117">Filters</span></span>

<span data-ttu-id="40be0-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="40be0-118">None.</span></span> <span data-ttu-id="40be0-119">Non è possibile filtrare il report di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="40be0-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="40be0-120">Metriche</span><span class="sxs-lookup"><span data-stu-id="40be0-120">Metrics</span></span>

<span data-ttu-id="40be0-121">Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="40be0-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="40be0-122">Metriche del report di diagnostica</span><span class="sxs-lookup"><span data-stu-id="40be0-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40be0-123">Nome</span><span class="sxs-lookup"><span data-stu-id="40be0-123">Name</span></span></th>
<th><span data-ttu-id="40be0-124">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="40be0-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="40be0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40be0-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40be0-126"><strong>Tempo di report</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-127">No</span><span class="sxs-lookup"><span data-stu-id="40be0-127">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-128">Data e ora in cui il report è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="40be0-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-129"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-130">No</span><span class="sxs-lookup"><span data-stu-id="40be0-130">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-131">Codice di risposta SIP inviato quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="40be0-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40be0-132"><strong>Tipo di richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-133">No</span><span class="sxs-lookup"><span data-stu-id="40be0-133">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-134">Tipo di richiesta SIP non riuscito.</span><span class="sxs-lookup"><span data-stu-id="40be0-134">SIP request type that failed.</span></span> <span data-ttu-id="40be0-135">Ad esempio, invita, BYE o SERVICE.</span><span class="sxs-lookup"><span data-stu-id="40be0-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-136"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-137">No</span><span class="sxs-lookup"><span data-stu-id="40be0-137">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-138">Origine dell'errore.</span><span class="sxs-lookup"><span data-stu-id="40be0-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40be0-139"><strong>Da URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-140">No</span><span class="sxs-lookup"><span data-stu-id="40be0-140">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-141">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="40be0-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-142"><strong>Dall'agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-143">No</span><span class="sxs-lookup"><span data-stu-id="40be0-143">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-144">Software usato dall'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="40be0-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40be0-145"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-146">No</span><span class="sxs-lookup"><span data-stu-id="40be0-146">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-147">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="40be0-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-148"><strong>Tipo di contenuto</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-149">No</span><span class="sxs-lookup"><span data-stu-id="40be0-149">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-150">Tipo di contenuto multimediale non riuscito.</span><span class="sxs-lookup"><span data-stu-id="40be0-150">Type of media content that failed.</span></span> <span data-ttu-id="40be0-151">Ad esempio, un tipo di contenuto comune è Application/sdp.</span><span class="sxs-lookup"><span data-stu-id="40be0-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="40be0-152">Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="40be0-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40be0-153"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-154">No</span><span class="sxs-lookup"><span data-stu-id="40be0-154">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-155">Applicazione coinvolta nell'errore.</span><span class="sxs-lookup"><span data-stu-id="40be0-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-156"><strong>All'URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-157">No</span><span class="sxs-lookup"><span data-stu-id="40be0-157">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-158">Indirizzo SIP dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="40be0-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40be0-159">Orari di partecipazione alla conferenza (MS)</span><span class="sxs-lookup"><span data-stu-id="40be0-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="40be0-160">No</span><span class="sxs-lookup"><span data-stu-id="40be0-160">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-161">Intervallo di tempo (in millisecondi) che l'utente ha impiegato per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="40be0-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40be0-162"><strong>Intestazione di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="40be0-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="40be0-163">No</span><span class="sxs-lookup"><span data-stu-id="40be0-163">No</span></span></p></td>
<td><p><span data-ttu-id="40be0-164">Descrizione dell'ID di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="40be0-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="40be0-165">Un elenco di errori di diagnostica può essere trovato nella [pagina di intestazione MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="40be0-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

