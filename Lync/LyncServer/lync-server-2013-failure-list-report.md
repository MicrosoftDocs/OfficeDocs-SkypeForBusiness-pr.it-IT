---
title: 'Lync Server 2013: report elenco errori'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c1c9c15b1f539aa1a5213989674dfea268a684
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="f2df4-102">Report elenco errori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2df4-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2df4-103">_**Argomento Ultima modifica:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="f2df4-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="f2df4-104">Il report elenco errori contiene informazioni sui singoli partecipanti che hanno partecipato a una sessione peer-to-peer o conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="f2df4-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="f2df4-105">Queste informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID di diagnostica associati all'errore.</span><span class="sxs-lookup"><span data-stu-id="f2df4-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="f2df4-106">Accesso al report elenco errori</span><span class="sxs-lookup"><span data-stu-id="f2df4-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="f2df4-107">Per accedere al report elenco errori, fare clic su una delle metriche seguenti nel [report distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="f2df4-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="f2df4-108">Principali motivi diagnostici (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="f2df4-109">Modalità top (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="f2df4-110">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="f2df4-111">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="f2df4-112">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-112">Top components (sessions)</span></span>

  - <span data-ttu-id="f2df4-113">Inizio da utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="f2df4-114">Inizio per gli utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="f2df4-115">Inizio da agenti utente (sessioni)</span><span class="sxs-lookup"><span data-stu-id="f2df4-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="f2df4-116">Nel report elenco errori è possibile accedere al [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) facendo clic sulla metrica di dettaglio della sessione per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f2df4-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="f2df4-117">È anche possibile accedere al report Dettagli conferenza facendo clic sulla metrica conferenza per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f2df4-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="f2df4-118">Sfruttare al meglio il report elenco errori</span><span class="sxs-lookup"><span data-stu-id="f2df4-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="f2df4-119">Nel report elenco errori è possibile visualizzare una descrizione per ogni codice di risposta o ogni ID di diagnostica semplicemente tenendo premuto il mouse su tale valore.</span><span class="sxs-lookup"><span data-stu-id="f2df4-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="f2df4-120">Ad esempio, se si tiene premuto il mouse sull'ID di diagnostica 7025, in una descrizione comandi verranno visualizzati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f2df4-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="f2df4-121">Errore del server interno che crea elementi multimediali per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f2df4-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="f2df4-122">È importante notare che il report elenco errori non offre un modo semplice per recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita, né offre un modo per determinare gli utenti più spesso coinvolti in un errore sessione.</span><span class="sxs-lookup"><span data-stu-id="f2df4-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="f2df4-123">Per prima cosa, il report elenco errori non ha funzionalità di filtro. Tuttavia, se si esportano i dati e quindi lo si converte in un file con valori delimitati da virgole, è possibile usare Windows PowerShell per trovare le risposte a domande come quelle.</span><span class="sxs-lookup"><span data-stu-id="f2df4-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="f2df4-124">Supponiamo ad esempio di salvare i dati in un. File CSV denominato C:\\errore\\\_di dati List. csv.</span><span class="sxs-lookup"><span data-stu-id="f2df4-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="f2df4-125">In base ai dati salvati nel file, questo comando elenca tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita:</span><span class="sxs-lookup"><span data-stu-id="f2df4-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="f2df4-126">Questo comando restituirà un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f2df4-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="f2df4-127">Questi due comandi segnalano il numero totale di sessioni non riuscite in cui ogni utente è coinvolto:</span><span class="sxs-lookup"><span data-stu-id="f2df4-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="f2df4-128">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="f2df4-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f2df4-129">Filtri</span><span class="sxs-lookup"><span data-stu-id="f2df4-129">Filters</span></span>

<span data-ttu-id="f2df4-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f2df4-130">None.</span></span> <span data-ttu-id="f2df4-131">Non è possibile filtrare il report elenco errori.</span><span class="sxs-lookup"><span data-stu-id="f2df4-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f2df4-132">Metriche</span><span class="sxs-lookup"><span data-stu-id="f2df4-132">Metrics</span></span>

<span data-ttu-id="f2df4-133">Nella tabella seguente sono elencate le informazioni fornite nel report elenco errori per ogni chiamata non riuscita.</span><span class="sxs-lookup"><span data-stu-id="f2df4-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="f2df4-134">Metriche rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="f2df4-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2df4-135">Nome</span><span class="sxs-lookup"><span data-stu-id="f2df4-135">Name</span></span></th>
<th><span data-ttu-id="f2df4-136">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="f2df4-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2df4-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2df4-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2df4-138"><strong>Tempo segnalato</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-139">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-139">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-140">Data e ora in cui il report è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="f2df4-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2df4-141"><strong>Richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-142">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-142">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-143">Tipo di richiesta SIP non riuscito.</span><span class="sxs-lookup"><span data-stu-id="f2df4-143">SIP request type that failed.</span></span> <span data-ttu-id="f2df4-144">Ad esempio, invita o BYE.</span><span class="sxs-lookup"><span data-stu-id="f2df4-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2df4-145"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-146">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-146">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-147">Codice di risposta SIP inviato quando la conferenza non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f2df4-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2df4-148"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-149">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-149">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-150">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="f2df4-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2df4-151"><strong>Tempo di costo di partecipazione (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-152">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-152">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-153">Intervallo di tempo (in millisecondi) necessario affinché l'utente partecipi alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="f2df4-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2df4-154"><strong>Dall'utente</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-155">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-155">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-156">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f2df4-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2df4-157"><strong>Dall'agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-158">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-158">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-159">Software usato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f2df4-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2df4-160"><strong>All'utente</strong></span><span class="sxs-lookup"><span data-stu-id="f2df4-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2df4-161">No</span><span class="sxs-lookup"><span data-stu-id="f2df4-161">No</span></span></p></td>
<td><p><span data-ttu-id="f2df4-162">Indirizzo SIP dell'utente che veniva chiamato.</span><span class="sxs-lookup"><span data-stu-id="f2df4-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

