---
title: Esempi di sviluppo in DQC
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
ms.openlocfilehash: 5e650047fefb865f7fe9af84f93a5f57e7bbf086
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992863"
---
# <a name="cqd-development-samples"></a>Esempi di sviluppo in DQC

**Riepilogo:** Esaminare gli esempi di esercitazione e sviluppo per dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.

Questo articolo contiene un'esercitazione ed esempi sullo sviluppo di Call Quality Dashboard (Call Quality Dashboard).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Esempi di sviluppo di Call Quality Dashboard (Call Quality Dashboard)

Esercitazione: creazione di una presentazione di report personalizzata con il servizio dati Call Quality dashboard e l'API del servizio repository.

### <a name="introduction-to-cqd"></a>Introduzione a Call Quality dashboard

Call Quality dashboard offre un accesso rapido e semplice alle informazioni di qualità delle chiamate aggregate per le distribuzioni locali di Skype for Business Server. Call Quality dashboard è costituito da tre componenti: il database di archiviazione QoE, il cubo e il portale. Il portale è il livello principale della presentazione e può essere ulteriormente suddiviso nei tre componenti seguenti:

1. Servizio dati, accessibile per gli utenti autenticati tramite l' [API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server](data-api.md).

2. Servizio repository, accessibile per gli utenti autenticati tramite l' [API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server](repository-api.md).

3. Web Portal, ovvero l'interfaccia basata su HTML5 con cui gli utenti di Call Quality dashboard vedono e interagiscono. Questa operazione è accessibile per gli utenti autenticati.

I report visualizzati nel portale Web sono raggruppati in "set di report". La figura mostra un set di report con due report. Ogni report in questo dashboard seguente mostra i risultati delle query su numero di chiamate valide, chiamate scadenti e percentuale di chiamata scadente per diversi mesi, con vari filtri applicati. 

