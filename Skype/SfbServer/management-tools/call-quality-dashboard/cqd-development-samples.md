---
title: Esempi di sviluppo in DQC
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
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: "Riepilogo: esaminare un'esercitazione e esempi di sviluppo per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832726"
---
# <a name="cqd-development-samples"></a>Esempi di sviluppo in DQC

**Riepilogo:** Esaminare gli esempi di esercitazione e sviluppo per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.

In questo articolo viene fornita un'esercitazione e esempi di sviluppo per Call Quality Dashboard (CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Esempi di sviluppo di Call Quality Dashboard (CQD)

Esercitazione: creazione di una presentazione di report personalizzata utilizzando il servizio dati di CQD e l'API del servizio di repository.

### <a name="introduction-to-cqd"></a>Introduzione a CQD

CQD offre un accesso rapido e semplice alle informazioni sulla qualità delle chiamate aggregate per le distribuzioni di Skype for Business Server in locale. CQD è costituito da tre componenti: il database di archiviazione QoE, il cubo e il portale. Il portale è il livello di presentazione principale e può essere ulteriormente suddiviso nei tre componenti seguenti:

1. Data Service, accessibile per gli utenti autenticati tramite l' [API dei dati per Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).

2. Servizio di repository, accessibile per gli utenti autenticati tramite l' [API del repository per Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).

3. Portale Web, che è l'interfaccia basata su HTML5 che gli utenti di CQD possono visualizzare e interagire. Questo è accessibile per gli utenti autenticati.

I rapporti visualizzati sul portale Web sono raggruppati in "set di report". Nella figura viene visualizzato un set di report con due report. In ogni report di questo dashboard sono riportati i risultati delle query su numero di chiamate valide, di chiamate insufficienti e di percentuale di chiamate insufficienti per diversi mesi, con vari filtri applicati. 

