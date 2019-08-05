---
title: Report elenco errori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Riepilogo: informazioni sul report elenco errori in Skype for Business Server.'
ms.openlocfilehash: 72637863d7a15d26ea997de8a9c3526279afc57f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195684"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="b22d1-103">Report elenco errori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b22d1-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="b22d1-104">**Riepilogo:** Informazioni sul report elenco errori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b22d1-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="b22d1-105">Il report elenco errori contiene informazioni sui singoli partecipanti che hanno partecipato a una sessione peer-to-peer o conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="b22d1-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="b22d1-106">Queste informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID di diagnostica associati all'errore.</span><span class="sxs-lookup"><span data-stu-id="b22d1-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="b22d1-107">Accesso al report elenco errori</span><span class="sxs-lookup"><span data-stu-id="b22d1-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="b22d1-108">Per accedere al report elenco errori, fare clic su una delle metriche seguenti nel [report distribuzione errori in Skype for Business Server](failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="b22d1-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="b22d1-109">Principali motivi diagnostici (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="b22d1-110">Modalità top (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="b22d1-111">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="b22d1-112">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="b22d1-113">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="b22d1-114">Inizio da utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="b22d1-115">Inizio per gli utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="b22d1-116">Inizio da agenti utente (sessioni)</span><span class="sxs-lookup"><span data-stu-id="b22d1-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="b22d1-117">Nel report elenco errori è possibile accedere al [report Dettagli sessione peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) facendo clic sulla metrica di dettaglio della sessione per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b22d1-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="b22d1-118">È anche possibile accedere al report Dettagli conferenza facendo clic sulla metrica conferenza per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="b22d1-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="b22d1-119">Sfruttare al meglio il report elenco errori</span><span class="sxs-lookup"><span data-stu-id="b22d1-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="b22d1-120">Nel report elenco errori è possibile visualizzare una descrizione per ogni codice di risposta o ogni ID di diagnostica semplicemente tenendo premuto il mouse su tale valore.</span><span class="sxs-lookup"><span data-stu-id="b22d1-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="b22d1-121">Ad esempio, se si tiene premuto il mouse sull'ID di diagnostica 7025, in una descrizione comandi verranno visualizzati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b22d1-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="b22d1-122">Errore del server interno che crea elementi multimediali per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b22d1-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="b22d1-123">È importante notare che il report elenco errori non offre un modo semplice per recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita, né offre un modo per determinare gli utenti più spesso coinvolti in un errore sessione.</span><span class="sxs-lookup"><span data-stu-id="b22d1-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="b22d1-124">Per prima cosa, il report elenco errori non ha funzionalità di filtro. Tuttavia, se si esportano i dati e quindi lo si converte in un file con valori delimitati da virgole, è possibile usare Windows PowerShell per trovare le risposte a domande come quelle.</span><span class="sxs-lookup"><span data-stu-id="b22d1-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="b22d1-125">Supponiamo ad esempio di salvare i dati in un. File CSV denominato C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="b22d1-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="b22d1-126">In base ai dati salvati nel file, questo comando elenca tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita:</span><span class="sxs-lookup"><span data-stu-id="b22d1-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="b22d1-127">Questo comando restituirà un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b22d1-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="b22d1-128">Questi due comandi segnalano il numero totale di sessioni non riuscite in cui ogni utente è coinvolto:</span><span class="sxs-lookup"><span data-stu-id="b22d1-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="b22d1-129">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="b22d1-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="b22d1-130">Filtri</span><span class="sxs-lookup"><span data-stu-id="b22d1-130">Filters</span></span>

<span data-ttu-id="b22d1-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b22d1-131">None.</span></span> <span data-ttu-id="b22d1-132">Non è possibile filtrare il report elenco errori.</span><span class="sxs-lookup"><span data-stu-id="b22d1-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="b22d1-133">Metriche</span><span class="sxs-lookup"><span data-stu-id="b22d1-133">Metrics</span></span>

<span data-ttu-id="b22d1-134">Nella tabella seguente sono elencate le informazioni fornite nel report elenco errori per ogni chiamata non riuscita.</span><span class="sxs-lookup"><span data-stu-id="b22d1-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="b22d1-135">**Metriche rapporto Elenco errori**</span><span class="sxs-lookup"><span data-stu-id="b22d1-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="b22d1-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b22d1-136">**Name**</span></span>|<span data-ttu-id="b22d1-137">**Si può ordinare su questo elemento?**</span><span class="sxs-lookup"><span data-stu-id="b22d1-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="b22d1-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b22d1-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b22d1-139">**Tempo segnalato**</span><span class="sxs-lookup"><span data-stu-id="b22d1-139">**Reported time**</span></span> <br/> |<span data-ttu-id="b22d1-140">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-140">No</span></span>  <br/> |<span data-ttu-id="b22d1-141">Data e ora in cui il report è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="b22d1-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="b22d1-142">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b22d1-142">**Request**</span></span> <br/> |<span data-ttu-id="b22d1-143">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-143">No</span></span>  <br/> |<span data-ttu-id="b22d1-144">Tipo di richiesta SIP non riuscito.</span><span class="sxs-lookup"><span data-stu-id="b22d1-144">SIP request type that failed.</span></span> <span data-ttu-id="b22d1-145">Ad esempio, invita o BYE.</span><span class="sxs-lookup"><span data-stu-id="b22d1-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="b22d1-146">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="b22d1-146">**Response code**</span></span> <br/> |<span data-ttu-id="b22d1-147">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-147">No</span></span>  <br/> |<span data-ttu-id="b22d1-148">Codice di risposta SIP inviato quando la conferenza non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b22d1-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="b22d1-149">**ID diagnostica**</span><span class="sxs-lookup"><span data-stu-id="b22d1-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="b22d1-150">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-150">No</span></span>  <br/> |<span data-ttu-id="b22d1-151">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="b22d1-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="b22d1-152">**Tempo di costo di partecipazione (MS)**</span><span class="sxs-lookup"><span data-stu-id="b22d1-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="b22d1-153">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-153">No</span></span>  <br/> |<span data-ttu-id="b22d1-154">Intervallo di tempo (in millisecondi) necessario affinché l'utente partecipi alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="b22d1-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="b22d1-155">**Dall'utente**</span><span class="sxs-lookup"><span data-stu-id="b22d1-155">**From user**</span></span> <br/> |<span data-ttu-id="b22d1-156">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-156">No</span></span>  <br/> |<span data-ttu-id="b22d1-157">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b22d1-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="b22d1-158">**Dall'agente utente**</span><span class="sxs-lookup"><span data-stu-id="b22d1-158">**From user agent**</span></span> <br/> |<span data-ttu-id="b22d1-159">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-159">No</span></span>  <br/> |<span data-ttu-id="b22d1-160">Software usato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b22d1-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="b22d1-161">**All'utente**</span><span class="sxs-lookup"><span data-stu-id="b22d1-161">**To user**</span></span> <br/> |<span data-ttu-id="b22d1-162">No</span><span class="sxs-lookup"><span data-stu-id="b22d1-162">No</span></span>  <br/> |<span data-ttu-id="b22d1-163">Indirizzo SIP dell'utente che veniva chiamato.</span><span class="sxs-lookup"><span data-stu-id="b22d1-163">SIP address of the user who was being called.</span></span>  <br/> |
   