![Report di esempio Call Quality dashboard](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

Call Quality dashboard viene creato seguendo la metodologia di qualità delle chiamate (CQM), quindi il set di report predefinito è progettato per essere allineato al flusso di analisi introdotto da CQM. Gli utenti hanno anche la possibilità di modificare o creare report personalizzati per soddisfare le proprie esigenze. Tuttavia, dato che esistono diversi modi per visualizzare i dati, la visualizzazione fornita da Call Quality Dashboard potrebbe non rispondere completamente alle esigenze di ogni utente. In questi casi, un utente può sfruttare le API dei dati e le API del repository per creare pagine del report personalizzate. In questa esercitazione verrà illustrata una serie di esempi.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Modalità di utilizzo del servizio dati da parte del dashboard

Quando si passa alla Home page di Call Quality Dashboard (ad http://localhost/cqd)esempio, il set di report e i report corrispondenti per un utente autenticato e autorizzato verranno recuperati dal servizio repository. Un URL completo verrà costruito dall'ID set di report e l'anno-mese (ID set di report è il numero intero dopo la sezione "/#/" in URL e per impostazione predefinita l'anno-mese corrente viene accodato alla fine del report-ID set dopo la barra). Le definizioni del report sono archiviate in formato JSON e, se recuperate dal servizio repository, verranno usate come input per il servizio dati. Il servizio dati genera query MDX (Multi-Dimension Expression) in base all'input e quindi esegue queste query MDX sul cubo per recuperare i dati per ogni report. 

### <a name="building-customized-reports"></a>Creazione di report personalizzati

Call Quality Dashboard ha già molta flessibilità nella personalizzazione dei report, ma potrebbero esserci situazioni in cui gli utenti potrebbero voler aggregare i dati in più report creati in Call Quality dashboard. Ad esempio, potrebbe essere necessario creare un report che mostra le percentuali di chiamata scadente di tutte le possibili combinazioni di chiamate cablate in una tabella (risultato simile alla figura):

![Tabella Call Quality dashboard](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Usando il portale fornito da Call Quality dashboard, un utente dovrebbe passare a più report per estrarre e registrare la povera chiamata% per ognuno, che può essere laboriosa se sono presenti molti punti dati da raccogliere. Le API dei dati consentono agli utenti di eseguire questa operazione a livello di codice, recuperando i dati dal servizio dati (ad esempio tramite chiamate AJAX). 

 **Esempio 1: esempio di report semplice**

Prendiamo prima di tutto un semplice esempio. Se si vuole visualizzare il flusso audio buono e il conteggio dei flussi audio non validi di 2015 febbraio in una pagina HTML come la figura:

![Report di esempio di Call Quality dashboard](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Ciò che serve è inviare una chiamata al servizio dati con i parametri corretti e visualizzare i risultati della query in una tabella HTML. Di seguito è riportato un esempio di codice JavaScript:

```javascript        
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

Questo esempio può essere ulteriormente decostruito in tre passaggi:

1. Costruisci la query (nell'esempio questo è definito nella variabile "query"). La query è definita come oggetto JSON, che include i dati seguenti:

   un. Zero o più dimensioni. Ogni dimensione è indicata da una datamodelname.

   b. Zero o più filtri. Ogni filtro ha:

   - Datamodelname (la dimensione che avrà il set di filtri).

   - Value (il valore che verrà confrontato dall'operando).

   - Operando (tipo di confronto, 0 significa "uguale").

     c. Una o più misure.

2. Inviare la query al servizio dati tramite chiamata AJAX. I parametri di richiesta seguenti devono essere forniti:

   un. URL (che deve essere http://[nomeserver]/QoEDataService/RunQuery).

   b. Data (questa è la rappresentazione di stringa dell'oggetto JSON definito nella variabile di query). Il servizio dati restituirà i risultati della query come parametro della funzione di richiamata per l'esito positivo.

   c. Type (per QoEDataService, RunQuery accetta solo le richieste "POST").

   3D. Async (un contrassegno che indica se la chiamata AJAX deve essere sincrona o asincrona).

   e. contentType (deve essere "application/json").

   f. operazione riuscita (funzione di richiamata per quando la chiamata AJAX viene completata correttamente).

   g. errore (funzione di gestione degli errori per la chiamata AJAX non riesce).

3. Inserire dati in elementi div nell'HTML (nell'esempio nel codice, questa operazione viene eseguita tramite la chiamata di funzione anonima dopo che la richiesta AJAX è stata completata correttamente).

Racchiudere il codice JavaScript in una pagina HTML e la pagina mostrerà un report come quello mostrato nella figura. Il codice HTML completo è il seguente:

```javascript
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

Finora il report è ancora molto semplice. Per personalizzare il report, l'utente può aggiungere altre misure, dimensioni o filtri. Ad esempio, se si vuole visualizzare la percentuale di chiamata condivisione applicazioni scadente, è necessario aggiungere una nuova misura per quanto riguarda condivisione applicazioni. Se si vuole visualizzare tutte le chiamate TCP v.s. Chiamate UDP, deve essere aggiunta una nuova dimensione per il tipo di trasporto. Se si vuole visualizzare il numero di chiamate non consentite in un determinato edificio, è necessario aggiungere un nuovo filtro per selezionare le chiamate da e verso l'edificio.

 **Esempio 2: esempio di definizione del report**

Potrebbe essere difficile per qualcuno capire come scrivere l'elenco completo di misure/dimensioni/filtri e i valori corrispondenti durante la costruzione di una query. In questo caso, è possibile accedere al portale, creare un report usando l'editor report e visualizzare la stringa JSON della definizione del report e quindi copiare la definizione in un report personalizzato. 

In questo esempio creeremo una pagina Web come quella mostrata nella figura in cui un utente può immettere l'ID di qualsiasi set di report esistente (o report) e visualizzare la definizione del set di report o del report nella pagina Web. L'utente può quindi connettere la stringa JSON di ogni report in codice simile a quello mostrato nell'esempio 1 e creare un report personalizzato che l'utente desidera. 

![Esempio di Call Quality dashboard](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Per creare lo strumento Visualizzatore definizione report, è necessario inviare chiamate al servizio repository per recuperare le rappresentazioni di stringa JSON delle definizioni di ogni set di report desiderato. L'API del repository restituirà la definizione di set di report in base a un ID set di report specifico. 

Un esempio rapido è il seguente: il codice contiene un blocco che è un semplice esempio per inviare una query al servizio repository per ottenere il contenuto di un elemento del repository in base al relativo identificatore. E la parte successiva del codice (metodo processReportSetData) sta inviando chiamate AJAX per ottenere la definizione di ogni report all'interno del set di report. Dato che l'ID nel portale Web di Call Quality dashboard è l'ID di un set di report, la chiamata AJAX restituirà un elemento del set di report. Altri dettagli sull'API del repository e in particolare su GetItems possono essere trovati negli [elementi Get](get-items.md). 

```html
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

Il risultato precedente si tradurrà in una pagina Web come quella della figura (senza la definizione del rapporto alla prima visita). Ottenere l'ID set di report dal portale di Call Quality Dashboard (dopo l'accesso a "/#/", accedere all'URL del portale di Call Quality dashboard, ad esempio nella prima figura l'ID set di report è 3024) e inserire l'ID del set di report nella sezione input di questa pagina Web. Premere il pulsante "carica" e vedere la definizione completa (misure, dimensioni, elenchi filtri) del set di report.

In Riepilogo, per ottenere rapidamente la definizione completa di un set di report/report. I passaggi sono i seguenti:

1. Accedere al portale e usare l'editor di query per personalizzare un report (fare clic sul pulsante "modifica" sopra un report per modificare, aggiungere, rimuovere misure/dimensioni/filtri e quindi salvare il report).

2. Ottenere l'ID del set di report da URL (il numero intero dopo l'accesso all'URL "/#/").

3. Avviare questa pagina Web di definizione del report creata nell'esempio 2 e immettere l'ID set di report e recuperare la definizione completa di un set di report (da usare nelle chiamate API dati).

   **Esempio 3: esempio di scorecard**

Tempo per un'attività più complessa. Cosa fare se si vuole creare una pagina Web come la figura? È necessario aggiornare l'esempio 1 (con l'aiuto della pagina Web generata nell'esempio 2 per recuperare la definizione completa di qualsiasi report) in modo da poter gestire una maggiore quantità di dati.

In questo caso, è necessario aggiornare l'elenco di misure e dimensioni. Il modo per capire come aggiungere/modificare una misurazione e/o una dimensione consiste nel seguire le istruzioni dell'esempio 2 e recuperare la definizione completa del report, inclusi gli elenchi di misura e di dimensione completi. Inserire la definizione completa del report nel codice di esempio. 

Ecco la procedura dettagliata per ottenere la pagina della scorecard nella figura dell'esempio 1:

1. Aggiornare le misure nella variabile "query" da `[Measures].[Audio Good Streams JPDR Count]` e `[Measures].[Audio Poor Streams JPDR Count]` verso `[Measures].[AudioPoorJPDRPercentage]`. 

2. Aggiornare i filtri. I dati JSON per i filtri nell'esempio 1 includono un filtro, che è impostato sulla dimensione `[StartDate].[Month]`. Dato che Filters è una matrice JSON, è possibile aggiungere altre dimensioni all'elenco dei filtri. Ad esempio, per ottenere il client-server all'interno delle chiamate cablate per "currentMonth", dovremmo avere i seguenti filtri:

   ```javascript
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

   Qui la dimensione `[Scenarios].[ScenarioPair]` è impostata su uguale `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`. È `[Scenario.][ScenarioPair]` una dimensione speciale creata per semplificare la creazione di report. Sono presenti sei valori corrispondenti a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`. Quindi, invece di usare una combinazione di 6 filtri per definire uno scenario, è necessario usare solo un filtro. In questo esempio, il valore `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` si traduce nello scenario in cui: First è server, il secondo non è server, il primo è all'interno, il secondo è all'interno, il primo tipo di connessione è cablato e il secondo tipo di connessione è Wired, che è la definizione esatta di "server-client-inside Wired".

3. Creare un set di filtri per ogni scenario. Ogni riga della scorecard, nella figura, rappresenta uno scenario diverso, che sarà un filtro diverso (mentre le dimensioni e le misurazioni rimarranno uguali). 

4. Analizza i risultati delle chiamate AJAX e posizionali nella posizione corretta della tabella. Dato che si tratta principalmente di manipolazione HTML e JavaScript, non andremo nei dettagli qui. Il codice viene invece fornito nell'Appendice A.

    > [!NOTE]
    >  Se CORS (Cross-Origin Resource Sharing) è abilitato, gli utenti potrebbero riscontrare errori come l'intestazione "No ' Access-Control-Allow-Origin" presente nella risorsa richiesta. L'origine "null" non è quindi consentito Access ". Per risolvere il problema, posizionare il file HTML sotto la cartella in cui è installato il portale (per impostazione predefinita, dovrebbe `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`essere. Quindi, accedere al codice HTML tramite qualsiasi browser con `http://<servername>/cqd/<html_file_name>`l'URL. (L'URL predefinito per il dashboard di Call Quality dashboard `http://<servername>/cqd.`locale è) 

### <a name="appendix-a"></a>Appendice A

Codice HTML, ad esempio 3 (esempio di scorecard):

```html
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