![Report di esempio di CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD viene creato seguendo la metodologia della qualità delle chiamate (CQM), quindi il set predefinito di report è stato disegnato per essere allineato al flusso di analisi introdotto da CQM. Gli utenti hanno inoltre la possibilità di modificare o creare report personalizzati per soddisfare le proprie esigenze. Tuttavia, poiché esistono più modi per visualizzare i dati, la visualizzazione fornita da CQD potrebbe non soddisfare pienamente le esigenze di ogni utente. In tali situazioni, un utente può sfruttare le API dei dati e le API del repository per creare pagine di report personalizzate. In questa esercitazione verrà illustrata una serie di esempi.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Utilizzo del servizio dati da parte del dashboard

Quando si accede alla Home page di CQD (ad esempio http://localhost/cqd) , il set di report e i report corrispondenti per un utente autenticato e autorizzato verranno recuperati dal servizio di repository. Un URL completo verrà creato dall'ID del set di report e l'anno-mese (ID del set di report è il numero intero dopo la sezione '/#/' in URL e, per impostazione predefinita, l'anno-mese corrente viene accodato alla fine dell'ID del set di rapporti dopo la barra). Le definizioni dei rapporti sono archiviate in formato JSON e quando vengono recuperate dal servizio di archiviazione, verranno quindi utilizzate come input per il servizio dati. Il servizio dati genera query MDX (Multi-Dimension Expressions) in base all'input e quindi esegue queste query MDX sul cubo per recuperare i dati per ogni report. 

### <a name="building-customized-reports"></a>Creazione di report personalizzati

CQD ha già molta flessibilità nella personalizzazione dei report, ma potrebbero verificarsi situazioni in cui gli utenti possono aggregare dati tra più report creati in CQD. Ad esempio, potrebbe essere necessario creare un report in cui vengano visualizzate le percentuali di chiamate insufficienti di tutte le combinazioni possibili di chiamate cablate in una tabella (un risultato simile alla figura):

![Tabella CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Se si utilizza il portale fornito da CQD, un utente dovrà passare a più report per estrarre e registrare la percentuale di chiamate non consentite per ognuno di essi, il che può essere laborioso se sono presenti molti punti dati che è necessario raccogliere. Le API dei dati forniscono agli utenti un modo programmatico per ottenere questo risultato, recuperando dati dal servizio dati (ad esempio tramite chiamate AJAX). 

 **Esempio 1: esempio di report semplice**

Per prima cosa, è possibile eseguire un semplice esempio. Se si desidera visualizzare il flusso audio Good e il numero di flussi audio non validi del 2015 febbraio su una pagina HTML come la figura:

![Report di esempio di CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

È necessario inviare una chiamata al servizio dati con i parametri appropriati e visualizzare i risultati della query in una tabella HTML. Di seguito è riportato un esempio del codice JavaScript:

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

1. Creare la query (nell'esempio questo è definito nella variabile ' query '). La query è definita come un oggetto JSON, che include i dati seguenti:

   a. Zero o più dimensioni. Ogni dimensione è indicata da un datamodelname.

   b. Zero o più filtri. Ogni filtro ha:

   - Datamodelname (la dimensione che conterrà il set di filtri).

   - Valore, ovvero il valore che verrà confrontato dall'operando.

   - Operando (tipo di confronto, 0 significa "uguale").

     c. Una o più misure.

2. Inviare la query al servizio dati tramite chiamata AJAX. È necessario fornire i parametri di richiesta seguenti:

   a. URL (che dovrebbe essere http://[nomeserver]/QoEDataService/RunQuery).

   b. Data (rappresenta la rappresentazione in forma di stringa dell'oggetto JSON definito nella variabile ' query '). Il servizio dati restituirà i risultati della query come parametro della funzione di richiamata per ottenere un esito positivo.

   c. Type (per QoEDataService, RunQuery accetta solo le richieste ' POST ').

   d. Async (un flag che indica se la chiamata AJAX deve essere sincrona o asincrona).

   e. contentType (dovrebbe essere "application/json").

   f. operazione riuscita (funzione di richiamata per quando la chiamata AJAX viene completata correttamente).

   g. errore (funzione di gestione degli errori per quando la chiamata AJAX ha esito negativo).

3. Inserire i dati negli elementi div nel codice HTML (nell'esempio riportato di seguito viene eseguito tramite la chiamata di funzione anonima dopo che la richiesta AJAX è stata completata correttamente).

L'inclusione del codice JavaScript in una pagina HTML e la pagina mostrerà un rapporto come quello illustrato nella figura. Il codice HTML completo è il seguente:

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

Finora, la relazione è ancora molto semplice. L'utente può aggiungere altre misure, dimensioni o filtri per personalizzare il report. Ad esempio, se si desidera visualizzare la percentuale di chiamate AppSharing insufficienti, è necessario aggiungere una nuova misura relativa a AppSharing. Se si desidera visualizzare tutte le chiamate TCP v.s. Chiamate UDP, è necessario aggiungere una nuova dimensione per il tipo di trasporto. Se si desidera visualizzare il numero di chiamate insufficienti all'interno di un determinato edificio, è necessario aggiungere un nuovo filtro per selezionare le chiamate da e verso quell'edificio.

 **Esempio 2: esempio di definizione del report**

Potrebbe essere difficile per qualcuno capire come scrivere l'elenco completo delle misure/dimensioni/filtri e i valori corrispondenti durante la creazione di una query. In questo caso, è possibile passare al portale, creare un report utilizzando l'editor di report e visualizzare la stringa JSON della definizione del report e quindi copiare la definizione in un report personalizzato. 

In questo esempio verrà creata una pagina Web come quella illustrata nella figura in cui un utente può immettere l'ID di qualsiasi set di report esistente (o report) e visualizzare la definizione del set di report o del report nella pagina Web. L'utente può quindi collegare la stringa JSON di ogni report in codice simile a quello illustrato nell'esempio 1 e creare qualsiasi report personalizzato che l'utente desidera. 

![Esempio di CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Per creare lo strumento Visualizzatore di definizioni di report, è necessario inviare le chiamate al servizio di repository per recuperare le rappresentazioni di stringa JSON delle definizioni di ogni set di report desiderato. L'API del repository restituirà la definizione del set di report in base a un determinato ID del set di report. 

Un esempio rapido è il seguente: il codice contiene un blocco che è un semplice esempio per inviare una query al servizio di repository per ottenere il contenuto di un elemento di archivio in base all'identificatore. E la parte successiva del codice (metodo processReportSetData) sta inviando chiamate AJAX per ottenere la definizione di ogni report all'interno di tale set di report. Poiché l'ID nel portale Web di CQD è l'ID di un set di report, la chiamata AJAX restituirà un set di report. Ulteriori informazioni sull'API del repository e in particolare, GetItems, sono disponibili negli [elementi Get](get-items.md). 

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

Di seguito viene riportata una pagina Web come quella della figura (senza la definizione del rapporto al momento della visita iniziale). Ottenere l'ID del set di report dal portale di CQD (dopo '/#/' accedere all'URL del portale di CQD (ad esempio, nella prima figura l'ID del set di report è 3024) e inserire l'ID del set di report nella sezione input di questa pagina Web. Premere il pulsante "carica" e vedere la definizione completa (misure, dimensioni, elenchi di filtri) del set di report.

In sintesi, per ottenere rapidamente la definizione completa di un set di report/report. Ecco come procedere:

1. Andare al portale e utilizzare l'editor di query per personalizzare un report (fare clic sul pulsante "modifica" sopra un report per modificare, aggiungere, rimuovere misure/dimensioni/filtri e quindi salvare il report).

2. Ottenere l'ID del set di report dall'URL (il numero intero dopo l'accesso all'URL '/#/').

3. Avviare la pagina Web definizione report creata nell'esempio 2 e immettere l'ID set di report e recuperare la definizione completa di un set di report (da utilizzare nelle chiamate API dati).

   **Esempio 3: esempio di scorecard**

Tempo per un'attività più complessa. Che cosa succede se si desidera creare una pagina Web come la figura? È necessario aggiornare l'esempio 1, (con l'ausilio della pagina Web generata nell'esempio 2 per recuperare la definizione completa di qualsiasi report), in modo da poter gestire una quantità maggiore di dati.

In questo caso, è necessario aggiornare la misura e l'elenco delle dimensioni. Per capire come aggiungere/modificare una misura e/o una dimensione, è possibile seguire le istruzioni riportate nell'esempio 2 e recuperare la definizione del rapporto completo, inclusi gli elenchi di misure e di dimensioni complete. Inserire la definizione del rapporto completo nel codice di esempio. 

Di seguito sono illustrati i passaggi dettagliati per accedere alla pagina della scorecard nella figura del campione fornito nell'esempio 1:

1. Aggiornare le misure nella variabile ' query ' da  `[Measures].[Audio Good Streams JPDR Count]` e `[Measures].[Audio Poor Streams JPDR Count]` verso `[Measures].[AudioPoorJPDRPercentage]` . 

2. Aggiornare i filtri. I dati JSON per i filtri nell'esempio 1 dispongono di un solo filtro, che è impostato sulla dimensione  `[StartDate].[Month]` . Poiché i filtri sono una matrice JSON, è possibile aggiungere ulteriori dimensioni all'elenco dei filtri. Ad esempio, per ottenere il client del server all'interno delle chiamate cablate per il "currentMonth", è necessario disporre dei filtri seguenti:

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

   Qui la dimensione  `[Scenarios].[ScenarioPair]` è impostata su Equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` . La  `[Scenario.][ScenarioPair]` è una dimensione speciale creata per semplificare la creazione dei report. Contiene sei valori corrispondenti a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` . Pertanto, invece di utilizzare una combinazione di 6 filtri per definire uno scenario, è necessario utilizzare solo 1 filtro. In questo esempio, il valore si  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` traduce nello scenario in cui: First è server, il secondo non è server, First è all'interno, il secondo è all'interno, il primo tipo di connessione è cablato e il secondo tipo di connessione è cablato, che è la definizione esatta di "server-client-inside Wired".

3. Creare un set di filtri per ogni scenario. Ogni riga della scorecard, nella figura, rappresenta un altro scenario, che sarà un altro filtro (mentre le dimensioni e le misure rimarranno uguali). 

4. Analizzare i risultati delle chiamate AJAX e inserirli nella posizione corretta della tabella. Poiché si tratta principalmente di manipolazione HTML e JavaScript, non entreremo nei dettagli qui. Al contrario, il codice viene fornito nell'Appendice A.

    > [!NOTE]
    >  Se è abilitata la condivisione risorse CORS (Cross-Origining Resource), gli utenti potrebbero riscontrare errori come l'intestazione "No ' Access-Control-Allow-Origin ' è presente nella risorsa richiesta. L'origine ' null ' non è pertanto consentita per l'accesso ". Per risolvere il problema, inserire il file HTML nella cartella in cui è installato il portale (per impostazione predefinita, dovrebbe essere `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` . Accedere quindi al codice HTML tramite qualsiasi browser con l'URL  `http://<servername>/cqd/<html_file_name>` . (L'URL predefinito per il dashboard di CQD locale è  `http://<servername>/cqd.` ) 

### <a name="appendix-a"></a>Appendice A

Codice HTML per esempio 3 (esempio di scorecard):

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
