---
title: Rapporto elenco errori in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Riepilogo: informazioni sul Rapporto elenco errori in Skype for Business Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816846"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="ca302-103">Rapporto elenco errori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ca302-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="ca302-104">**Riepilogo:** Informazioni sul Rapporto elenco errori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca302-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="ca302-p101">Nel Rapporto Elenco errori vengono fornite informazioni sui singoli partecipanti che hanno preso parte a una sessione di conferenza o peer-to-peer in cui si sono verificati problemi. Tali informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID diagnostica associati all'errore.</span><span class="sxs-lookup"><span data-stu-id="ca302-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="ca302-107">Accesso al Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="ca302-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="ca302-108">È possibile accedere al Rapporto Elenco errori facendo clic su una delle metriche seguenti nel Rapporto distribuzione [errori in Skype for Business Server:](failure-distribution-report.md)</span><span class="sxs-lookup"><span data-stu-id="ca302-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="ca302-109">Motivi diagnostica principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="ca302-110">Modalità principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="ca302-111">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="ca302-112">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="ca302-113">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="ca302-114">Utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="ca302-115">Utenti di destinazione principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="ca302-116">Agenti utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="ca302-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="ca302-117">Dal Rapporto elenco errori è possibile accedere al Rapporto dettagli sessione [peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) facendo clic sulla metrica Dettagli sessione per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ca302-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="ca302-118">È inoltre possibile accedere al Rapporto Dettagli conferenza facendo clic sulla metrica Conferenza per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ca302-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="ca302-119">Utilizzo ottimale del Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="ca302-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="ca302-p103">Nel Rapporto Elenco errori è possibile visualizzare una descrizione di ogni codice di risposta o di ogni ID diagnostica semplicemente posizionando il puntatore del mouse sul valore desiderato. Se ad esempio si posiziona il puntatore del mouse su Diagnostic ID 7025, in una descrizione comando verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ca302-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="ca302-122">Internal server error creating media for user.</span><span class="sxs-lookup"><span data-stu-id="ca302-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="ca302-p104">È importante notare che il Rapporto Elenco errori non consente di recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione con problemi, né consente di determinare quali utenti hanno partecipato più spesso a una sessione con problemi. Tale rapporto innanzitutto non dispone di funzionalità di filtro. Se però i dati vengono esportati e convertiti in un file con valori delimitati da virgole, è possibile utilizzare Windows PowerShell per trovare le risposte a domande come queste. Si supponga ad esempio di salvare i dati in un file CSV denominato C:\Data\Failure_List.csv. In base ai dati salvati in tale file, questo comando elencherà tutti gli utenti che hanno partecipato ad almeno una sessione con problemi:</span><span class="sxs-lookup"><span data-stu-id="ca302-p104">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="ca302-127">Tale comando restituirà un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ca302-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="ca302-128">Questi due comandi restituiscono il numero totale di sessioni con problemi a cui ha partecipato ogni utente:</span><span class="sxs-lookup"><span data-stu-id="ca302-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="ca302-129">Verranno restituiti dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca302-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="ca302-130">Filtri</span><span class="sxs-lookup"><span data-stu-id="ca302-130">Filters</span></span>

<span data-ttu-id="ca302-p105">Nessuno. Non è possibile filtrare il Rapporto elenco errori.</span><span class="sxs-lookup"><span data-stu-id="ca302-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="ca302-133">Metriche</span><span class="sxs-lookup"><span data-stu-id="ca302-133">Metrics</span></span>

<span data-ttu-id="ca302-134">Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto elenco errori per ogni chiamata non riuscita.</span><span class="sxs-lookup"><span data-stu-id="ca302-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="ca302-135">**Metriche del Rapporto elenco errori**</span><span class="sxs-lookup"><span data-stu-id="ca302-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="ca302-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ca302-136">**Name**</span></span>|<span data-ttu-id="ca302-137">**Elemento utilizzabile per eseguire l'ordinamento?**</span><span class="sxs-lookup"><span data-stu-id="ca302-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="ca302-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ca302-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca302-139">**Ora rapporto**</span><span class="sxs-lookup"><span data-stu-id="ca302-139">**Reported time**</span></span> <br/> |<span data-ttu-id="ca302-140">No</span><span class="sxs-lookup"><span data-stu-id="ca302-140">No</span></span>  <br/> |<span data-ttu-id="ca302-141">Data e ora di registrazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="ca302-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="ca302-142">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="ca302-142">**Request**</span></span> <br/> |<span data-ttu-id="ca302-143">No</span><span class="sxs-lookup"><span data-stu-id="ca302-143">No</span></span>  <br/> |<span data-ttu-id="ca302-p106">Tipo di richiesta SIP non riuscita. Ad esempio, INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="ca302-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="ca302-146">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="ca302-146">**Response code**</span></span> <br/> |<span data-ttu-id="ca302-147">No</span><span class="sxs-lookup"><span data-stu-id="ca302-147">No</span></span>  <br/> |<span data-ttu-id="ca302-148">Codice di risposta SIP inviato per la conferenza non riuscita.</span><span class="sxs-lookup"><span data-stu-id="ca302-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="ca302-149">**ID diagnostica**</span><span class="sxs-lookup"><span data-stu-id="ca302-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="ca302-150">No</span><span class="sxs-lookup"><span data-stu-id="ca302-150">No</span></span>  <br/> |<span data-ttu-id="ca302-151">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="ca302-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="ca302-152">**Tempo costo partecipazione (ms)**</span><span class="sxs-lookup"><span data-stu-id="ca302-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="ca302-153">No</span><span class="sxs-lookup"><span data-stu-id="ca302-153">No</span></span>  <br/> |<span data-ttu-id="ca302-154">Intervallo di tempo, in millisecondi, necessario all'utente per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ca302-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="ca302-155">**Da utente**</span><span class="sxs-lookup"><span data-stu-id="ca302-155">**From user**</span></span> <br/> |<span data-ttu-id="ca302-156">No</span><span class="sxs-lookup"><span data-stu-id="ca302-156">No</span></span>  <br/> |<span data-ttu-id="ca302-157">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ca302-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ca302-158">**Da agente utente**</span><span class="sxs-lookup"><span data-stu-id="ca302-158">**From user agent**</span></span> <br/> |<span data-ttu-id="ca302-159">No</span><span class="sxs-lookup"><span data-stu-id="ca302-159">No</span></span>  <br/> |<span data-ttu-id="ca302-160">Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ca302-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ca302-161">**A utente**</span><span class="sxs-lookup"><span data-stu-id="ca302-161">**To user**</span></span> <br/> |<span data-ttu-id="ca302-162">No</span><span class="sxs-lookup"><span data-stu-id="ca302-162">No</span></span>  <br/> |<span data-ttu-id="ca302-163">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="ca302-163">SIP address of the user who was being called.</span></span>  <br/> |
   

