---
title: Usare il dashboard qualità chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Riepilogo: informazioni su come usare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816665"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usare il dashboard qualità chiamata per Skype for Business Server

**Riepilogo:** Informazioni su come usare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.

Call Quality Dashboard (Call Quality Dashboard) consente ai professionisti IT di usare i dati aggregati per identificare i problemi di creazione di problemi di qualità multimediale, confrontando le statistiche per i gruppi di utenti per identificare tendenze e modelli. Call Quality Dashboard non è focalizzato sulla risoluzione dei singoli problemi di chiamata, ma sull'individuazione di problemi e soluzioni applicabili a molti utenti.

## <a name="call-quality-dashboard-user-guide"></a>Guida per l'utente del dashboard qualità chiamata

Call Quality dashboard è un portale Web per creare e organizzare rapidamente report basati sui dati di qualità dell'esperienza (QoE). Call Quality dashboard distribuisce un cubo SSAS per aggregare i dati nel database di metriche QoE e consente agli amministratori di creare e modificare report o eseguire indagini in tempo reale. Anche se è possibile usare Excel per connettersi direttamente al cubo, il portale è ottimizzato per diversi flussi di lavoro che coinvolgono i dati QoE. I dati includono:

- Dati del report memorizzati nella cache per l'accesso rapido
- Collegamenti profondi alle pagine del report per la condivisione e la pubblicazione delle informazioni
- Semplificare la modifica e la creazione di report e i metadati modificabili per le descrizioni dei report.

Inoltre, Call Quality dashboard espone le API Web che offrono agli utenti l'accesso a livello di codice ai dati del cubo per l'uso nei dashboard personalizzati.

### <a name="feature-overview"></a>Panoramica delle funzionalità

Quando si visita il dashboard qualità chiamata, viene visualizzata la schermata seguente:

