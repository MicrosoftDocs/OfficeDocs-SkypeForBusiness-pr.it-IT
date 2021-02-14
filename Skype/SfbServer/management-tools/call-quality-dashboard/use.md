---
title: Usare il dashboard qualità delle chiamate per Skype for Business Server
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
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Riepilogo: informazioni su come usare il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: ed1e5563a4677dce33648280590530ca2a9b1b9b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803106"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usare il dashboard qualità delle chiamate per Skype for Business Server

**Riepilogo:** Informazioni su come usare il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.

Call Quality Dashboard (CQD) consente ai professionisti IT di utilizzare dati aggregati per identificare i problemi di creazione di problemi di qualità multimediale confrontando le statistiche per gruppi di utenti per identificare tendenze e modelli. La DQD non è incentrata sulla risoluzione di singoli problemi di chiamata, ma sull'identificazione di problemi e soluzioni applicabili a molti utenti.

## <a name="call-quality-dashboard-user-guide"></a>Manuale dell'utente del dashboard sulla qualità delle chiamate

CQD è un portale Web per la creazione e l'organizzazione rapida di report basati sui dati QoE (Quality of Experience). CQD distribuisce un cubo SSAS per aggregare i dati nel database delle metriche QoE e consente agli amministratori di creare e modificare report o eseguire indagini in tempo reale. Sebbene sia possibile utilizzare Excel per connettersi direttamente al cubo, il portale è ottimizzato per diversi flussi di lavoro che coinvolgono dati QoE. I dati includono:

- Dati dei report memorizzati nella cache per l'accesso rapido
- Collegamenti diretti alle pagine di report per la condivisione e la pubblicazione di informazioni
- Modifica e creazione semplificate dei report e metadati modificabili per le descrizioni dei report.

Inoltre, CQD espone API Web che consentono agli utenti di accedere a livello di codice ai dati del cubo per l'utilizzo in dashboard personalizzati.

### <a name="feature-overview"></a>Panoramica delle funzionalità

Quando si visita il dashboard qualità delle chiamate, viene visualizzata la schermata seguente:

