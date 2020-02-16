---
title: 'Lync Server 2013: rapporto Elenco errori'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cd8d15e81a54085624fab2dc751759d8196c48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="84cd9-102">Rapporto Elenco errori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84cd9-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84cd9-103">_**Ultimo argomento modificato:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="84cd9-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="84cd9-p101">Nel Rapporto Elenco errori vengono fornite informazioni sui singoli partecipanti che hanno preso parte a una sessione di conferenza o peer-to-peer in cui si sono verificati problemi. Tali informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID diagnostica associati all'errore.</span><span class="sxs-lookup"><span data-stu-id="84cd9-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="84cd9-106">Accesso al Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="84cd9-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="84cd9-107">È possibile accedere al rapporto Elenco errori facendo clic su una delle metriche seguenti nel [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="84cd9-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="84cd9-108">Motivi diagnostica principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="84cd9-109">Modalità principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="84cd9-110">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="84cd9-111">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="84cd9-112">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-112">Top components (sessions)</span></span>

  - <span data-ttu-id="84cd9-113">Utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="84cd9-114">Utenti di destinazione principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="84cd9-115">Agenti utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="84cd9-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="84cd9-116">Dal rapporto Elenco errori è possibile accedere al [rapporto Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) facendo clic sulla metrica Dettagli sessione per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="84cd9-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="84cd9-117">È inoltre possibile accedere al Rapporto Dettagli conferenza facendo clic sulla metrica Conferenza per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="84cd9-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="84cd9-118">Utilizzo ottimale del Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="84cd9-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="84cd9-p103">Nel Rapporto Elenco errori è possibile visualizzare una descrizione di ogni codice di risposta o di ogni ID diagnostica semplicemente posizionando il puntatore del mouse sul valore desiderato. Se ad esempio si posiziona il puntatore del mouse su Diagnostic ID 7025, in una descrizione comando verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="84cd9-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="84cd9-121">Internal server error creating media for user.</span><span class="sxs-lookup"><span data-stu-id="84cd9-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="84cd9-122">È importante notare che il Rapporto Elenco errori non consente di recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione con problemi, né consente di determinare quali utenti hanno partecipato più spesso a una sessione con problemi.</span><span class="sxs-lookup"><span data-stu-id="84cd9-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="84cd9-123">Per una cosa, il rapporto Elenco errori non dispone di funzionalità di filtro. Tuttavia, se i dati vengono esportati e quindi convertiti in un file con valori delimitati da virgole, è possibile utilizzare Windows PowerShell per trovare le risposte a domande come quelle.</span><span class="sxs-lookup"><span data-stu-id="84cd9-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="84cd9-124">Si supponga, ad esempio, di salvare i dati in un. File CSV denominato C:\\data\\Failure\_List. csv.</span><span class="sxs-lookup"><span data-stu-id="84cd9-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="84cd9-125">In base ai dati salvati in tale file, questo comando elencherà tutti gli utenti che hanno partecipato ad almeno una sessione con problemi:</span><span class="sxs-lookup"><span data-stu-id="84cd9-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="84cd9-126">Tale comando restituirà un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="84cd9-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="84cd9-127">Questi due comandi restituiscono il numero totale di sessioni con problemi a cui ha partecipato ogni utente:</span><span class="sxs-lookup"><span data-stu-id="84cd9-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="84cd9-128">Verranno restituiti dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cd9-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="84cd9-129">Filtri</span><span class="sxs-lookup"><span data-stu-id="84cd9-129">Filters</span></span>

<span data-ttu-id="84cd9-p105">Nessuno. Non è possibile filtrare il Rapporto elenco errori.</span><span class="sxs-lookup"><span data-stu-id="84cd9-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="84cd9-132">Metriche</span><span class="sxs-lookup"><span data-stu-id="84cd9-132">Metrics</span></span>

<span data-ttu-id="84cd9-133">Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto elenco errori per ogni chiamata non riuscita.</span><span class="sxs-lookup"><span data-stu-id="84cd9-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="84cd9-134">Metriche del Rapporto elenco errori</span><span class="sxs-lookup"><span data-stu-id="84cd9-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cd9-135">Name</span><span class="sxs-lookup"><span data-stu-id="84cd9-135">Name</span></span></th>
<th><span data-ttu-id="84cd9-136">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="84cd9-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="84cd9-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cd9-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cd9-138"><strong>Ora rapporto</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-139">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-139">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-140">Data e ora di registrazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="84cd9-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cd9-141"><strong>Richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-142">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-142">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-p106">Tipo di richiesta SIP non riuscita. Ad esempio, INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="84cd9-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cd9-145"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-146">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-146">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-147">Codice di risposta SIP inviato per la conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="84cd9-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cd9-148"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-149">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-149">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-150">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="84cd9-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cd9-151"><strong>Tempo costo partecipazione (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-152">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-152">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-153">Intervallo di tempo, in millisecondi, necessario all'utente per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="84cd9-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cd9-154"><strong>Da utente</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-155">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-155">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-156">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="84cd9-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cd9-157"><strong>Da agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-158">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-158">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-159">Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="84cd9-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cd9-160"><strong>A utente</strong></span><span class="sxs-lookup"><span data-stu-id="84cd9-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="84cd9-161">No</span><span class="sxs-lookup"><span data-stu-id="84cd9-161">No</span></span></p></td>
<td><p><span data-ttu-id="84cd9-162">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="84cd9-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

