---
title: Dati e report in Call Quality Dashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni sui dati e i report disponibili in Microsoft Call Quality Dashboard (CQD).
ms.openlocfilehash: ba30be8d63dab1f5720be5637ea0a28c26d5d877
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789811"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dati e report in Call Quality Dashboard (CQD)

Microsoft Call Quality Dashboard (CQD) utilizza un feed di dati NRT (Near Real-Time). I record delle chiamate sono disponibili in Call Quality Dashboard entro 30 minuti dalla fine di una chiamata. I record delle chiamate dalla pipeline NRT sono disponibili solo per alcuni mesi prima che vengano rimossi dal set di dati.

## <a name="many-ways-to-access-cqd-data"></a>Molti modi per accedere ai dati di Call Quality Dashboard

È possibile accedere ai dati di Call Quality Dashboard da diverse posizioni. Scegli quello più adatto alle tue esigenze:

|&nbsp;|&nbsp;|
|---|---|
|Interfaccia di amministrazione di Teams [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)|Call Quality Dashboard è incluso nella pagina **Utenti** dell'interfaccia di amministrazione di Teams, che mostra i dati più comuni in un formato di facile lettura. Non è possibile personalizzare i dati di Call Quality Dashboard disponibili in **Utenti**.|
|Call Quality Dashboard [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)|Riepilogo completo e report dettagliati che soddisfano le più esigenze, con il filtro drill-through. È anche possibile personalizzare i report nel portale di Call Quality Dashboard. <br><br>Ottenere due [modelli di report di Call Quality Dashboard](#import-the-cqd-report-templates) per analizzare i dati nel portale di Call Quality Dashboard.|
|Power BI|Usare le query dirette per visualizzare i dati di Call Quality Dashboard in Power BI usando [modelli di Power BI personalizzabili](CQD-Power-BI-query-templates.md). [Scaricare i modelli di query di Power BI per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>È anche possibile [usare l'API REST per accedere ai dati di Call Quality Dashboard](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) tramite Power BI. Usare questo metodo se si vogliono scaricare i dati di Call Quality Dashboard in modo da potervi lavorare offline. L'uso di questo metodo offre prestazioni migliori, particolarmente utili per set di dati di grandi dimensioni che si arrestano in Power BI quando si è online.|
|API di Microsoft Graph|Accedi ai dati sulla qualità delle chiamate manualmente usando il [API Graph](/graph/api/resources/callrecords-api-overview). Questo è il metodo più complesso, ma offre il maggior controllo e la massima flessibilità nell'analisi dei dati sulla qualità delle chiamate. Ad esempio, se è necessario aggiungerli ad altri dati per l'organizzazione, è possibile usare il API Graph per creare un modello di dati e incorporare i dati sulla qualità delle chiamate.|

## <a name="import-the-cqd-report-templates"></a>Importare i modelli di report call quality dashboard

Scarica [due modelli di report CQD curati](https://aka.ms/qertemplates) (Tutte le reti e Le reti gestite) per aiutarti a diventare rapidamente operativo con Call Quality Dashboard. Il modello Tutte le reti, sebbene ottimizzato per l'uso con un file di dati dell'edificio, può essere usato mentre si lavora alla raccolta e al caricamento di informazioni sull'edificio in Call Quality Dashboard, come descritto nella sezione successiva.

**Per importare i modelli (. CQDX) in Call Quality Dashboard**:

1. In Call Quality Dashboard selezionare **Report dettagliati** dal menu nella parte superiore della pagina.

2. Nel riquadro sinistro seleziona **Importa**. Passare al primo modello CQDX e selezionare **Apri**.

3. Dopo il caricamento del modello, in una finestra popup viene visualizzato il messaggio "Importazione del report completata".

4. Ripetere i passaggi 2 e 3 per il secondo modello CQD.

   > [!NOTE]
   > Ogni utente deve importare i modelli di Call Quality Dashboard nella propria istanza di Call Quality Dashboard.

## <a name="euii-data"></a>Dati EUII

Per motivi di conformità, i dati identificativi dell'utente finale (INFORMAZIONI PERSONALI) vengono conservati solo per 28 giorni. Quando i dati NRT attraversano il contrassegno di 28 giorni, i campi che contengono EUII vengono cancellati, generando dati NRT privi di EUII. I campi che contengono dati EUII sono:

- Indirizzo IP completo
- Indirizzo mac (Media Controllo di accesso)
- Identificatore del set di servizi di base (BSSID)
- URI SIP (Session Initiation Protocol) (solo Skype for Business)
- Nome entità utente (UPN)
- Nome endpoint computer
- Feedback degli utenti verbali
- ID oggetto (ID oggetto Active Directory dell'utente dell'endpoint)
- Numero di telefono

### <a name="admin-roles-with-and-without-euii-access"></a>Amministrazione ruoli con e senza accesso EUII

Questi ruoli [RBAC](/azure/role-based-access-control/overview) **hanno** accesso EUII:

- Amministrazione globale
- Amministrazione del servizio Teams
- Teams Communications Amministrazione
- Tecnico supporto comunicazioni Teams
- Lettore globale
- Skype for Business Amministrazione

Questi ruoli RBAC **non** hanno accesso EUII:

- Lettore di report
- Specialista del supporto tecnico per le comunicazioni di Teams

## <a name="date-controls"></a>Controlli data

Call Quality Dashboard supporta i seguenti tipi di tendenza mobile:

- 5 giorni
- 7 giorni
- 30 giorni
- 60 giorni
- 90 giorni

Il parametro URL Date accetta un campo Day. I report relativi ai giorni di distribuzione usano le date specificate nel formato AAAA-MM-GG come ultimo giorno della tendenza. Il parametro Url Date "00" indica "oggi".

|URL|Data di fine della tendenza del giorno di distribuzione|
|:---|:---|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02/</span>|Giorno corrente di febbraio 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02-15/</span>|15 febbraio 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/00/</span>|Giorno corrente|

Per impostazione predefinita, il giorno corrente del mese viene usato come ultimo giorno della tendenza dei giorni di distribuzione.

## <a name="data-available-in-cqd-reports"></a>Dati disponibili nei report di Call Quality Dashboard

Il riepilogo predefinito e i report dettagliati di Call Quality Dashboard possono essere tutto ciò che serve per gestire la qualità delle chiamate per l'organizzazione. Se necessario, è possibile [creare report personalizzati](#create-custom-detailed-reports).

Se si vuole usare Power BI per analizzare i dati di Call Quality Dashboard, vedere [Usare Power BI per analizzare i dati CQD per Teams](CQD-Power-BI-query-templates.md).

|Funzionalità|Report di riepilogo|Report dettagliati|
|:---|:---|:---|
|Metrica condivisione applicazioni|No|Sì|
|Supporto per informazioni sulla creazione di clienti|Sì|Sì|
|Supporto per le informazioni sull'endpoint del cliente|Solo in <span>cqd.teams.microsoft.com<span/>|Solo in <span>cqd.teams.microsoft.com<span/>|
|Supporto dell'analisi drill-down|No|Sì|
|Metriche di affidabilità dei supporti|No|Sì|
|Report predefiniti|Sì|Sì|
|Report di panoramica|Sì|Sì|
|Set di report per utente|No|Sì|
|Personalizzazione del set di report (aggiunta, eliminazione, modifica di report)|No|Sì|
|Metriche di condivisione dello schermo basata su video|No|Sì|
|Metriche video|No|Sì|
|Quantità di dati disponibili|Ultimi 12 mesi|Ultimi 12 mesi|
|Dati di Microsoft Teams|Sì|Sì|

### <a name="select-product-data-to-see-in-reports"></a>Selezionare i dati del prodotto da visualizzare nei report

Nel riepilogo e nei report di Location-Enhanced, è possibile usare l'elenco a discesa **Filtro prodotti** per visualizzare tutti i dati di prodotto, solo i dati di Microsoft Teams o solo Skype for Business dati online.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra le opzioni di controllo Filtro prodotti.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

Nei report dettagliati è possibile usare la dimensione **È Teams** per filtrare i dati in base a Microsoft Teams o Skype for Business dati online.

## <a name="summary-reports"></a>Report di riepilogo

Questi sono i report che verranno visualizzati nel dashboard di Call Quality Dashboard quando si accede per la prima volta a Call Quality Dashboard. Offrono uno sguardo immediato alle tendenze di qualità con report giornalieri, mensili e di tabella per facilitare l'identificazione delle subnet di scarsa qualità.

|Scheda|Descrizione|
|---|---|
|Qualità complessiva delle chiamate|Aggregare le altre 3 schede.|
|Server - Client|Dettagli dei flussi tra endpoint server e client.|
|Client - Client|Dettagli dei flussi tra due endpoint client.|
|Contratto di servizio sulla qualità vocale|Informazioni sulle chiamate incluse nel [contratto](https://go.microsoft.com/fwlink/p/?linkid=846252) di servizio sulla qualità vocale Skype for Business.|

### <a name="overall-call-quality-tab"></a>Scheda Generale Qualità chiamata

Usare i dati in questa scheda per valutare lo stato e le tendenze della qualità delle chiamate in base al conteggio dei flussi e alle percentuali scadenti. La legenda nell'angolo in alto a destra mostra il colore e gli elementi visivi che rappresentano queste metriche.

> [!div class="mx-imgBorder"]
> ![Screenshot: visualizzare la scheda Qualità chiamata.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

I flussi sono classificati in tre gruppi: Buono, Scadente e Non classificato. Sono anche stati calcolati valori  *poor %*  che forniscono il rapporto tra flussi classificati come *scadenti*  e il numero totale di flussi classificati. Poiché *% scarsa = flussi scadenti/(flussi scadenti + flussi buoni) \* 100*, la *percentuale scarsa* non è interessata dalla presenza di più flussi *non classificati*  . Per vedere cosa classifica un flusso come scadente o buono, consulta [Classificazione flusso nel dashboard qualità chiamata](stream-classification-in-call-quality-dashboard.md).

Usare la scala a sinistra per misurare i valori del conteggio dei flussi.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra i valori del numero di flussi.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

Usare la scala a destra per misurare i valori della percentuale di povertà.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra i valori % scadenti.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

È anche possibile ottenere i valori numerici effettivi passando il mouse su una barra.

> [!NOTE]
> L'esempio seguente riguarda un set di dati di esempio molto piccolo e i valori non sono realistici per una distribuzione effettiva.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra il mouse usato per accedere ai dati.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

Il volume complessivo dei flussi consente di determinare la rilevanza delle percentuali calcolate per i flussi di flussi scadenti. Minore è il volume complessivo dei flussi, meno affidabili sono i valori della percentuale di scarsa riferita.

### <a name="server-client-tab-and-client-client-tabs"></a>scheda Server-Client e schede di Client-Client

Queste due schede forniscono dettagli sui flussi che hanno avuto luogo negli scenari endpoint-endpoint. La scheda Server-Client include quattro sezioni comprimibili che rappresentano quattro scenari in cui scorrerebbero flussi multimediali.

- Cablata all'interno
- Cablata esterna
- WiFi interno
- WiFi esterno

Analogamente, la scheda Client-Client include cinque sezioni comprimibili:

- Cablata all'interno - Cablata all'interno
- Cablata all'interno - Cablata all'esterno
- Cablata all'esterno - Cablata all'esterno
- Cablata all'interno - WiFi interno
- Cablata all'interno - WiFi esterno

#### <a name="inside-versus-outside"></a>All'interno e all'esterno

Call Quality Dashboard classifica un flusso come  *Interno*  o *Esterno*  usando informazioni di tipo Building, se presenti. Gli endpoint di ogni flusso sono associati a un indirizzo subnet. Se la subnet è nell'elenco delle subnet contrassegnate InsideCorp nelle informazioni dell'edificio caricato, allora è considerato *Interno*. Se le informazioni sull'edificio non sono ancora state caricate, Inside Test classifica sempre i flussi come *esterni*.

Il test interno per uno scenario di Server-Client considera solo l'endpoint client. Poiché i server sono sempre esterni dal punto di vista di un utente, questo non viene contabilitato nel test.

#### <a name="wired-versus-wifi"></a>Cablata o WiFi

Come indicano i nomi, i criteri di classificazione si basano sul tipo di connessioni client. Il server è sempre cablato e non è incluso nel calcolo. In un determinato flusso, se uno dei due endpoint è connesso a una rete WiFi, call quality dashboard lo classifica come WiFi.

> [!NOTE]
> Dato uno stream, se uno dei due endpoint è connesso a una rete WiFi, viene classificato come WiFi in Call Quality Dashboard.

## <a name="tenant-data-information"></a>Informazioni sui dati del tenant

Il dashboard Report di riepilogo di Call Quality Dashboard include una pagina **Caricamento dati tenant** , accessibile selezionando **Caricamento dati tenant** dal menu delle impostazioni nell'angolo in alto a destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio:

- Mappa dell'indirizzo IP e delle informazioni geografiche.
- Mappa di ogni AP wireless e del relativo indirizzo MAC.
- Mappa dell'endpoint alla creazione/modello/tipo dell'endpoint e così via.

È consigliabile caricare i dati relativi a tenant, edificio e posizione in modo che Call Quality Dashboard possa includere queste informazioni nei report. Se questi dati non sono ancora stati caricati, leggere Caricare i [dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md).

## <a name="detailed-reports"></a>Report dettagliati

|Nome|Descrizione|
|---|---|
|Report Location-Enhanced|Mostra le tendenze di qualità in base alle informazioni sulla posizione. Questo report viene visualizzato solo se sono stati [caricati i dati del tenant](CQD-upload-tenant-building-data.md).|
|Report di affidabilità|Include audio, video, condivisione dello schermo basata su video (VBSS) e report di condivisione app.|
|Rapporti sulla qualità dell'esperienza|Qualità e affidabilità dell'audio per tutti i client e i dispositivi, incluse le sale riunioni. Questi report sono una versione "ridotta" dei [modelli scaricabili di Call Quality Dashboard](https://aka.ms/QERtemplates), incentrati sulle aree chiave per l'analisi della qualità e dell'affidabilità dell'audio.|
|Report drill-down di qualità|Drill-down: Data per area geografica, località, subnet, ora e utenti.|
|Report drill-down degli errori|Drill-down: Data per area geografica, località, subnet, ora e utenti.|
|Valutare i report delle chiamate|Analizzare le valutazioni delle chiamate degli utenti in base all'area geografica, alla posizione o in base all'utente. Include feedback testuale.|
|Report dell'Help Desk|I report dell'help desk esaminano i dati delle chiamate e delle riunioni per singoli utenti, gruppi di utenti o tutti. Incorporando i dati building e EUII, questi report aiutano a identificare i possibili problemi di sistema in base al percorso di rete, ai dettagli della conferenza, ai dispositivi o al firmware.|
|Report sulla versione client|Riepilogo della versione client: visualizzare il numero di sessioni e utenti per ogni versione dell'app client<br><br>Versione client per utente: visualizzare i nomi utente per ogni versione dell'app client <br><br>I filtri predefiniti per tipo di prodotto e client consentono di concentrare le versioni su client specifici.|
|Report endpoint|Mostra la qualità delle chiamate in base agli endpoint del computer (computer make and model). Questi report includono la creazione di dati, se sono stati caricati.|

## <a name="create-custom-detailed-reports"></a>Creare report dettagliati personalizzati

Se i report CQD predefiniti non soddisfano le proprie esigenze, usare queste istruzioni per creare un report personalizzato. In alternativa, a partire da gennaio 2020 [, usare Power BI per i report di Call Quality Dashboard ](cqd-power-bi-query-templates.md).

Nell'elenco a discesa dei report nella parte superiore della schermata visualizzata all'accesso\(, nella schermata\) **Report di riepilogo** selezionare **Report dettagliati** e quindi **Nuovo**. Fare clic su **Modifica** in un report per visualizzare il Editor di query. Ogni report è supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. La Editor di query consente di modificare queste query e le opzioni di visualizzazione del report.

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di edifici verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo building, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può causare la mappatura errata delle subnet agli edifici nei report. Alcune implementazioni VPN non riportano in modo accurato le informazioni sulla subnet. Quando si aggiunge una subnet VPN al file dell'edificio, invece di una voce per la subnet, vengono aggiunte voci separate per ogni indirizzo nella subnet VPN come rete a 32 bit separata. Ogni riga può avere gli stessi metadati di compilazione. Ad esempio, invece di una riga per 172.16.18.0/24, è necessario avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32 incluse.
>
> La colonna VPN è facoltativa e per impostazione predefinita è 0.  Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da quella riga verrà completamente espansa in modo che corrisponda a tutti gli indirizzi IP all'interno della subnet.  Utilizza questa opzione con moderazione e solo per le subnet VPN, poiché l'espansione completa di queste subnet avrà un impatto negativo sui tempi di query per le query che implicano la creazione di dati.

Posizionare il puntatore del mouse su grafici a barre e linee di tendenza nel report per visualizzare valori dettagliati. Il report con lo stato attivo mostrerà il menu azione: **Modifica**, **Clona**, **Elimina**, **Scarica** ed **Esporta albero dei report**.

## <a name="query-filters"></a>Filtri di query

I filtri di query vengono implementati usando il Editor di query in Call Quality Dashboard. Questi filtri vengono usati per ridurre il numero di record restituiti da Call Quality Dashboard, riducendo così le dimensioni complessive del report e i tempi di query. Ciò è particolarmente utile per filtrare le reti non gestite. I filtri elencati nella tabella seguente usano espressioni regolari (RegEx).

|Filter|Descrizione|Esempio di filtro query CQD|
|---|---|---|
|Nessun valore vuoto|Alcuni filtri non hanno l'opzione per filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.|Second Building Name \<\> \^\\s\*\$|
|Escludere subnet comuni|Senza un file di compilazione valido per separare le reti gestite da reti non gestite, le reti home verranno incluse nei report. Queste subnet domestiche esulano dall'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questa guida, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Visualizza solo all'interno|Consente di filtrare un report per scenari gestiti (all'interno) o non gestiti (all'esterno). Il modello CQD gestito è già preconfigurato con questi filtri.|Second Inside Corp = Inside|

## <a name="report-filters"></a>Filtri rapporto

Usare i filtri rapporto CQD per limitare l'ambito delle indagini. Usare i filtri rapporto aggiungendo un filtro al report con rendering nel Editor di query o direttamente nel report. I filtri dei report seguenti vengono usati in tutti i [modelli di Call Quality Dashboard](https://aka.ms/QERtemplates).

|Filter|Descrizione|Esempio di filtro rapporto Call Quality Dashboard|
|---|---|---|
|Month|Inizia con l'anno prima, poi con il mese.|2017-10|
|Alfabetico|Filtra gli eventuali caratteri alfabetici.|[a-z]|
|Numerico|Filtri per qualsiasi carattere numerico.|[0-9]|
|Percentuale|Filtri per una percentuale.|([3-9]\\.)\| ([3-9])\| ([1-9][0-9])|

### <a name="drill-down-filters"></a>Filtri drill-down

I report di Call Quality Dashboard includono diversi filtri drill-down, che sono potenti strumenti per restringere l'ambito delle indagini sulla qualità delle chiamate. Se si seleziona un campo drill-down, il report apre automaticamente la scheda e i filtri appropriati sul valore selezionato. Se questa scheda ha campi drill-down propri e uno è selezionato, vengono applicati entrambi i set di filtri, restringendo progressivamente il set di dati risultante.

![Diagramma che illustra il flusso di report drill-down.](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>Aggiunta e modifica di campi drill-down

Quando si modifica un report, è possibile specificare campi drill-down personalizzati usando la Editor di query.

Per iniziare, fare clic su **...** per il report da modificare, quindi selezionare **Modifica**.

![Screenshot della modifica di un campo drill-down.](media/qerguide-image-addeditdrilldownfields.png)

Selezionare una Quota nell'elenco sul lato sinistro della Editor di query. Quindi fare clic sull'elenco a discesa sotto l'etichetta **Passa** a e selezionare il gruppo di schede ed espandi su cui si vuole eseguire il drill-through della dimensione. Nota: attualmente, la funzionalità drill-down funziona solo passando a schede diverse. Il supporto per il drill-through a uno specifico expander verrà aggiunto in un secondo momento. Infine, fare clic su **Chiudi** per salvare le modifiche apportate alla dimensione, quindi fare clic su **Salva** per salvare e chiudere la Editor di query.

![Screenshot della selezione di una dimensione nella Editor di query.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtri di selezione multipla

Oltre alla funzionalità di drill-down, Call Quality Dashboard supporta anche l'impostazione di filtri con più valori (filtri OR).

Per selezionare più valori di filtro, iniziare aggiungendo un nuovo filtro al report. Fare clic **+** accanto all'etichetta **Filtri** , immettere il nome della dimensione da usare e fare clic su **Aggiungi**.

![Screenshot dell'aggiunta di un filtro con selezione multipla.](media/qerguide-image-addmultiselectfilter.png)

Quindi, fare clic su **Cerca** (icona a forma di lente di ingrandimento accanto al nuovo filtro). Verranno visualizzati un campo di testo e una serie di opzioni, tra cui **Seleziona tutto** e **Inverti**. Immettere un valore e fare clic su **Cerca** accanto al campo in cui eseguire la ricerca. In alternativa, lasciare vuoto il campo di testo e fare clic su **Cerca** per visualizzare fino alle prime 100 opzioni.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:

![Screenshot dell'aggiunta di un filtro query.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtri a livello di dashboard

In alcuni report di Call Quality Dashboard sono stati aggiunti filtri a livello di dashboard, semplificando il filtro in base ai parametri comuni. Questi filtri vengono visualizzati all'esterno delle normali schede dei report e direttamente sotto il filtro Prodotto e vengono applicati a tutti i filtri nel dashboard.

![Screenshot di un filtro del dashboard.](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtri URL

Call Quality Dashboard supporta l'aggiunta di filtri all'URL. In questo modo è facile condividere o aggiungere un segnalibro a una query CQD. È possibile definire i parametri nell'URL, ad esempio Mese di tendenza, ID tenant o lingua. È anche possibile aggiungere filtri a livello di prodotto o dashboard all'URL.
L'esclusione di dati federati dai report di Call Quality Dashboard è utile quando si rimediano edifici gestiti o reti in cui gli endpoint federati potrebbero influire sui report.

Per aggiungere un filtro, aggiungere quanto segue alla fine dell'URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Per aggiungere un filtro a livello di dashboard a un URL, tale filtro deve essere presente in Call Quality Dashboard come filtro a livello di prodotto o dashboard. Aggiungere questi filtri all'URL dopo il mese di tendenza e prima dei parametri dell'URL:

`filter/DATA_MODEL_NAME|VALUE`

Ad esempio, per applicare un valore di filtro prodotto di Microsoft Teams, aggiungeresti quanto segue:

`filter/[AllStreams].[Is%20Teams]|[True]`

L'intero URL avrà un aspetto simile al seguente:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Per applicare filtri URL con valori di selezione multipla, separare ogni valore con un carattere di pipe ( | ). Ad esempio:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Se si specifica un nome o un valore non valido, il filtro URL non verrà applicato.

È possibile usare un filtro URL per filtrare ogni report in base a una dimensione specifica. I filtri URL più comuni vengono usati per filtrare i report per escludere la telemetria dei partecipanti federati o per concentrarsi solo su Teams o Skype for Business Online. L'esclusione di dati federati dai report di Call Quality Dashboard è utile quando si rimediano edifici gestiti o reti in cui gli endpoint federati potrebbero influire sui report.

|Filter|Descrizione|Esempio di filtro query CQD|
|---|---|---|
|Nessun valore vuoto|Alcuni filtri non hanno l'opzione per filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.|Second Building Name \<\> \^\\s\*\$|
|Escludere subnet comuni|Senza un file di compilazione valido per separare le reti gestite da reti non gestite, le reti home verranno incluse nei report. Queste subnet domestiche esulano dall'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questo articolo, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Visualizza solo all'interno|Consente di filtrare un report per scenari gestiti (all'interno) o non gestiti (all'esterno). Il modello CQD gestito è già preconfigurato con questi filtri.|Second Inside Corp = Inside|

#### <a name="how-to-find-your-tenant-id"></a>Come trovare l'ID tenant

L'ID tenant in Call Quality Dashboard corrisponde all'ID directory in Azure. Se non conosci l'ID directory, puoi trovarlo nel portale di Azure:

1. Accedi al portale di Azure Microsoft:<https://portal.azure.com>

2. Selezionare **Azure Active Directory**.

3. In **Gestisci** seleziona **Proprietà**. L'ID tenant si trova nella casella **ID directory** .

È anche possibile trovare l'ID tenant usando PowerShell:

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Confronto tra i dati di Teams e call quality dashboard di Skype for Business

Durante la revisione dei dati, potrebbero verificarsi differenze nei dati tra Teams e Skype for Business. Alcuni motivi:

- Differenze nei meccanismi per garantire prestazioni e affidabilità:
  - Teams ha la riconnessione automatica e il roaming rapido. Skype for Business no.
  - Teams offre una gestione dinamica della larghezza di banda. Skype for Business no.
- Differenze negli [intervalli di indirizzi IP](Office-365-URLs-IP-address-ranges.md) tra Teams e Skype for Business. Gli intervalli IP di Teams sono più recenti, il che potrebbe causare problemi di connettività nel firewall.

## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati di tenant e building](CQD-upload-tenant-building-data.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)
