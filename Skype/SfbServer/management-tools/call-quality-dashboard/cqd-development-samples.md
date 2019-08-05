---
title: Esempi di sviluppo Call Quality dashboard
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Riepilogo: esaminare gli esempi di esercitazione e sviluppo per dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: 4eac679950abdff5041bdfb63b633287d06a11e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186971"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="f7efe-104">Esempi di sviluppo Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="f7efe-104">CQD Development Samples</span></span>

<span data-ttu-id="f7efe-105">**Riepilogo:** Esaminare gli esempi di esercitazione e sviluppo per dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="f7efe-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="f7efe-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7efe-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="f7efe-107">Questo articolo contiene un'esercitazione ed esempi sullo sviluppo di Call Quality Dashboard (Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="f7efe-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="f7efe-108">Esempi di sviluppo di Call Quality Dashboard (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="f7efe-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="f7efe-109">Esercitazione: creazione di una presentazione di report personalizzata con il servizio dati Call Quality dashboard e l'API del servizio repository.</span><span class="sxs-lookup"><span data-stu-id="f7efe-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="f7efe-110">Introduzione a Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="f7efe-110">Introduction to CQD</span></span>

<span data-ttu-id="f7efe-111">Call Quality dashboard offre un accesso rapido e semplice alle informazioni di qualità delle chiamate aggregate per le distribuzioni locali di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7efe-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="f7efe-112">Call Quality dashboard è costituito da tre componenti: il database di archiviazione QoE, il cubo e il portale.</span><span class="sxs-lookup"><span data-stu-id="f7efe-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="f7efe-113">Il portale è il livello principale della presentazione e può essere ulteriormente suddiviso nei tre componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7efe-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="f7efe-114">Servizio dati, accessibile per gli utenti autenticati tramite l' [API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server](data-api.md).</span><span class="sxs-lookup"><span data-stu-id="f7efe-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="f7efe-115">Servizio repository, accessibile per gli utenti autenticati tramite l' [API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server](repository-api.md).</span><span class="sxs-lookup"><span data-stu-id="f7efe-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="f7efe-116">Web Portal, ovvero l'interfaccia basata su HTML5 con cui gli utenti di Call Quality dashboard vedono e interagiscono.</span><span class="sxs-lookup"><span data-stu-id="f7efe-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="f7efe-117">Questa operazione è accessibile per gli utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="f7efe-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="f7efe-118">I report visualizzati nel portale Web sono raggruppati in "set di report".</span><span class="sxs-lookup"><span data-stu-id="f7efe-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="f7efe-119">La figura mostra un set di report con due report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="f7efe-120">Ogni report in questo dashboard seguente mostra i risultati delle query su numero di chiamate valide, chiamate scadenti e percentuale di chiamata scadente per diversi mesi, con vari filtri applicati.</span><span class="sxs-lookup"><span data-stu-id="f7efe-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Report di esempio Call Quality dashboard](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="f7efe-122">Call Quality dashboard viene creato seguendo la metodologia di qualità delle chiamate (CQM), quindi il set di report predefinito è progettato per essere allineato al flusso di analisi introdotto da CQM.</span><span class="sxs-lookup"><span data-stu-id="f7efe-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="f7efe-123">Gli utenti hanno anche la possibilità di modificare o creare report personalizzati per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="f7efe-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="f7efe-124">Tuttavia, dato che esistono diversi modi per visualizzare i dati, la visualizzazione fornita da Call Quality Dashboard potrebbe non rispondere completamente alle esigenze di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f7efe-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="f7efe-125">In questi casi, un utente può sfruttare le API dei dati e le API del repository per creare pagine del report personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f7efe-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="f7efe-126">In questa esercitazione verrà illustrata una serie di esempi.</span><span class="sxs-lookup"><span data-stu-id="f7efe-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="f7efe-127">Modalità di utilizzo del servizio dati da parte del dashboard</span><span class="sxs-lookup"><span data-stu-id="f7efe-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="f7efe-128">Quando si passa alla Home page di Call Quality Dashboard (ad http://localhost/cqd)esempio, il set di report e i report corrispondenti per un utente autenticato e autorizzato verranno recuperati dal servizio repository.</span><span class="sxs-lookup"><span data-stu-id="f7efe-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="f7efe-129">Un URL completo verrà costruito dall'ID set di report e l'anno-mese (ID set di report è il numero intero dopo la sezione "/#/" in URL e per impostazione predefinita l'anno-mese corrente viene accodato alla fine del report-ID set dopo la barra).</span><span class="sxs-lookup"><span data-stu-id="f7efe-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="f7efe-130">Le definizioni del report sono archiviate in formato JSON e, se recuperate dal servizio repository, verranno usate come input per il servizio dati.</span><span class="sxs-lookup"><span data-stu-id="f7efe-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="f7efe-131">Il servizio dati genera query MDX (Multi-Dimension Expression) in base all'input e quindi esegue queste query MDX sul cubo per recuperare i dati per ogni report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="f7efe-132">Creazione di report personalizzati</span><span class="sxs-lookup"><span data-stu-id="f7efe-132">Building customized reports</span></span>

<span data-ttu-id="f7efe-133">Call Quality Dashboard ha già molta flessibilità nella personalizzazione dei report, ma potrebbero esserci situazioni in cui gli utenti potrebbero voler aggregare i dati in più report creati in Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="f7efe-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="f7efe-134">Ad esempio, potrebbe essere necessario creare un report che mostra le percentuali di chiamata scadente di tutte le possibili combinazioni di chiamate cablate in una tabella (risultato simile alla figura):</span><span class="sxs-lookup"><span data-stu-id="f7efe-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Tabella Call Quality dashboard](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="f7efe-136">Usando il portale fornito da Call Quality dashboard, un utente dovrebbe passare a più report per estrarre e registrare la povera chiamata% per ognuno, che può essere laboriosa se sono presenti molti punti dati da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="f7efe-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="f7efe-137">Le API dei dati consentono agli utenti di eseguire questa operazione a livello di codice, recuperando i dati dal servizio dati (ad esempio tramite chiamate AJAX).</span><span class="sxs-lookup"><span data-stu-id="f7efe-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="f7efe-138">**Esempio 1: esempio di report semplice**</span><span class="sxs-lookup"><span data-stu-id="f7efe-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="f7efe-139">Prendiamo prima di tutto un semplice esempio.</span><span class="sxs-lookup"><span data-stu-id="f7efe-139">Let us take a simple example first.</span></span> <span data-ttu-id="f7efe-140">Se si vuole visualizzare il flusso audio buono e il conteggio dei flussi audio non validi di 2015 febbraio in una pagina HTML come la figura:</span><span class="sxs-lookup"><span data-stu-id="f7efe-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Report di esempio di Call Quality dashboard](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="f7efe-142">Ciò che serve è inviare una chiamata al servizio dati con i parametri corretti e visualizzare i risultati della query in una tabella HTML.</span><span class="sxs-lookup"><span data-stu-id="f7efe-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="f7efe-143">Di seguito è riportato un esempio di codice JavaScript:</span><span class="sxs-lookup"><span data-stu-id="f7efe-143">The following is a sample of the JavaScript code:</span></span>

```        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="f7efe-144">Questo esempio può essere ulteriormente decostruito in tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="f7efe-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="f7efe-145">Costruisci la query (nell'esempio questo è definito nella variabile "query").</span><span class="sxs-lookup"><span data-stu-id="f7efe-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="f7efe-146">La query è definita come oggetto JSON, che include i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7efe-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="f7efe-147">un.</span><span class="sxs-lookup"><span data-stu-id="f7efe-147">a.</span></span> <span data-ttu-id="f7efe-148">Zero o più dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f7efe-148">Zero or more dimensions.</span></span> <span data-ttu-id="f7efe-149">Ogni dimensione è indicata da una datamodelname.</span><span class="sxs-lookup"><span data-stu-id="f7efe-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="f7efe-150">b.</span><span class="sxs-lookup"><span data-stu-id="f7efe-150">b.</span></span> <span data-ttu-id="f7efe-151">Zero o più filtri.</span><span class="sxs-lookup"><span data-stu-id="f7efe-151">Zero or more filters.</span></span> <span data-ttu-id="f7efe-152">Ogni filtro ha:</span><span class="sxs-lookup"><span data-stu-id="f7efe-152">Each filter has:</span></span>

   - <span data-ttu-id="f7efe-153">Datamodelname (la dimensione che avrà il set di filtri).</span><span class="sxs-lookup"><span data-stu-id="f7efe-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="f7efe-154">Value (il valore che verrà confrontato dall'operando).</span><span class="sxs-lookup"><span data-stu-id="f7efe-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="f7efe-155">Operando (tipo di confronto, 0 significa "uguale").</span><span class="sxs-lookup"><span data-stu-id="f7efe-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="f7efe-156">c.</span><span class="sxs-lookup"><span data-stu-id="f7efe-156">c.</span></span> <span data-ttu-id="f7efe-157">Una o più misure.</span><span class="sxs-lookup"><span data-stu-id="f7efe-157">One or more measurements.</span></span>

2. <span data-ttu-id="f7efe-158">Inviare la query al servizio dati tramite chiamata AJAX.</span><span class="sxs-lookup"><span data-stu-id="f7efe-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="f7efe-159">I parametri di richiesta seguenti devono essere forniti:</span><span class="sxs-lookup"><span data-stu-id="f7efe-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="f7efe-160">un.</span><span class="sxs-lookup"><span data-stu-id="f7efe-160">a.</span></span> <span data-ttu-id="f7efe-161">URL (che deve essere http://[nomeserver]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="f7efe-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="f7efe-162">b.</span><span class="sxs-lookup"><span data-stu-id="f7efe-162">b.</span></span> <span data-ttu-id="f7efe-163">Data (questa è la rappresentazione di stringa dell'oggetto JSON definito nella variabile di query).</span><span class="sxs-lookup"><span data-stu-id="f7efe-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="f7efe-164">Il servizio dati restituirà i risultati della query come parametro della funzione di richiamata per l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f7efe-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="f7efe-165">c.</span><span class="sxs-lookup"><span data-stu-id="f7efe-165">c.</span></span> <span data-ttu-id="f7efe-166">Type (per QoEDataService, RunQuery accetta solo le richieste "POST").</span><span class="sxs-lookup"><span data-stu-id="f7efe-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="f7efe-167">3D.</span><span class="sxs-lookup"><span data-stu-id="f7efe-167">d.</span></span> <span data-ttu-id="f7efe-168">Async (un contrassegno che indica se la chiamata AJAX deve essere sincrona o asincrona).</span><span class="sxs-lookup"><span data-stu-id="f7efe-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="f7efe-169">e.</span><span class="sxs-lookup"><span data-stu-id="f7efe-169">e.</span></span> <span data-ttu-id="f7efe-170">contentType (deve essere "application/json").</span><span class="sxs-lookup"><span data-stu-id="f7efe-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="f7efe-171">f.</span><span class="sxs-lookup"><span data-stu-id="f7efe-171">f.</span></span> <span data-ttu-id="f7efe-172">operazione riuscita (funzione di richiamata per quando la chiamata AJAX viene completata correttamente).</span><span class="sxs-lookup"><span data-stu-id="f7efe-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="f7efe-173">g.</span><span class="sxs-lookup"><span data-stu-id="f7efe-173">g.</span></span> <span data-ttu-id="f7efe-174">errore (funzione di gestione degli errori per la chiamata AJAX non riesce).</span><span class="sxs-lookup"><span data-stu-id="f7efe-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="f7efe-175">Inserire dati in elementi div nell'HTML (nell'esempio nel codice, questa operazione viene eseguita tramite la chiamata di funzione anonima dopo che la richiesta AJAX è stata completata correttamente).</span><span class="sxs-lookup"><span data-stu-id="f7efe-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="f7efe-176">Racchiudere il codice JavaScript in una pagina HTML e la pagina mostrerà un report come quello mostrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="f7efe-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="f7efe-177">Il codice HTML completo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f7efe-177">The full html is as follows:</span></span>

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="f7efe-178">Finora il report è ancora molto semplice.</span><span class="sxs-lookup"><span data-stu-id="f7efe-178">So far, the report is still very simple.</span></span> <span data-ttu-id="f7efe-179">Per personalizzare il report, l'utente può aggiungere altre misure, dimensioni o filtri.</span><span class="sxs-lookup"><span data-stu-id="f7efe-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="f7efe-180">Ad esempio, se si vuole visualizzare la percentuale di chiamata condivisione applicazioni scadente, è necessario aggiungere una nuova misura per quanto riguarda condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f7efe-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="f7efe-181">Se si vuole visualizzare tutte le chiamate TCP v.s.</span><span class="sxs-lookup"><span data-stu-id="f7efe-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="f7efe-182">Chiamate UDP, deve essere aggiunta una nuova dimensione per il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f7efe-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="f7efe-183">Se si vuole visualizzare il numero di chiamate non consentite in un determinato edificio, è necessario aggiungere un nuovo filtro per selezionare le chiamate da e verso l'edificio.</span><span class="sxs-lookup"><span data-stu-id="f7efe-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="f7efe-184">**Esempio 2: esempio di definizione del report**</span><span class="sxs-lookup"><span data-stu-id="f7efe-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="f7efe-185">Potrebbe essere difficile per qualcuno capire come scrivere l'elenco completo di misure/dimensioni/filtri e i valori corrispondenti durante la costruzione di una query.</span><span class="sxs-lookup"><span data-stu-id="f7efe-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="f7efe-186">In questo caso, è possibile accedere al portale, creare un report usando l'editor report e visualizzare la stringa JSON della definizione del report e quindi copiare la definizione in un report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f7efe-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="f7efe-187">In questo esempio creeremo una pagina Web come quella mostrata nella figura in cui un utente può immettere l'ID di qualsiasi set di report esistente (o report) e visualizzare la definizione del set di report o del report nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="f7efe-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="f7efe-188">L'utente può quindi connettere la stringa JSON di ogni report in codice simile a quello mostrato nell'esempio 1 e creare un report personalizzato che l'utente desidera.</span><span class="sxs-lookup"><span data-stu-id="f7efe-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Esempio di Call Quality dashboard](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="f7efe-190">Per creare lo strumento Visualizzatore definizione report, è necessario inviare chiamate al servizio repository per recuperare le rappresentazioni di stringa JSON delle definizioni di ogni set di report desiderato.</span><span class="sxs-lookup"><span data-stu-id="f7efe-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="f7efe-191">L'API del repository restituirà la definizione di set di report in base a un ID set di report specifico.</span><span class="sxs-lookup"><span data-stu-id="f7efe-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="f7efe-192">Un esempio rapido è il seguente: il codice contiene un blocco che è un semplice esempio per inviare una query al servizio repository per ottenere il contenuto di un elemento del repository in base al relativo identificatore.</span><span class="sxs-lookup"><span data-stu-id="f7efe-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="f7efe-193">E la parte successiva del codice (metodo processReportSetData) sta inviando chiamate AJAX per ottenere la definizione di ogni report all'interno del set di report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="f7efe-194">Dato che l'ID nel portale Web di Call Quality dashboard è l'ID di un set di report, la chiamata AJAX restituirà un elemento del set di report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="f7efe-195">Altri dettagli sull'API del repository e in particolare su GetItems possono essere trovati negli [elementi Get](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="f7efe-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="f7efe-196">Il risultato precedente si tradurrà in una pagina Web come quella della figura (senza la definizione del rapporto alla prima visita).</span><span class="sxs-lookup"><span data-stu-id="f7efe-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="f7efe-197">Ottenere l'ID set di report dal portale di Call Quality Dashboard (dopo l'accesso a "/#/", accedere all'URL del portale di Call Quality dashboard, ad esempio</span><span class="sxs-lookup"><span data-stu-id="f7efe-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="f7efe-198">nella prima figura l'ID set di report è 3024) e inserire l'ID del set di report nella sezione input di questa pagina Web.</span><span class="sxs-lookup"><span data-stu-id="f7efe-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="f7efe-199">Premere il pulsante "carica" e vedere la definizione completa (misure, dimensioni, elenchi filtri) del set di report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="f7efe-200">In Riepilogo, per ottenere rapidamente la definizione completa di un set di report/report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="f7efe-201">I passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7efe-201">The steps are:</span></span>

1. <span data-ttu-id="f7efe-202">Accedere al portale e usare l'editor di query per personalizzare un report (fare clic sul pulsante "modifica" sopra un report per modificare, aggiungere, rimuovere misure/dimensioni/filtri e quindi salvare il report).</span><span class="sxs-lookup"><span data-stu-id="f7efe-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="f7efe-203">Ottenere l'ID del set di report da URL (il numero intero dopo l'accesso all'URL "/#/").</span><span class="sxs-lookup"><span data-stu-id="f7efe-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="f7efe-204">Avviare questa pagina Web di definizione del report creata nell'esempio 2 e immettere l'ID set di report e recuperare la definizione completa di un set di report (da usare nelle chiamate API dati).</span><span class="sxs-lookup"><span data-stu-id="f7efe-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="f7efe-205">**Esempio 3: esempio di scorecard**</span><span class="sxs-lookup"><span data-stu-id="f7efe-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="f7efe-206">Tempo per un'attività più complessa.</span><span class="sxs-lookup"><span data-stu-id="f7efe-206">Time for a more complicated task.</span></span> <span data-ttu-id="f7efe-207">Cosa fare se si vuole creare una pagina Web come la figura?</span><span class="sxs-lookup"><span data-stu-id="f7efe-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="f7efe-208">È necessario aggiornare l'esempio 1 (con l'aiuto della pagina Web generata nell'esempio 2 per recuperare la definizione completa di qualsiasi report) in modo da poter gestire una maggiore quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="f7efe-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="f7efe-209">In questo caso, è necessario aggiornare l'elenco di misure e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f7efe-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="f7efe-210">Il modo per capire come aggiungere/modificare una misurazione e/o una dimensione consiste nel seguire le istruzioni dell'esempio 2 e recuperare la definizione completa del report, inclusi gli elenchi di misura e di dimensione completi.</span><span class="sxs-lookup"><span data-stu-id="f7efe-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="f7efe-211">Inserire la definizione completa del report nel codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="f7efe-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="f7efe-212">Ecco la procedura dettagliata per ottenere la pagina della scorecard nella figura dell'esempio 1:</span><span class="sxs-lookup"><span data-stu-id="f7efe-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="f7efe-213">Aggiornare le misure nella variabile "query" da `[Measures].[Audio Good Streams JPDR Count]` e `[Measures].[Audio Poor Streams JPDR Count]` verso `[Measures].[AudioPoorJPDRPercentage]`.</span><span class="sxs-lookup"><span data-stu-id="f7efe-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="f7efe-214">Aggiornare i filtri.</span><span class="sxs-lookup"><span data-stu-id="f7efe-214">Update the filters.</span></span> <span data-ttu-id="f7efe-215">I dati JSON per i filtri nell'esempio 1 includono un filtro, che è impostato sulla dimensione `[StartDate].[Month]`.</span><span class="sxs-lookup"><span data-stu-id="f7efe-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="f7efe-216">Dato che Filters è una matrice JSON, è possibile aggiungere altre dimensioni all'elenco dei filtri.</span><span class="sxs-lookup"><span data-stu-id="f7efe-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="f7efe-217">Ad esempio, per ottenere il client-server all'interno delle chiamate cablate per "currentMonth", dovremmo avere i seguenti filtri:</span><span class="sxs-lookup"><span data-stu-id="f7efe-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="f7efe-218">Qui la dimensione `[Scenarios].[ScenarioPair]` è impostata su uguale `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span><span class="sxs-lookup"><span data-stu-id="f7efe-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="f7efe-219">È `[Scenario.][ScenarioPair]` una dimensione speciale creata per semplificare la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="f7efe-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="f7efe-220">Sono presenti sei valori corrispondenti a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span><span class="sxs-lookup"><span data-stu-id="f7efe-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="f7efe-221">Quindi, invece di usare una combinazione di 6 filtri per definire uno scenario, è necessario usare solo un filtro.</span><span class="sxs-lookup"><span data-stu-id="f7efe-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="f7efe-222">In questo esempio, il valore `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` si traduce nello scenario in cui: First è server, il secondo non è server, il primo è all'interno, il secondo è all'interno, il primo tipo di connessione è cablato e il secondo tipo di connessione è Wired, che è la definizione esatta di " Server-client-inside Wired ".</span><span class="sxs-lookup"><span data-stu-id="f7efe-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="f7efe-223">Creare un set di filtri per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="f7efe-223">Create one filter set per scenario.</span></span> <span data-ttu-id="f7efe-224">Ogni riga della scorecard, nella figura, rappresenta uno scenario diverso, che sarà un filtro diverso (mentre le dimensioni e le misurazioni rimarranno uguali).</span><span class="sxs-lookup"><span data-stu-id="f7efe-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="f7efe-225">Analizza i risultati delle chiamate AJAX e posizionali nella posizione corretta della tabella.</span><span class="sxs-lookup"><span data-stu-id="f7efe-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="f7efe-226">Dato che si tratta principalmente di manipolazione HTML e JavaScript, non andremo nei dettagli qui.</span><span class="sxs-lookup"><span data-stu-id="f7efe-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="f7efe-227">Il codice viene invece fornito nell'Appendice A.</span><span class="sxs-lookup"><span data-stu-id="f7efe-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f7efe-228">Se CORS (Cross-Origin Resource Sharing) è abilitato, gli utenti potrebbero riscontrare errori come l'intestazione "No ' Access-Control-Allow-Origin" presente nella risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="f7efe-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="f7efe-229">L'origine "null" non è quindi consentito Access ".</span><span class="sxs-lookup"><span data-stu-id="f7efe-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="f7efe-230">Per risolvere il problema, posizionare il file HTML sotto la cartella in cui è installato il portale (per impostazione predefinita, dovrebbe `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`essere.</span><span class="sxs-lookup"><span data-stu-id="f7efe-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="f7efe-231">Quindi, accedere al codice HTML tramite qualsiasi browser con `http://<servername>/cqd/<html_file_name>`l'URL.</span><span class="sxs-lookup"><span data-stu-id="f7efe-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="f7efe-232">(L'URL predefinito per il dashboard di Call Quality dashboard `http://<servername>/cqd.`locale è)</span><span class="sxs-lookup"><span data-stu-id="f7efe-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="f7efe-233">Appendice A</span><span class="sxs-lookup"><span data-stu-id="f7efe-233">Appendix A</span></span>

<span data-ttu-id="f7efe-234">Codice HTML, ad esempio 3 (esempio di scorecard):</span><span class="sxs-lookup"><span data-stu-id="f7efe-234">HTML code for Example 3 (Scorecard sample):</span></span>

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