![Usare CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Il "riquadro di riepilogo" è il punto in cui è possibile trovare il contesto per il "Set di report" (a destra).
2. Fare clic su "Modifica" nel riquadro di riepilogoReport per impostare le proprietà del livello, inclusa l'altezza dell'asse Y.
3. Il percorso di navigazione consente di identificare la posizione corrente all'interno della gerarchia dell'insieme di report.
4. I report con sottoreport vengono visualizzati con un collegamento blu. Fare clic sul collegamento per eseguire il drill-down nei report figlio.

Spostare il mouse sui grafici a barre e sulle linee di tendenza per visualizzare valori dettagliati. Il report con lo stato attivo mostra il menu azioni: "Modifica", "Clone", "Elimina" e "Scarica".

### <a name="default-reports"></a>Report predefiniti

Quando si accede per la prima volta al portale Call Quality Dashboard, viene creato automaticamente un set predefinito di report. Questi report vengono talvolta definiti report di sistema. È possibile modificare o eliminare liberamente questi report o estenderli creando nuovi report figlio e di pari livello.

Al livello principale, il report "Tendenza mensile flussi audio" mostra la tendenza mensile per tutti i flussi audio. Spostare il mouse sulle barre di un grafico a barre per visualizzare una visualizzazione più dettagliata dei dati rappresentati dal grafico a barre. Fare clic sul titolo del report Tendenze mensili flussi audio per passare al report "Flussi audio gestiti e non gestiti", in cui i report sono suddivisi tra chiamate gestite e non gestite. Le chiamate gestite sono chiamate effettuate dall'interno del firewall aziendale tramite connessioni cablate. Le chiamate non gestite includono le chiamate effettuate dall'esterno del firewall aziendale e tutte le chiamate effettuate tramite Wi-Fi.

L'altro report di primo livello è denominato "Istogramma di valutazione qualità delle chiamate segnalato dall'utente". Le valutazioni di qualità delle chiamate sono i numeri assegnati dagli utenti di Skype for Business al termine di una chiamata per indicare la qualità della chiamata. I numeri di valutazione sono da 1 a 5, 1 è il peggiore e 5 è il migliore. L'istogramma mostra il numero di chiamate audio con la valutazione indicata in un mese.

Fare clic sul titolo di uno dei report per spostarsi nei report con più filtri sui dati. Nei report di sistema, ogni report figlio visualizza un sottoinsieme dei dati disponibili nel relativo report padre. Il modello di risoluzione dei problemi è semplice: analizzare a quale sottoreport sono limitati i dati o la tendenza che suggerisce un problema e restringere gradualmente lo spazio del problema. La possibilità di creare sottoreport consente di analizzare le proprie ipotesi sulla causa di tendenze dei dati specifiche.

### <a name="create-and-edit-reports"></a>Creare e modificare rapporti

Fare clic su "Modifica" nel menu azioni di un report per visualizzare l'Editor report. Ogni report è supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla relativa query. L'Editor report consente di modificare queste query e le opzioni di visualizzazione del report. Quando si apre l'editor di report, viene visualizzato:

![Usare CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Le dimensioni, le misure e i filtri vengono scelti nel riquadro sinistro. Posizionare il puntatore del mouse su uno dei valori esistenti per visualizzare un pulsante "x" che consente di rimuovere il valore. Fare clic sul pulsante "più" accanto a un'intestazione per aprire la finestra di dialogo in cui è possibile aggiungere una nuova dimensione, misura o filtro.
2. Le opzioni per la personalizzazione dei grafici vengono visualizzate nella parte superiore.
3. Nell'Editor report è disponibile un'anteprima del report.
4. È possibile creare una descrizione dettagliata del report con la casella di modifica nella parte inferiore.

### <a name="sparklines-in-tables"></a>Grafici sparkline nelle tabelle

Quando StartDate.Month viene aggiunto come dimensione e il rendering dei dati viene eseguito come tendenza in forma di tabella, i grafici a barre e i grafici sparkline possono essere visualizzati all'interno delle celle della tabella. Spostare il puntatore del mouse sul grafico a barre e sui grafici sparkline per visualizzare i valori dei singoli mesi.

![Usare CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Per visualizzare i grafici a barre e i grafici sparkline, è necessario selezionare la casella di controllo "Mostra grafici sparkline" nella parte superiore dell'Editor report. In questo modo viene selezionata l'opzione Tendenza e il mese viene spostato verso il basso per essere l'ultima dimensione, che può essere eseguita anche facendo clic su Mese e utilizzando le frecce su e giù per spostare StartDate.Month verso l'alto o verso il basso.

### <a name="settings"></a>Impostazioni

Il menu delle impostazioni contiene collegamenti a pagine utili come le pagine Integrità del sistema e Informazioni su e si trova nell'angolo in alto a destra del dashboard.

![Usare CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

La visualizzazione di descrizioni e indicatori di data e ora è un'opzione che può essere impostata solo per i singoli utenti e queste impostazioni influiscono solo sulla versione del dashboard e non modificano il set di report o ciò che viene visualizzato dagli altri utenti. Cancellando la cache, tutte le query ricaricano i dati dal cubo, mentre il ripristino delle impostazioni predefinite elimina tutti i report creati dall'utente o modificati e ricrea il set di report di sistema, ovvero ciò che un utente visualizza quando accede per la prima volta.

Il collegamento Dashboard utenti mostra una pagina in cui gli utenti possono visualizzare altri utenti di CQD e sfogliare i propri report. Per condividere un set di report, copia il collegamento nella barra dell'URL e condividilo con un altro utente CQD. Questo collegamento è lo stesso collegamento che verrebbe visualizzato dagli altri utenti nella pagina Collegamento dashboard utenti sotto il nome utente dell'utente.

### <a name="supplying-subnet-information"></a>Fornitura di informazioni sulla subnet

Ulteriori informazioni possono essere rivelate se nel database Archive vengono immesse informazioni specifiche del sito per fornire informazioni di mapping tra subnet e edificio (ad esempio, la qualità delle chiamate cablate/wireless in base alla creazione).

Per creare questi report, completare almeno le tabelle seguenti:

- CqdBuilding
- CqdNetwork

È possibile fornire ulteriori informazioni nelle tabelle CqdBuildingType e CqdBuildingOwnershipType per consentire ulteriori filtri ed eseguire il drill-down.

I dati utilizzati per queste tabelle sono definiti come segue:

**CqdBuilding**

|Colonna|Tipo di dati|Consentire valori Null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |No |Chiave primaria per la tabella CqdBuilding. |
|BuildingName |varchar(80) |No |Nome dell'edificio. |
|BuildingShortName |varchar(10) |No |Versione più breve del nome dell'edificio. |
|OwnershipTypeId |int |No |Chiave esterna che corrisponde a una delle voci della tabella CqdBuildingOwners. |
|BuildingTypeId |int |No |Chiave esterna che corrisponde a una delle voci della tabella CqdBuildingType. |
|Latitudine |float |Sì |Latitudine dell'edificio. |
|Longitudine |float |Sì |Longitudine dell'edificio. |
|CityName |varchar(30) |Sì |Nome della città in cui si trova l'edificio. |
|ZipCode |varchar(25) |Sì |CAP in cui si trova l'edificio. |
|CountryShortCode |varchar(2) |Sì |Codici ISO 3166-1 alpha-2 per il paese in cui si trova l'edificio. |
|StateProvinceCode |varchar(3) |Sì |Abbreviazione di tre lettere per la provincia in cui si trova l'edificio. |
|InsideCorp |bit |Sì |Bit indica se l'edificio fa parte della rete aziendale. |
|BuildingOfficeType |nvarchar(150) |Sì |Descrizione del tipo di ufficio dell'edificio. |
|Area geografica |varchar(25) |Sì |Area geografica in cui si trova l'edificio. |
|||||

**CqdNetwork**

|Colonna|Tipo di dati|Consentire valori Null?|Dettagli|
|:-----|:-----|:-----|:-----|
|Rete |varchar(25) |No |Indirizzo subnet. |
|NetworkRange |tinyint |Sì |Subnet mask. |
|NetworkNameID |int |Sì |Facoltativamente, esegue il mapping a una riga della tabella CqdNetworkName. |
|BuildingKey |int |Sì |Chiave esterna che corrisponde a una delle voci della tabella CqdBuilding. |
|UpdatedDate |datetime |No |Data/ora dell'ultimo aggiornamento della voce. |
||||||

Per impostazione predefinita, la tabella successiva contiene una voce (0, "Sconosciuto").

**CqdBuildingType**

|Colonna|Tipo di dati|Consentire valori Null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |No |Chiave primaria per la tabella CqdBuildingType. |
|BuildingTypeDesc |char(18) |No |Descrizione del tipo di edificio. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0, "Sconosciuto", 0, Null).

**CqdBuildingOwnershipType**

|Colonna|Tipo di dati|Consentire valori Null?|Dettagli|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |No |Chiave primaria per la tabella CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |No |Descrizione del tipo di proprietà. |
|LeaseInd |tinyint |Sì |Indice che fa riferimento a un'altra riga della tabella CqdBuildingOwnershipType, utilizzata per identificare gli edifici in leasing. |
|Proprietario |varchar(50) |Sì |Proprietario dell'edificio. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0, "Sconosciuto", 0, Null).

**CqdBssid**

|Colonna|Tipo di dati|Consentire valori Null?|Dettagli|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |No |Chiave primaria per la tabella CqdBssid. È il BSSID del punto di accesso WiFi. |
|ess |nvarchar(50) |Sì |Informazioni sul controller del punto di accesso Wifi. |
|phy |nvarchar(50) |Sì |Informazioni sulla fisica. |
|ap |nvarchar(50) |Sì |Nome punto di accesso Wifi. |
|Building |nvarchar(500) |Sì |Nome dell'edificio in cui si trova il punto di accesso WiFi. |
||||

## <a name="cqd-streams"></a>Flussi CQD

Un flusso CQD è considerato buono, scadente o non classificato. CQM 1.5 ora usa la definizione CQD seguente:

- Un flusso scadente è una qualsiasi combinazione delle metriche delle chiamate di qualità scarsa oltre la soglia.
- Quando un flusso di una chiamata è scadente, entrambi i flussi della chiamata vengono contrassegnati di qualità scarsa. Nelle conferenze, ogni partecipante viene conteggiato come una chiamata univoca e viene segnalato indipendentemente da tutti gli altri.
- I flussi non classificati sono flussi senza metriche di qualità, ovvero transazioni sintetiche o chiamate brevi.
- Flussi validi = client non mobili
- Impossibile modificare il classificatore

**Definizione/classificatore di chiamata scadente**

|Metrica|Soglia|
|:-----|:-----|
|DegradationAvg |Maggiore di 1,0 (-1 MOS di rete) |
|RoundTrip |Maggiore di 500 |
|PacketLossRate |Maggiore di 0,1 (10%) |
|JitterInterArrival |Maggiore di 30 |
|RatioConcealedSamplesAvg |Maggiore di 0,07 |
|||

Definizione JPDR = Definizione di chiamata scadente meno RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Dove si trova Chiamante/Chiamato?

In CQD non vengono utilizzati i campi Chiamante/Chiamato, ma "Primo" e "Secondo", perché sono presenti passaggi tra il chiamante e il chiamante.

 **First** Sarà sempre l'endpoint del server (ad esempio, AV MCU o Mediation Server) se un server è coinvolto nel flusso.

 **Second** Sarà sempre l'endpoint client, a meno che non si tratta di Server-Server flusso.

**Esempio di classificazione First e Second**

|Endpoint 1 UAType|Endpoint 2 UUAType|First|Second|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for Business) |Endpoint 1 |Endpoint 2 |
|2 (AVMCU) |1 (mMediationServer) |Endpoint 2 |Endpoint 1 |
|4 (Skype for Business) |4 (Skype for Business) |Il chiamante in MediaLine |Il chiamato in MMediaLine |
|||||

Se entrambi gli endpoint sono dello stesso tipo, CQD rende la voce Chiamante first e la Callee Second. Per altre informazioni sui nomi degli endpoint, vedi [questo blog.](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)

## <a name="accounting-for-vpn"></a>Accounting for VPN

Se la soluzione VPN è nota per impostare in modo accurato il flag VPN, sei tutto impostato. In caso contrario, utilizzare uno dei metodi seguenti:

- Crea un tipo di rete denominato VPN (preferito), quindi associa subnet VPN a questo nuovo NetworkType VPN.
- Crea un edificio denominato VPN, quindi associa subnet VPN a questo edificio.

## <a name="query-fundamentals"></a>Nozioni fondamentali sulla query

Una query ben formata contiene tutti e tre i parametri seguenti:

- Misurazione
- Dimensione
- Filtro

Un esempio di query ben formata è "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."

## <a name="what-does-union-do"></a>Quali sono le funzioni di UNION?

L'unione consente di filtrare le condizioni con l'operatore AND. Esistono scenari in cui è possibile combinare più condizioni di filtro per ottenere un risultato simile a un'operazione OR.

Esempio: per ottenere tutti i flussi da un edificio, UNION offre una visualizzazione distinta del set di dati unito. Per utilizzare union, inserire il testo comune nel campo UNION nelle due condizioni di filtro che si desidera utilizzare come UNION.

## <a name="default-report-breakdown"></a>Scomposizione report predefinita

Se wireless viene gestito internamente, puoi ricreare i report wireless nel bucket gestito.

![Scomposizione report CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processi operativi

Esaminare e correggere prima i flussi gestiti. La qualità in quest'area deve essere al 100% all'interno del controllo e quindi più semplice da correggere.

### <a name="managed-streams"></a>Flussi gestiti

Esaminare e correggere i flussi gestiti nell'ordine seguente:

1. Server-Server
2. Server-Wired-Inside
3. Wired-Wired-Inside

### <a name="unmanaged-streams"></a>Flussi non gestiti

Esaminare e correggere i flussi non gestiti nell'ordine seguente:

1. Server-Wifi-Inside
2. Server cablato all'esterno
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Wired-Outside-Relay
6. Altro non gestito
