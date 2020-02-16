---
title: 'Lync Server 2013: rapporto di diagnostica'
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
ms.openlocfilehash: a906e131329df1b59c4ac6067a4696871f0bebfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="24b05-102">Rapporto di diagnostica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b05-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b05-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="24b05-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="24b05-104">Nel Rapporto di diagnostica vengono fornite informazioni per la diagnostica e la risoluzione dei problemi di una sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="24b05-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="24b05-105">Queste informazioni includono l'ID diagnostica e l'intestazione di diagnostica segnalati quando la sessione ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="24b05-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="24b05-106">L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione di tale ID.</span><span class="sxs-lookup"><span data-stu-id="24b05-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="24b05-107">Nel rapporto possono inoltre essere inclusi per la risoluzione dei problemi dettagli importanti, noti al componente di segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="24b05-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="24b05-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="24b05-108">For example:</span></span>

  - <span data-ttu-id="24b05-p102">Codice di causa fornito dal gateway PSTN che ha generato il problema. Se una chiamata in uscita ha esito negativo sulla rete PSTN, viene generato automaticamente un codice di causa ISUP (ISDN User Part). Un gateway PSTN ad esempio può inviare un codice di causa 34 per indicare l'indisponibilità di circuiti o canali per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="24b05-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="24b05-112">FQDN del peer, porta ed errori Winsock per i problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="24b05-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="24b05-p103">Nomi ricercati per i problemi di risoluzione DNS. Tale risoluzione ha luogo ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome di dispositivo specificato.</span><span class="sxs-lookup"><span data-stu-id="24b05-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="24b05-115">Accesso al Rapporto di diagnostica</span><span class="sxs-lookup"><span data-stu-id="24b05-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="24b05-116">È possibile accedere al rapporto di diagnostica facendo clic sulla metrica del rapporto di diagnostica (dettaglio) nel [rapporto Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o nel rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="24b05-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="24b05-117">Filtri</span><span class="sxs-lookup"><span data-stu-id="24b05-117">Filters</span></span>

<span data-ttu-id="24b05-p104">Nessuno. Non è possibile filtrare il Rapporto di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="24b05-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="24b05-120">Metriche</span><span class="sxs-lookup"><span data-stu-id="24b05-120">Metrics</span></span>

<span data-ttu-id="24b05-121">La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="24b05-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="24b05-122">Metriche del Rapporto di diagnostica</span><span class="sxs-lookup"><span data-stu-id="24b05-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24b05-123">Name</span><span class="sxs-lookup"><span data-stu-id="24b05-123">Name</span></span></th>
<th><span data-ttu-id="24b05-124">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="24b05-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="24b05-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24b05-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24b05-126"><strong>Ora rapporto</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-127">No</span><span class="sxs-lookup"><span data-stu-id="24b05-127">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-128">Data e ora di registrazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="24b05-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-129"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-130">No</span><span class="sxs-lookup"><span data-stu-id="24b05-130">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-131">Codice di risposta SIP inviato per la sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="24b05-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b05-132"><strong>Tipo di richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-133">No</span><span class="sxs-lookup"><span data-stu-id="24b05-133">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-p105">Tipo di richiesta SIP non riuscita. Ad esempio, INVITE, BYE o SERVICE.</span><span class="sxs-lookup"><span data-stu-id="24b05-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-137">No</span><span class="sxs-lookup"><span data-stu-id="24b05-137">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-138">Origine dell'errore.</span><span class="sxs-lookup"><span data-stu-id="24b05-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b05-139"><strong>URI utente di origine</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-140">No</span><span class="sxs-lookup"><span data-stu-id="24b05-140">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-141">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="24b05-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-142"><strong>Da agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-143">No</span><span class="sxs-lookup"><span data-stu-id="24b05-143">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-144">Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="24b05-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b05-145"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-146">No</span><span class="sxs-lookup"><span data-stu-id="24b05-146">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-147">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="24b05-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-148"><strong>Tipo di contenuto</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-149">No</span><span class="sxs-lookup"><span data-stu-id="24b05-149">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-p106">Tipo di contenuto multimediale con errori. Un tipo di contenuto comune è ad esempio Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per gli annunci di sessione, gli inviti per le sessioni e altre forme di avvio di sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="24b05-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b05-153"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-154">No</span><span class="sxs-lookup"><span data-stu-id="24b05-154">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-155">Applicazione coinvolta nell'errore.</span><span class="sxs-lookup"><span data-stu-id="24b05-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-156"><strong>URI utente di destinazione</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-157">No</span><span class="sxs-lookup"><span data-stu-id="24b05-157">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-158">Indirizzo SIP dell'utente che è stato invitato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="24b05-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b05-159">Tempi partecipazione conferenza (ms)</span><span class="sxs-lookup"><span data-stu-id="24b05-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="24b05-160">No</span><span class="sxs-lookup"><span data-stu-id="24b05-160">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-161">Intervallo di tempo, in millisecondi, che è stato necessario all'utente per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="24b05-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b05-162"><strong>Intestazione di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="24b05-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="24b05-163">No</span><span class="sxs-lookup"><span data-stu-id="24b05-163">No</span></span></p></td>
<td><p><span data-ttu-id="24b05-164">Descrizione dell'ID diagnostica.</span><span class="sxs-lookup"><span data-stu-id="24b05-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24b05-165">È possibile trovare un elenco di errori diagnostici nella [pagina di intestazione MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="24b05-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

