---
title: Dati e report in dashboard qualità chiamata (Call Quality Dashboard)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni sui dati e i report disponibili in Microsoft Call Quality Dashboard (Call Quality Dashboard).
ms.openlocfilehash: ec9714e0eae187bc82edf01809b50d8512d04e01
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583093"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dati e report in dashboard qualità chiamata (Call Quality Dashboard)

Microsoft Call Quality Dashboard (Call Quality Dashboard) usa un feed di dati in tempo reale (NRT). I record di chiamata sono disponibili in Call Quality dashboard entro 30 minuti dalla fine di una chiamata. I record di chiamata della pipeline NRT sono disponibili solo per alcuni mesi prima di essere rimossi dal set di dati. 


## <a name="many-ways-to-access-cqd-data"></a>Molti modi per accedere ai dati di Call Quality dashboard

Puoi accedere ai dati di Call Quality dashboard in diversi viali. Scegliere quello che meglio soddisfa le proprie esigenze:

|  |  |
|---------|---------|
|Interfaccia di amministrazione di teams [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | I dati di Call Quality dashboard sono inclusi nella pagina **utenti** nell'interfaccia di amministrazione di teams, che mostra i dati più comuni necessari in un formato di facile lettura. Non è possibile personalizzare i dati di Call Quality dashboard che si trovano in **utenti**.  |
|Portale di [Call Quality dashboard https://cqd.teams.microsoft.com) (](https://cqd.teams.microsoft.com)     | Report di riepilogo e dettagliati affidabili che soddisfano la maggior parte delle esigenze, con il filtro drill-through. È anche possibile personalizzare i report nel portale di Call Quality dashboard. <br><br>Ottenere due [modelli di report di Call Quality dashboard](#import-the-cqd-report-templates) per analizzare i dati nel portale di Call Quality dashboard.       |
|Power BI     | Usare le query dirette per visualizzare i dati di Call Quality dashboard in Power BI usando i [modelli di Power bi personalizzabili](CQD-Power-BI-query-templates.md). [Scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>Puoi anche [usare l'API REST per accedere ai dati di Call Quality dashboard](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) tramite Power bi. Usa questo metodo se vuoi scaricare i tuoi dati di Call Quality dashboard in modo da poterli lavorare offline. Il vantaggio dell'uso di questo metodo è una prestazione migliore, particolarmente utile per i set di dati di grandi dimensioni che si impantanano in Power BI quando si è online.       |
|API di Microsoft Graph     | Accedere ai dati di qualità delle chiamate con l' [API del grafico](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta). Questo è il metodo più complesso, ma offre il massimo controllo e flessibilità per analizzare i dati di qualità delle chiamate. Ad esempio, se devi unirti ad altri dati per l'organizzazione, puoi usare l'API del grafico per creare un modello di dati e incorporare i dati sulla qualità delle chiamate.        |

## <a name="import-the-cqd-report-templates"></a>Importare i modelli di report di Call Quality dashboard

Scaricare [due modelli di report di Call Quality dashboard curati](https://aka.ms/qertemplates) (tutte le reti e le reti gestite) per velocizzare rapidamente l'attività con Call Quality dashboard. Il modello tutte le reti, anche se ottimizzato per l'uso con un file di dati dell'edificio, può essere usato mentre si lavora per la raccolta e il caricamento di informazioni sulla compilazione in Call Quality dashboard, come descritto nella sezione successiva.

**Per importare i modelli (. CQDX) in Call Quality dashboard**

1. In Call Quality Dashboard selezionare **report dettagliati** dal menu nella parte superiore della pagina.

2. Nel riquadro sinistro selezionare **Importa**. Passare al primo modello di CQDX e selezionare **Apri**.

3. Dopo il caricamento del modello, nella finestra popup verrà visualizzato il messaggio "l'importazione di report è stata completata". 

4. Ripetere i passaggi 2 e 3 per il secondo modello di Call Quality dashboard.

> [!NOTE]
> Ogni utente deve importare i modelli di Call Quality dashboard nella propria istanza di Call Quality dashboard. 



## <a name="euii-data"></a>Dati EUII

Per motivi di conformità, i dati di identificazione dell'utente finale (EUII) (noti anche come informazioni personali o PII) vengono conservati solo per 30 giorni. Dato che i dati della NRT attraversano il contrassegno di 30 giorni, i campi che contengono EUII sono deselezionati, con risultati della NRT senza EUII. I campi che contengono i dati di EUII sono:

- Indirizzo IP completo
- Indirizzo MAC (Media Access Control)
- ID set di servizi di base (BSSID)
- URI SIP (Session Initiation Protocol) (solo Skype for business)
- Nome dell'entità utente (UPN)
- Nome endpoint computer
- Feedback Verbatim dell'utente
- ID oggetto (l'ID oggetto Active Directory dell'utente dell'endpoint)

### <a name="admin-roles-with-and-without-euii-access"></a>Ruoli di amministratore con e senza accesso a EUII

Questi [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) ruoli RBAC **DO** hanno accesso a EUII:
- Amministratore globale
- Amministratore del servizio Teams
- Amministratore di Communications Teams
- Tecnico supporto comunicazioni Teams
- Lettore globale
- Amministratore di Skype for business

Questi ruoli RBAC **non** hanno accesso a EUII:
- Lettore di report
- Specialista supporto comunicazioni Teams


## <a name="date-controls"></a>Controlli data

Call Quality dashboard supporta i tipi di tendenza a rotazione seguenti:

- 5 giorni
- 7 giorni
- 30 giorni
- 60-giorno
- 90-giorno

Il parametro data URL accetta un campo Day. I report di giorni lavorativi usano le date specificate nel formato AAAA-MM-DD come ultimo giorno della tendenza. Il parametro data URL "00" indica "oggi".

|URL| Data di fine dell'andamento del giorno di rotolamento|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/dashboard/ <reportid> /2019-02/</span>   |Giorno corrente di feb 2019|
|<span>https:// <cqdv3> /SPD/#/dashboard/ <reportid> /2019-02-15/</span>|15 feb 2019|
|<span>https:// <cqdv3> /SPD/#/dashboard/ <reportid> /00/</span>        |Giorno corrente|
|||

Per impostazione predefinita, il giorno corrente del mese viene usato come ultimo giorno della tendenza del giorno di rotolamento.


## <a name="data-available-in-cqd-reports"></a>Dati disponibili nei report di Call Quality dashboard

Il riepilogo predefinito e i report di Call Quality dashboard dettagliati possono essere necessari per gestire la qualità delle chiamate per l'organizzazione. Se necessario, è possibile [creare report personalizzati](#create-custom-detailed-reports). 

Se si vuole usare Power BI per analizzare i dati di Call Quality dashboard, leggere [usare Power BI per analizzare i dati di Call Quality dashboard per i team](CQD-Power-BI-query-templates.md).

|Funzionalità|Report di riepilogo|Report dettagliati|
|:--- |:--- |:--- |
|Metrica di condivisione applicazioni | No | Sì |
|Supporto per informazioni sulla creazione di clienti | Sì | Sì |
|Supporto per le informazioni sull'endpoint cliente | Solo in <span> CQD.teams.Microsoft.com<span/> | Solo in <span> CQD.teams.Microsoft.com<span/> |
|Supporto analisi drill-down   | No   | Sì   |
|Metriche per l'affidabilità multimediale   | No   | Sì   |
|Report di out-of-the-box   | Sì   | Sì   |
|Report generali   | Sì   | Sì   |
|Set di report per utente   | No   | Sì   |
|Personalizzazione del set di report (aggiunta, eliminazione, modifica di report)   | No   | Sì   |
|Metriche di condivisione dello schermo basate su video   | No   | Sì   |
|Metriche video   | No   | Sì   |
|Quantità di dati disponibili   | Ultimi 12 mesi   | Ultimi 12 mesi   |
|Dati di Microsoft Teams   | Sì   | Sì   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Selezionare i dati del prodotto da visualizzare nei report

Nei report Riepilogo e posizione avanzata è possibile usare l'elenco a discesa **filtro prodotto** per visualizzare tutti i dati del prodotto, solo i dati di Microsoft teams o solo i dati di Skype for business online.
  
![Screenshot: Mostra le opzioni di controllo del filtro prodotto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In report dettagliati è possibile usare la dimensione **is teams** per filtrare i dati in Microsoft teams o nei dati di Skype for business online.

## <a name="summary-reports"></a>Report di riepilogo

Questi sono i report che verranno visualizzati nel dashboard di Call Quality dashboard quando si accede per la prima volta a Call Quality dashboard. Ti offrono un aspetto a colpo d'occhio sulle tendenze di qualità con i report giornalieri, mensili e della tabella per facilitare l'identificazione delle subnet con qualità scadente. 

|Scheda  |  |
|---------|---------|
|Qualità complessiva delle chiamate     | Aggregazione delle altre 3 schede        |
|Server-client     |Dettagli dei flussi tra endpoint server e client         |
|Client-client     |Dettagli dei flussi tra due endpoint client         |
|SLA qualità vocale     |Informazioni sulle chiamate incluse nell' [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) qualità vocale di Skype for business         |

### <a name="overall-call-quality-tab"></a>Scheda qualità complessiva delle chiamate

Usare i dati in questa scheda per valutare lo stato di qualità delle chiamate e le tendenze in base a conteggi flusso e percentuali scadenti. La legenda nell'angolo in alto a destra mostra il colore e gli elementi visivi che rappresentano queste metriche.
  
![Screenshot: visualizzare la scheda qualità chiamata](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
I flussi sono classificati in tre gruppi: Buono, scadente e non classificato. Vengono inoltre calcolati valori di *% poveri* che consentono di ottenere il rapporto tra i flussi classificati come *poveri* e il conteggio totale del flusso classificato. Poiché il *povero% = flussi poveri/(flussi poveri + flussi buoni) * 100*, il *povero%* non è influenzato dalla presenza di più flussi non *classificati* . Per vedere cosa classifica un flusso come scadente o valido, vedere classificazione dello [Stream nel dashboard qualità chiamata](stream-classification-in-call-quality-dashboard.md).
  
Usare la scala a sinistra per misurare i valori del conteggio del flusso.
  
![Screenshot: Mostra i valori del conteggio dei flussi](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Usare la scala a destra per misurare i valori di% poveri.
  
![Screenshot: Mostra i valori di% poveri](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Puoi anche ottenere i valori numerici effettivi passando il puntatore del mouse su una barra.
  
> [!NOTE]
> L'esempio seguente è costituito da un set di dati di esempio molto piccolo e i valori non sono realistici per una distribuzione effettiva.
  
![Screenshot: Mostra il mouse usato per accedere ai dati](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume complessivo del flusso consente di determinare la pertinenza delle percentuali di scarsità calcolate. Minore è il volume dei flussi generali, meno affidabili sono i valori di percentuale di scarsità segnalati.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Scheda client-server e schede client-client

Queste due schede includono dettagli per i flussi che hanno avuto luogo negli scenari endpoint-to-endpoint. La scheda Server-client include quattro sezioni comprimibili che rappresentano quattro scenari in cui i flussi multimediali scorrono.
  
- Cablato all'interno
- Cablata all'esterno
- WiFi all'interno
- WiFi all'esterno

Analogamente, la scheda client-client contiene cinque sezioni comprimibili:

- Cablato all'interno: cablato all'interno
- Cablata all'interno: esterna cablata
- Esterno cablato: collegato all'esterno
- Cablato all'interno: WiFi all'interno
- Cablata all'interno: WiFi all'esterno

#### <a name="inside-versus-outside"></a>All'interno rispetto all'esterno

Call Quality Dashboard classifica un flusso come *all'interno* o all' *esterno* usando le informazioni edilizie, se esiste. Gli endpoint di ogni flusso sono associati a un indirizzo di subnet. Se la subnet si trova nell'elenco delle subnet contrassegnate InsideCorp nelle informazioni di compilazione caricate, viene considerato *all'interno*. Se le informazioni sulla compilazione non sono ancora state caricate, in test vengono sempre classificati i flussi come *all'esterno*. 

Il test interno per uno scenario server-client considera solo l'endpoint client. Poiché i server sono sempre esterni dal punto di vista dell'utente, questo non viene contabilizzato nel test.
  
#### <a name="wired-versus-wifi"></a>Cablata rispetto a WiFi

Come indicano i nomi, i criteri di classificazione si basano sul tipo di connessioni client. Il server è sempre cablato e non è incluso nel calcolo. In un flusso specifico, se uno dei due endpoint è connesso a una rete WiFi, Call Quality dashboard lo classifica come WiFi.
> [!NOTE]
> Dato un flusso, se uno dei due endpoint è connesso a una rete Wi-Fi, viene classificato come WiFi in Call Quality dashboard.
  
  
## <a name="tenant-data-information"></a>Informazioni sui dati del tenant

Il dashboard report di riepilogo di Call Quality dashboard include una pagina di **caricamento dei dati del tenant** , a cui si accede selezionando **Carica dati tenant** dal menu impostazioni nell'angolo in alto a destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio:

- Mappa dell'indirizzo IP e delle informazioni geografiche
- Mappa di ogni punto di accesso wireless e del relativo indirizzo MAC
- Una mappa di endpoint da fare/modello/tipo di endpoint e così via.
  
Ti consigliamo di caricare i dati del tenant, dell'edificio e della posizione in modo che Call Quality dashboard possa includere queste informazioni nei rapporti. Se i dati non sono già stati caricati, leggere [caricare tenant e creare dati](CQD-upload-tenant-building-data.md). 


## <a name="detailed-reports"></a>Report dettagliati

|Nome  |  |
|---------|---------|
|Report con posizione avanzata     |Mostra le tendenze della qualità in base alle informazioni sulla posizione. Questo report viene visualizzato solo se sono stati [caricati i dati del tenant](CQD-upload-tenant-building-data.md).        |
|Report sull'affidabilità     |Include l'audio, il video, la condivisione dello schermo basata su video (VBSS) e i report di condivisione delle app         |
|Report sulla qualità dei risultati dell'esperienza     |Qualità audio e affidabilità per tutti i client e i dispositivi, incluse le sale riunioni. Questi report sono una versione "snella" dei [modelli di Call Quality dashboard](https://aka.ms/QERtemplates)scaricabili, focalizzati sulle aree chiave per analizzare la qualità audio e l'affidabilità.         |
|Report drill-down di qualità     | Drill-down: data per area geografica, località, subnet, ora e utenti         |
|Report drill-down non riuscito     | Drill-down: data per area geografica, località, subnet, ora e utenti        |
|Valutare i report delle chiamate     |Analizzare le valutazioni delle chiamate utente per area geografica, località o per utente. Include feedback Verbatim.         |
|Report del supporto tecnico     |I report del supporto tecnico consentono di esaminare i dati delle chiamate e delle riunioni per singoli utenti, gruppi di utenti o tutti. Incorporando i dati di compilazione e EUII, questi report consentono di identificare i possibili problemi di sistema in base a posizione di rete, dettagli conferenza, dispositivi o firmware.         |
|Report versione client     |Riepilogo versione client: visualizzare le sessioni e i conteggi degli utenti per ogni versione dell'app client<br><br>Versione client per utente: visualizzare i nomi utente per ogni versione dell'app client <br><br>I filtri predefiniti per il tipo di prodotto e client consentono di mettere a punto le versioni a specifici client.         |
|Report endpoint     |Mostra la qualità della chiamata per gli endpoint del computer (modello e modelli). Questi report includono la creazione di dati, se è stata caricata.         |


## <a name="create-custom-detailed-reports"></a>Creare report dettagliati personalizzati

Se i report predefiniti di Call Quality Dashboard non soddisfano le proprie esigenze, seguire queste istruzioni per creare un report personalizzato. Oppure (da gennaio 2020) [Usa invece Power BI per i report di Call Quality dashboard ](cqd-power-bi-query-templates.md).

Nell'elenco a discesa dei report nella parte superiore dello schermo visualizzato all'accesso \( la schermata **Riepilogo report** \) selezionare **report dettagliati** e quindi **nuovo**. Fare clic su **modifica** in un report per visualizzare l'editor di query. Ogni report viene supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di query consente di modificare queste query e le opzioni di visualizzazione del report.
> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una SuperNet (combinazione di più subnet con un unico prefisso di routing). Tutti gli upload di nuovi edifici verranno controllati per gli intervalli sovrapposti. Se in precedenza è stato caricato un file di costruzione, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e correggere il problema prima del caricamento. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare l'errata mappatura delle subnet agli edifici nei report. Alcune implementazioni VPN non segnalano in modo accurato le informazioni sulla subnet. Si consiglia di aggiungere voci separate per ogni indirizzo della subnet VPN in una rete a 32 bit separata per l'aggiunta di una subnet VPN al file di compilazione, anziché una voce per la subnet. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, dovresti avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32, incluso.
>
> La colonna VPN è facoltativa e sarà impostata su 0.  Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da tale riga verrà espansa completamente in modo che corrisponda a tutti gli indirizzi IP nella subnet.  Usare questo metodo con parsimonia e solo per le subnet VPN poiché l'espansione completa di queste subnet avrà un impatto negativo sugli orari delle query per le query che coinvolgono i dati dell'edificio.

Posizionare il puntatore sul grafico a barre e sulle linee di tendenza nel report per visualizzare i valori dettagliati. Il report con lo stato attiva mostrerà il menu azione: **modifica**, **clona**, **Elimina**, **Scarica**ed **Esporta albero dei report**.



## <a name="query-filters"></a>Filtri di query

I filtri di query vengono implementati usando l'editor di query in Call Quality dashboard. Questi filtri vengono usati per ridurre il numero di record restituiti da Call Quality dashboard, riducendo al minimo le dimensioni complessive del report e i tempi di query. Questo è particolarmente utile per filtrare le reti non gestite. I filtri elencati nella tabella seguente usano le espressioni regolari (RegEx).


| Filter         | Descrizione          | Esempio di filtro di query Call Quality dashboard      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno la possibilità di filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su uguale o non uguale, a seconda delle proprie esigenze.      | Nome dell'edificio secondo \<\> \^ \\ s\*\$                       |
| Escludi subnet comuni | Senza un file di compilazione valido per separare il Managed from Managed Networks, le reti Home verranno incluse nei report. Queste subnet Home esulano dall'ambito del controllo e possono essere rapidamente escluse da un report. Le subnet comuni, come definite in questa guida, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Seconda subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Solo all'interno della visualizzazione  | Usato per filtrare un report per Managed (Inside) o non Managed (all'esterno). Il modello Call Quality dashboard gestito è già preconfigurato con questi filtri.       | Secondo all'interno di Corp = all'interno        |

## <a name="report-filters"></a>Filtri di report

Usare i filtri per i report di Call Quality dashboard per limitare lo stato di analisi delle indagini. Usare i filtri del report aggiungendo un filtro al report di cui è stato eseguito il rendering nell'editor di query o direttamente nel report. I filtri di report seguenti vengono usati in tutti i [modelli di Call Quality dashboard](https://aka.ms/QERtemplates).


| Filter     | Descrizione                            | Esempio di filtro report Call Quality dashboard         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Iniziare con l'anno prima e poi mese. | 2017-10                           |
| Alfabetico | Filtri per qualsiasi carattere alfabetico. | [a-z]                             |
| Numerico    | Filtri per qualsiasi carattere numerico.    | [0-9]                             |
| Percentuale | Filtri per una percentuale.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9] [0-9]) |


### <a name="drill-down-filters"></a>Filtri drill-down

I report di Call Quality dashboard includono diversi filtri per il drill-down, che sono potenti strumenti per limitare lo stato attuale delle indagini sulla qualità delle chiamate. Se si seleziona un campo drill-down, il report apre automaticamente la scheda appropriata e filtra il valore selezionato. Se la scheda ha un proprio campo di drill-down e uno è selezionato, vengono applicati entrambi i set di filtri, riducendo progressivamente il set di dati risultante.

![Diagramma che illustra il flusso di report drill-down](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Aggiunta e modifica di campi drill-down

Quando si modifica un report, è possibile specificare i campi di drill-down personalizzati con l'editor di query.

Per iniziare, fare clic su **...** per il report che si vuole modificare, quindi selezionare **modifica**.

![Screenshot della modifica di un campo di drill-down](media/qerguide-image-addeditdrilldownfields.png)

Selezionare una dimensione nell'elenco sul lato sinistro dell'editor di query. Quindi fare clic sull'elenco a discesa sotto l'etichetta **passa a** e selezionare il gruppo di schede e Expander a cui si vuole eseguire il drill-up. Nota: attualmente la funzionalità di drill-down funziona solo passando a schede diverse. Il supporto per la foratura fino a un Expander specifico verrà aggiunto in un secondo momento. Infine, fare clic su **Chiudi** per salvare le modifiche apportate alla dimensione, quindi fare clic su **Salva** per salvare e chiudere l'editor di query.

![Screenshot della selezione di una dimensione nell'editor di query](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtri a selezione multipla

Oltre alla funzionalità di drill-down, Call Quality dashboard supporta anche la specifica di filtri con più valori (o filtri).

Per selezionare più valori di filtro, iniziare aggiungendo un nuovo filtro al report. Fare clic **+** accanto all'etichetta **filtri** , immettere il nome della dimensione che si vuole usare e fare clic su **Aggiungi**.

![Screenshot dell'aggiunta di un filtro a selezione multipla](media/qerguide-image-addmultiselectfilter.png)

Fare quindi clic su **Cerca** (icona di lente di ingrandimento accanto al nuovo filtro). Verrà visualizzato un campo di testo e una serie di opzioni, tra cui **Seleziona tutto** e **Inverti**. Immettere un valore e fare clic su **Cerca** accanto al campo da cercare. In alternativa, lascia vuoto il campo di testo e fai clic su **Cerca** per visualizzare le prime opzioni di 100.

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio  

![Screenshot dell'aggiunta di un filtro di query](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtri a livello di dashboard
In alcuni report di Call Quality dashboard sono stati aggiunti filtri a livello di dashboard, che semplificano la filtrazione in base a parametri comuni. Questi filtri vengono visualizzati all'esterno delle schede del report normale e direttamente sotto il filtro del prodotto e si applicano a tutti i filtri nel dashboard.

![Screenshot di un filtro per Dashboard](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtri URL

Call Quality dashboard supporta l'aggiunta di filtri all'URL. In questo modo è facile condividere o aggiungere un segnalibro a una query Call Quality dashboard. Puoi definire i parametri nell'URL, ad esempio il mese di tendenza, l'ID tenant o la lingua. È anche possibile aggiungere filtri a livello di prodotto o di Dashboard all'URL.
L'esclusione di dati federati da report Call Quality dashboard è utile quando si rimediano edifici gestiti o reti in cui gli endpoint federati potrebbero influenzare i report.

Per aggiungere un filtro, aggiungere il codice seguente alla fine dell'URL:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Per aggiungere un filtro a livello di dashboard a un URL, tale filtro deve esistere in Call Quality dashboard come filtro a livello di prodotto o di dashboard. Aggiungere questi filtri all'URL dopo il mese di tendenza e prima dei parametri dell'URL:

```filter/DATA_MODEL_NAME|VALUE```

Ad esempio, per applicare un valore di filtro prodotto di Microsoft teams, aggiungere le operazioni seguenti:

```filter/[AllStreams].[Is%20Teams]|[True]```

L'intero URL ha un aspetto simile al seguente:

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

Per applicare filtri URL con valori di selezione multipla, separare ogni valore con un carattere pipe (|). Ad esempio:

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

Se specifichi un nome o un valore non valido, il filtro URL non verrà applicato.


È possibile usare un filtro URL per filtrare ogni report per una dimensione specifica. I filtri URL più comuni vengono usati per filtrare i report per escludere la telemetria dei partecipanti federati o concentrarsi solo su team o Skype for business online. L'esclusione di dati federati da report Call Quality dashboard è utile quando si rimediano edifici gestiti o reti in cui gli endpoint federati potrebbero influenzare i report.

| Filter         | Descrizione          | Esempio di filtro di query Call Quality dashboard      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno la possibilità di filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su uguale o non uguale, a seconda delle proprie esigenze.      | Nome dell'edificio secondo \<\> \^ \\ s\*\$                       |
| Escludi subnet comuni | Senza un file di compilazione valido per separare il Managed from Managed Networks, le reti Home verranno incluse nei report. Queste subnet Home esulano dall'ambito del controllo e possono essere rapidamente escluse da un report. Le subnet comuni, come definite in questo articolo, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Seconda subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Solo all'interno della visualizzazione  | Usato per filtrare un report per Managed (Inside) o non Managed (all'esterno). Il modello Call Quality dashboard gestito è già preconfigurato con questi filtri.       | Secondo all'interno di Corp = all'interno        |


#### <a name="how-to-find-your-tenant-id"></a>Come trovare l'ID tenant

L'ID tenant in Call Quality dashboard corrisponde all'ID della directory in Azure. Se non si conosce l'ID directory, è possibile trovarlo nel portale di Azure:

1.  Accedere al portale di Microsoft Azure:<https://portal.azure.com>

2.  Selezionare **Azure Active Directory**.

3.  In **Gestisci**selezionare **Proprietà**. L'ID tenant è nella casella **ID directory** .

È anche possibile trovare l'ID tenant usando PowerShell: 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Confronto tra team e dati di Call Quality dashboard di Skype for business

Anche all'interno della versione più recente di Call Quality Dashboard (cqd.teams.microsoft.com), verranno visualizzate le differenze nei dati tra teams e Skype for business. Alcuni motivi:
- Differenze nei meccanismi per garantire prestazioni e affidabilità
  - Teams ha la riconnessione automatica e il roaming veloce. Skype for business non lo fa.
  - Teams ha una gestione dinamica della larghezza di banda. Skype for business non lo fa.
- Differenze negli [intervalli di indirizzi IP](Office-365-URLs-IP-address-ranges.md) tra team e Skype for business. Gli intervalli di indirizzi IP dei team sono più recenti, che potrebbero causare problemi di connettività al firewall.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Aprire Call Quality Dashboard dal portale legacy di Skype for business

![Icona del logo Skype for business ](media/sfb-logo-30x30.png) **con il portale legacy di Skype for business**

1. Accedere all'organizzazione di Office 365 con un account di amministratore e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
2. Nel riquadro sinistro, in interfaccia di **Amministrazione**, selezionare **Microsoft teams** per aprire l'interfaccia di amministrazione di teams.
3. Nell'interfaccia di amministrazione di teams selezionare **portale legacy** nel riquadro sinistro, selezionare **strumenti**e quindi selezionare **Skype for business online Call Quality dashboard**.

     ![Screenshot: selezionare il dashboard qualità chiamata](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Nella pagina visualizzata accedere con l'account di amministratore globale e quindi specificare le credenziali per l'account quando richiesto.

Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati. 

> [!IMPORTANT]
> A partire da dicembre 2019, è comunque possibile accedere alla versione precedente di Call Quality Dashboard (cqd.lync.com), anche se il portale legacy fornisce un collegamento all'ultima Call Quality Dashboard (cqd.teams.microsoft.com). Alla fine, la versione precedente di Call Quality dashboard verrà disattivata. A partire dal 1 ° luglio 2020, la versione precedente di Call Quality dashboard accede ai dati dal nuovo Call Quality Dashboard ( https://CQD.teams.microsoft.com) e non è più possibile esportare i dati della creazione e del report. Una volta alla fine di 2020, disattiveremo il vecchio Call Quality dashboard e non potrai più accedervi.


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Che cos'è Call Quality dashboard?](CQD-what-is-call-quality-dashboard.md)

[Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e della creazione](CQD-upload-tenant-building-data.md)

[Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)