![Usare Call Quality dashboard](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Il "riquadro di riepilogo" è il punto in cui è possibile trovare il contesto per il "set di report" (a destra).
2. Fare clic su "modifica" nel PaneReport di riepilogo per impostare le proprietà del livello (inclusa l'altezza dell'asse Y).
3. La barra di spostamento consente di identificare la posizione corrente all'interno della gerarchia del set di report.
4. I report con i sottoreport vengono visualizzati con un collegamento blu. Fare clic sul collegamento per eseguire il drill-down nei report figlio.

Posizionare il puntatore del mouse sui grafici a barre e sulle linee di tendenza per visualizzare i valori dettagliati. Il report con lo stato attiva Mostra il menu azione: "modifica", "clone", "Elimina" e "Scarica".

### <a name="default-reports"></a>Report predefiniti

Quando si accede per la prima volta al portale di Call Quality dashboard, viene creato automaticamente un set di report predefinito. Questi report vengono talvolta definiti report di sistema. È possibile modificare o eliminare liberamente questi report oppure estenderli creando nuovi report figlio e di pari livello.

Al primo livello, il report "audio streams Monthly trend" Mostra la tendenza mensile per tutti i flussi audio. Posizionare il puntatore del mouse sulle barre in un grafico a barre per visualizzare una visualizzazione più dettagliata dei dati rappresentati dal grafico a barre. Fare clic sul titolo del report flussi audio mensili per passare al report "flussi audio gestiti e non Managed", in cui i report vengono divisi tra chiamate gestite e non gestite. Le chiamate gestite sono chiamate effettuate dall'interno del firewall aziendale tramite connessioni cablate. Le chiamate non gestite includono le chiamate effettuate all'esterno del firewall aziendale e tutte le chiamate effettuate tramite Wi-Fi.

L'altro report di primo livello è denominato "istogramma di valutazione della qualità delle chiamate utente". Le valutazioni della qualità delle chiamate sono i numeri forniti dagli utenti di Skype for business alla fine di una chiamata per indicare la qualità della chiamata. I numeri di classificazione variano da 1 a 5, 1 è il peggiore e 5 è il migliore. L'istogramma mostra il numero di chiamate audio che avevano la classificazione indicata in un mese.

Fare clic sul titolo di uno dei report per spostarsi nei report con altri filtri sui dati. Nei report di sistema ogni report figlio Visualizza un sottoinsieme dei dati disponibili nel report padre. Il modello di risoluzione dei problemi è semplice: esaminare il sottoreport a cui si limitano i dati o le tendenze suggerendo un problema e limitando gradualmente lo spazio del problema. La possibilità di creare sottoreport consente di analizzare le proprie ipotesi sulla causa di specifiche tendenze dei dati.

### <a name="create-and-edit-reports"></a>Creare e modificare report

Fare clic su "modifica" nel menu azione di un report per visualizzare l'editor report. Ogni report viene supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor report consente di modificare queste query e le opzioni di visualizzazione del report. Quando si apre l'editor report, viene visualizzato:

![Usare Call Quality dashboard](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Le dimensioni, le misure e i filtri vengono scelti nel riquadro sinistro. Posizionare il puntatore su uno dei valori esistenti per visualizzare un pulsante "x" che consente di rimuovere il valore. Fare clic sul pulsante "più" accanto a un titolo per aprire la finestra di dialogo in cui è possibile aggiungere una nuova dimensione, misura o filtro.
2. Le opzioni per la personalizzazione del grafico sono visualizzate nella parte superiore.
3. Un'anteprima del report è disponibile nell'editor report.
4. Una descrizione dettagliata del report può essere creata con la casella Modifica nella parte inferiore.

### <a name="sparklines-in-tables"></a>Grafici sparkline nelle tabelle

Quando StartDate. Month viene aggiunto come dimensione e viene eseguito il rendering dei dati come tendenza in una maschera di tabella, i grafici a barre e i grafici sparkline possono essere visualizzati all'interno delle celle della tabella. Posizionare il puntatore del mouse sul grafico a barre e sui grafici sparkline per visualizzare i valori per i singoli mesi.

![Usare Call Quality dashboard](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Per visualizzare i grafici a barre e i grafici sparkline, la casella di controllo "Mostra grafici sparkline" nella parte superiore dell'editor report deve essere selezionata. In questo modo viene selezionata l'opzione tendenza e si sposta il mese in giù per essere l'ultima dimensione, che può essere eseguita anche facendo clic su mese e usando le frecce su e giù per spostare StartDate. mese in alto o in basso.

### <a name="settings"></a>Impostazioni

Il menu impostazioni contiene collegamenti a pagine utili come l'integrità del sistema e informazioni sulle pagine e si trova nell'angolo in alto a destra del dashboard.

![Usare Call Quality dashboard](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

La possibilità di visualizzare le descrizioni e i timestamp dipende dai singoli utenti e queste impostazioni influenzano solo la versione individuale del dashboard e non modificano il set di report o gli altri utenti. La cancellazione della cache causa la ricarica dei dati da parte di tutte le query dal cubo, mentre il ripristino delle impostazioni predefinite elimina tutti i report creati dall'utente o modificati e ricrea il set di report di sistema, quello che un utente vedrebbe quando accede per la prima volta.

Il collegamento dashboard utenti Mostra una pagina in cui gli utenti possono visualizzare altri utenti di Call Quality dashboard e sfogliare i loro report. Per condividere un set di report, copiare il collegamento nella barra dell'URL e condividerlo con un altro utente di Call Quality dashboard. Questo collegamento è lo stesso collegamento che altri utenti vedranno nella pagina del collegamento dashboard utenti sotto il nome utente.

### <a name="supplying-subnet-information"></a>Fornitura di informazioni sulla subnet

Altre informazioni possono essere rilevate se le informazioni specifiche del sito vengono immesse nel database di archiviazione per ottenere informazioni di mapping della subnet per la compilazione, ad esempio la qualità della chiamata cablata/wireless tramite la creazione.

Completare almeno le tabelle seguenti per creare questi report:

- CqdBuilding
- CqdNetwork

Altre informazioni possono essere fornite nelle tabelle CqdBuildingType e CqdBuildingOwnershipType per consentire ulteriori operazioni di filtro e drill-down.

I dati usati per queste tabelle sono definiti come segue:

**CqdBuilding**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |No |Chiave primaria per la tabella CqdBuilding. |
|Buildingname |varchar (80) |No |Nome dell'edificio. |
|BuildingShortName |varchar (10) |No |Versione più breve del nome dell'edificio. |
|OwnershipTypeId |int |No |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuildingOwners. |
|BuildingTypeId |int |No |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuildingType. |
|Latitudine |galleggiante |Sì |Latitudine dell'edificio. |
|Longitudine |galleggiante |Sì |Longitudine dell'edificio. |
|CityName |varchar (30) |Sì |Nome della città in cui si trova l'edificio. |
|ZipCode |varchar (25) |Sì |Codice postale in cui si trova l'edificio. |
|CountryShortCode |varchar (2) |Sì |Codici ISO 3166-1 Alpha-2 per il paese in cui si trova l'edificio. |
|StateProvinceCode |varchar (3) |Sì |Abbreviazione di tre lettere per lo stato o la provincia in cui si trova l'edificio. |
|InsideCorp |po' |Sì |Bit indica se l'edificio fa parte della rete aziendale. |
|BuildingOfficeType |nvarchar (150) |Sì |Descrizione del tipo di Office Building. |
|Area |varchar (25) |Sì |Area geografica in cui si trova l'edificio. |
|||||

**CqdNetwork**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|Rete |varchar (25) |No |Indirizzo subnet. |
|NetworkRange |tinyint |Sì |Subnet mask. |
|NetworkNameID |int |Sì |Facoltativamente, esegue il mapping a una riga nella tabella CqdNetworkName. |
|BuildingKey |int |Sì |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuilding. |
|UpdatedDate |DateTime |No |DateTime per quando la voce è stata aggiornata l'ultima volta. |
||||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ').

**CqdBuildingType**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |No |Chiave primaria per la tabella CqdBuildingType. |
|BuildingTypeDesc |carattere (18) |No |Descrizione del tipo di edificio. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ', 0, null).

**CqdBuildingOwnershipType**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |No |Chiave primaria per la tabella CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar (25) |No |Descrizione del tipo di proprietà. |
|LeaseInd |tinyint |Sì |Indice che fa riferimento a un'altra riga nella tabella CqdBuildingOwnershipType, usata per identificare gli edifici affittati. |
|Proprietario |varchar (50) |Sì |Proprietario dell'edificio. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ', 0, null).

**CqdBssid**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BSS |nvarchar (50) |No |Chiave primaria per la tabella CqdBssid. È l'BSSID del punto di accesso WiFi. |
|ESS |nvarchar (50) |Sì |Informazioni sul controller di Access Point WiFi. |
|PHY |nvarchar (50) |Sì |Informazioni PHY. |
|AP |nvarchar (50) |Sì |Nome punto di accesso WiFi. |
|Predefiniti |nvarchar (500) |Sì |Nome dell'edificio in cui si trova il punto di accesso WiFi. |
||||

## <a name="cqd-streams"></a>Flussi Call Quality dashboard

Un flusso Call Quality dashboard è considerato valido, scadente o non classificato. CQM 1,5 ora usa la seguente definizione di Call Quality Dashboard:

- Un flusso scadente è una combinazione delle metriche della chiamata scadente oltre la soglia.
- Quando un flusso in una chiamata è scadente, entrambi i flussi della chiamata vengono contrassegnati come poveri. Nelle conferenze ogni partecipante viene considerato come una chiamata univoca e viene segnalato indipendentemente da tutti gli altri utenti.
- I flussi non classificati sono flussi senza metriche di qualità, ovvero transazioni sintetiche o chiamate brevi.
- Flussi validi = client non mobili
- Non è possibile modificare il classificatore

**Classificazione/classificatore delle chiamate non di qualità**

|Metrica|Soglia|
|:-----|:-----|
|DegradationAvg |Maggiore di 1,0 (MOS di rete-1) |
|RoundTrip |Maggiore di 500 |
|PacketLossRate |Maggiore di 0,1 (10%) |
|JitterInterArrival |Maggiore di 30 |
|RatioConcealedSamplesAvg |Maggiore di 0,07 |
|||

Definizione di JPDR = definizione chiamata insufficiente meno RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Dove si trova il chiamante/chiamato?

Call Quality Dashboard non usa campi chiamante/chiamato, ma usa "First" e "Second" perché sono presenti passaggi intermedi tra il chiamante e il chiamato.

 **Primo** Sarà sempre l'endpoint del server, ad esempio MCU AV o Mediation Server, se un server è coinvolto nello stream.

 **Secondo** Sarà sempre l'endpoint client, a meno che non si tratta di un flusso Server-Server.

**Esempio di classificazione prima e seconda**

|Endpoint 1 UAType|Endpoint 2 UUAType|Primo|Second|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for business) |Endpoint 1 |Endpoint 2 |
|2 (AVMCU) |1 (mMediationServer) |Endpoint 2 |Endpoint 1 |
|4 (Skype for business) |4 (Skype for business) |Il chiamante in MediaLine |Il chiamato in MMediaLine |
|||||

Se entrambi gli endpoint sono dello stesso tipo, Call Quality dashboard effettua prima di tutto la voce del chiamante e il secondo chiamato. Per altre informazioni sui nomi degli endpoint, vedere [questo Blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>Contabilità per VPN

Se la soluzione VPN è nota per impostare in modo accurato il contrassegno VPN, è tutto impostato. In caso contrario, usa uno dei metodi seguenti:

- Creare un tipo di rete denominato VPN (preferito), quindi associare subnet VPN a questo nuovo NetworkType VPN.
- Creare un edificio denominato VPN, quindi associare subnet VPN a questo edificio.

## <a name="query-fundamentals"></a>Elementi fondamentali della query

Una query ben formata contiene tutti e tre i parametri seguenti:

- Misura
- Dimensione
- Filter

Un esempio di query ben formata sarebbe "Mostra i flussi poveri [misura] per subnet [dimensione] per l'edificio 6 [filtro]."

## <a name="what-does-union-do"></a>Cosa fa l'Unione?

L'Unione consente di filtrare le condizioni con l'operatore AND. Esistono scenari in cui è possibile combinare più condizioni di filtro insieme per ottenere un risultato simile a un'operazione OR.

Esempio: per ottenere tutti i flussi da un edificio, UNION offre una visualizzazione distinta del set di dati Unito. Per usare l'Unione, inserire testo comune nel campo unione sulle due condizioni di filtro che si desidera includere nell'Unione.

## <a name="default-report-breakdown"></a>Ripartizione del report predefinita

Se la funzionalità wireless è gestita internamente, è possibile ricreare i report wireless nel contenitore gestito.

![Ripartizione report di Call Quality dashboard](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processi operativi

Esaminare e correggere prima di tutto i flussi gestiti. La qualità in quest'area dovrebbe essere di 100% all'interno del controllo e quindi più semplice da correggere.

### <a name="managed-streams"></a>Flussi gestiti

Esaminare e correggere i flussi gestiti nell'ordine seguente:

1. Server-Server
2. Server-cablato-interno
3. Cablato-cablato-interno

### <a name="unmanaged-streams"></a>Flussi non gestiti

Esaminare e correggere i flussi non gestiti nell'ordine seguente:

1. Server-WiFi-interno
2. Server-cablato-esterno
3. Server-WiFi-esterno
4. Cablato-esterno-diretto
5. Inoltro via cavo-esterno
6. Altri non gestiti
