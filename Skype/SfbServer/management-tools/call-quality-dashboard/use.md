---
title: Utilizzo del dashboard qualità chiamata per Skype for Business Server
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
description: 'Riepilogo: informazioni su come utilizzare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: ed1e5563a4677dce33648280590530ca2a9b1b9b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803106"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Utilizzo del dashboard qualità chiamata per Skype for Business Server

**Riepilogo:** Informazioni su come utilizzare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.

Call Quality Dashboard (CQD) consente ai professionisti IT di utilizzare i dati aggregati per identificare i problemi relativi alla creazione di problemi di qualità multimediale confrontando le statistiche per i gruppi di utenti per identificare le tendenze e i modelli. CQD non è concentrato sulla risoluzione dei singoli problemi di chiamata, ma sull'identificazione di problemi e soluzioni che si applicano a molti utenti.

## <a name="call-quality-dashboard-user-guide"></a>Guida per l'utente del dashboard qualità chiamata

CQD è un portale Web per la creazione e l'organizzazione rapida di report in base ai dati QoE (Quality of Experience). CQD distribuisce un cubo di SSAS per aggregare i dati nel database di metriche QoE e consente agli amministratori di creare e modificare i report o di eseguire indagini in tempo reale. Anche se è possibile utilizzare Excel per connettersi direttamente al cubo, il portale è ottimizzato per diversi flussi di lavoro che coinvolgono dati QoE. I dati includono:

- Dati del report memorizzati nella cache per un accesso rapido
- Collegamenti profondi alle pagine dei report per la condivisione e la pubblicazione delle informazioni
- Semplificazione della modifica e della creazione di report e metadati modificabili per le descrizioni dei report.

Inoltre, in CQD sono esposte API Web che forniscono agli utenti l'accesso programmatico ai dati del cubo da utilizzare nei dashboard personalizzati.

### <a name="feature-overview"></a>Panoramica delle funzionalità

Quando si visita il dashboard qualità chiamata, viene visualizzata la schermata seguente:

![Utilizzo di CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Il riquadro riepilogativo è il luogo in cui è possibile trovare il contesto per il "set di report" (a destra).
2. Fare clic su "modifica" nell'PaneReport di riepilogo per impostare le proprietà del livello (inclusa l'altezza dell'asse Y).
3. La barra di spostamento consente di identificare la posizione corrente all'interno della gerarchia dei set di report.
4. I rapporti con i sottoreport vengono visualizzati con un collegamento blu. Fare clic sul collegamento per eseguire il drill-down nei report figlio.

Spostare il puntatore del mouse sui grafici a barre e le linee di tendenza per visualizzare i valori dettagliati. Il report con lo stato attivo Visualizza il menu azione: "modifica", "Clona", "Elimina" e "Scarica".

### <a name="default-reports"></a>Rapporti predefiniti

Quando si accede per la prima volta al portale dashboard qualità chiamata, viene creato automaticamente un set di report predefinito. Questi rapporti sono a volte indicati come report di sistema. È possibile modificare o eliminare liberamente tali rapporti o estenderli creando nuovi rapporti di pari livello e figlio.

Al livello superiore, il rapporto "flussi audio mensili" indica la tendenza mensile per tutti i flussi audio. Spostare il puntatore del mouse sulle barre in un grafico a barre per visualizzare una visualizzazione più dettagliata dei dati rappresentati dal grafico a barre. Fare clic sul titolo del rapporto tendenze mensili flussi audio per passare al report "flussi audio gestiti con non gestito", in cui i rapporti vengono divisi tra le chiamate gestite e non gestite. Le chiamate gestite sono chiamate effettuate dall'interno del firewall aziendale tramite connessioni cablate. Le chiamate non gestite includono le chiamate effettuate all'esterno del firewall aziendale e tutte le chiamate effettuate tramite Wi-Fi.

L'altro rapporto di primo livello è denominato "istogramma della qualità delle chiamate segnalate dall'utente". Le valutazioni della qualità delle chiamate sono i numeri forniti dagli utenti di Skype for business al termine di una chiamata per indicare la qualità della chiamata. I numeri di classificazione variano da 1 a 5, 1 è il peggiore e 5 è il migliore. L'istogramma Visualizza il numero di chiamate audio che hanno la classificazione indicata in un mese.

Fare clic sul titolo di uno dei rapporti per passare ai report con altri filtri sui dati. Nei report di sistema, ogni report figlio Visualizza un sottoinsieme dei dati disponibili nel relativo rapporto padre. Il modello per la risoluzione dei problemi è semplice: è possibile esaminare il sottoreport dei dati o della tendenza che suggerisce un problema e limitarlo gradualmente allo spazio del problema. La possibilità di creare sottoreport consente di analizzare le proprie congetture sulla causa di specifiche tendenze dei dati.

### <a name="create-and-edit-reports"></a>Creazione e modifica di report

Fare clic su "modifica" nel menu azione di un report per visualizzare l'editor di report. Ogni report è supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di report consente di modificare queste query e le opzioni di visualizzazione del report. Quando si apre l'editor di report, è possibile visualizzare le informazioni seguenti:

![Utilizzo di CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Nel riquadro sinistro sono state selezionate dimensioni, misure e filtri. Posizionare il puntatore del mouse su uno dei valori esistenti per visualizzare un pulsante "x" che consente di rimuovere il valore. Fare clic sul pulsante "più" accanto a un'intestazione per aprire la finestra di dialogo in cui è possibile aggiungere una nuova dimensione, una misura o un filtro.
2. Le opzioni per la personalizzazione del grafico vengono visualizzate nella parte superiore.
3. Un'anteprima del report è disponibile nell'editor di report.
4. È possibile creare una descrizione dettagliata del report con la casella di modifica in basso.

### <a name="sparklines-in-tables"></a>Grafici sparkline nelle tabelle

Quando StartDate. Month viene aggiunto come dimensione e viene eseguito il rendering dei dati come tendenza nella maschera di tabella, i grafici a barre e i grafici sparkline possono essere visualizzati all'interno delle celle della tabella. Spostare il puntatore del mouse sul grafico a barre e sui grafici sparkline per visualizzare i valori per i singoli mesi.

![Utilizzo di CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Per visualizzare i grafici a barre e i grafici sparkline, è necessario controllare la casella di controllo "Mostra grafici sparkline" nella parte superiore dell'editor di report. Questo seleziona l'opzione tendenza e sposta il mese verso l'alto per essere l'ultima dimensione, che può essere eseguita anche facendo clic sul mese e utilizzando le frecce su e giù per spostare StartDate. month verso il basso.

### <a name="settings"></a>Impostazioni

Il menu impostazioni contiene collegamenti a pagine utili come l'integrità del sistema e le pagine e si trova nell'angolo in alto a destra del dashboard.

![Utilizzo di CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

La possibilità di visualizzare le descrizioni e gli indicatori di data e ora spetta a singoli utenti e queste impostazioni influiscono solo sulla versione individuale del dashboard e non modificano il set di report o gli altri utenti visualizzati. Deselezionando la cache, tutte le query devono ricaricare i dati dal cubo, mentre il ripristino predefinito Elimina tutti i report creati dall'utente o modificati e ricrea il set di report di sistema, ovvero cosa verrebbe visualizzato dall'utente per la prima volta.

Il collegamento dashboard utenti Mostra una pagina in cui gli utenti possono visualizzare altri utenti di CQD e visualizzarne i report. Per condividere un set di report, copiare il collegamento nella barra degli URL e condividerlo con un altro utente di CQD. Questo collegamento è lo stesso collegamento che vedranno gli altri utenti nella pagina del collegamento del dashboard degli utenti sotto il nome utente.

### <a name="supplying-subnet-information"></a>Fornire informazioni sulla subnet

Ulteriori informazioni possono essere rilevate se le informazioni specifiche del sito vengono immesse nel database di archiviazione per fornire informazioni di mapping da subnet a compilazione (ad esempio, la qualità delle chiamate cablate/wireless tramite la compilazione).

Per creare i report, completare almeno le tabelle seguenti:

- CqdBuilding
- CqdNetwork

Altre informazioni possono essere fornite nelle tabelle CqdBuildingType e CqdBuildingOwnershipType per consentire ulteriori operazioni di filtro e drill-down.

I dati utilizzati per queste tabelle sono definiti come segue:

**CqdBuilding**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |No |Chiave primaria per la tabella CqdBuilding. |
|Buildingname |varchar (80) |No |Nome dell'edificio. |
|BuildingShortName |varchar (10) |No |Versione più corta del nome dell'edificio. |
|OwnershipTypeId |int |No |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuildingOwners. |
|BuildingTypeId |int |No |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuildingType. |
|Latitudine |galleggiante |Sì |Latitudine dell'edificio. |
|Longitudine |galleggiante |Sì |Longitudine dell'edificio. |
|CityName |varchar (30) |Sì |Nome della città in cui si trova l'edificio. |
|Cap |varchar (25) |Sì |Codice postale in cui si trova l'edificio. |
|CountryShortCode |varchar (2) |Sì |Codici ISO 3166-1 Alpha-2 per il paese in cui si trova l'edificio. |
|StateProvinceCode |varchar (3) |Sì |Abbreviazione di tre lettere per lo stato o la provincia in cui si trova l'edificio. |
|InsideCorp |po' |Sì |Bit indica se l'edificio fa parte della rete aziendale. |
|BuildingOfficeType |nvarchar (150) |Sì |Descrizione del tipo di ufficio di costruzione. |
|Area geografica |varchar (25) |Sì |Area geografica in cui si trova l'edificio. |
|||||

**CqdNetwork**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|Rete |varchar (25) |No |Indirizzo subnet. |
|NetworkRange |tinyint |Sì |Subnet mask. |
|NetworkNameID |int |Sì |Facoltativamente, è possibile eseguire il mapping a una riga nella tabella CqdNetworkName. |
|BuildingKey |int |Sì |Chiave esterna, corrisponde a una delle voci nella tabella CqdBuilding. |
|UpdatedDate |datetime |No |Data/ora per l'ultimo aggiornamento della voce. |
||||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' Unknown ').

**CqdBuildingType**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |No |Chiave primaria per la tabella CqdBuildingType. |
|BuildingTypeDesc |char (18) |No |Descrizione del tipo di compilazione. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' Unknown ', 0, null).

**CqdBuildingOwnershipType**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |No |Chiave primaria per la tabella CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar (25) |No |Descrizione del tipo di proprietà. |
|LeaseInd |tinyint |Sì |Indice che fa riferimento a un'altra riga della tabella CqdBuildingOwnershipType, utilizzata per identificare edifici affittati. |
|Proprietario |varchar (50) |Sì |Proprietario dell'edificio. |
|||||

Per impostazione predefinita, la tabella successiva contiene una voce (0,' Unknown ', 0, null).

**CqdBssid**

|Colonna|Tipo di dati|Consenti valori null?|Dettagli|
|:-----|:-----|:-----|:-----|
|BSS |nvarchar (50) |No |Chiave primaria per la tabella CqdBssid. È la BSSID del punto di accesso WiFi. |
|ESS |nvarchar (50) |Sì |Informazioni sul controller del punto di accesso WiFi. |
|PHY |nvarchar (50) |Sì |Informazioni PHY. |
|AP |nvarchar (50) |Sì |Nome punto di accesso WiFi. |
|Creazione |nvarchar (500) |Sì |Nome dell'edificio in cui si trova il punto di accesso Wi-Fi. |
||||

## <a name="cqd-streams"></a>Flussi di CQD

Un flusso CQD è considerato valido, scadente o non classificato. CQM 1,5 ora utilizza la seguente definizione di CQD:

- Un flusso scarso è qualsiasi combinazione delle metriche di chiamata scadente oltre la soglia.
- Quando un flusso di una chiamata è povero, entrambi i flussi della chiamata vengono contrassegnati come poveri. Nelle conferenze, ogni partecipante viene conteggiato come una chiamata univoca e viene segnalato in modo indipendente da tutti gli altri.
- I flussi non classificati sono flussi senza metriche di qualità, ovvero transazioni sintetiche o chiamate brevi.
- Flussi validi = client non mobili
- Non è possibile modificare il classificatore

**Definizione/classificatore di chiamata scadente**

|Metrica|Soglia|
|:-----|:-----|
|DegradationAvg |Maggiore di 1,0 (MOS di rete-1) |
|RoundTrip |Maggiore di 500 |
|PacketLossRate |Maggiore di 0,1 (10%) |
|JitterInterArrival |Maggiore di 30 |
|RatioConcealedSamplesAvg |Maggiore di 0,07 |
|||

JPDR Definition = poor Call Definition meno RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Dove si trova il chiamante/chiamato?

CQD non utilizza campi chiamante/chiamato, bensì utilizza "First" e "Second" perché sono presenti passaggi intermedi tra il chiamante e il destinatario della chiamata.

 **Primo** Sarà sempre l'endpoint del server, ad esempio MCU AV o Mediation Server, se un server è coinvolto nello stream.

 **Secondo** Sarà sempre l'endpoint client, a meno che non si tratta di un flusso Server-Server.

**Esempio di classificazione prima e seconda**

|Endpoint 1 UAType|Endpoint 2 UUAType|Prima|Secondo|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for business) |Endpoint 1 |Endpoint 2 |
|2 (AVMCU) |1 (mMediationServer) |Endpoint 2 |Endpoint 1 |
|4 (Skype for business) |4 (Skype for business) |Il chiamante in MediaLine |Il destinatario della chiamata in MMediaLine |
|||||

Se entrambi gli endpoint sono dello stesso tipo, CQD rende prima la voce del chiamante e la seconda chiamata. Per ulteriori informazioni sui nomi degli endpoint, vedere [questo Blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>Accounting per VPN

Se la soluzione VPN è nota per impostare accuratamente il flag VPN, è tutto pronto. In caso contrario, utilizzare uno dei metodi seguenti:

- Creare un tipo di rete denominato VPN (preferito), quindi associare le subnet VPN a questo nuovo NetworkType VPN.
- Creare un edificio denominato VPN, quindi associare le subnet VPN all'edificio.

## <a name="query-fundamentals"></a>Nozioni fondamentali sulla query

Una query ben formata contiene tutti e tre i parametri seguenti:

- Misura
- Dimensione
- Filtro

Un esempio di query ben formato potrebbe essere "Mostrami flussi poveri [misura] per subnet [dimensione] per l'edificio 6 [filtro]."

## <a name="what-does-union-do"></a>Che cosa fa l'Unione?

L'Unione consente di filtrare le condizioni con l'operatore AND. Esistono scenari in cui è possibile combinare contemporaneamente più condizioni di filtro per ottenere un risultato simile a un'operazione OR.

Esempio: per ottenere tutti i flussi da un edificio, l'Unione fornisce una visualizzazione distinta del set di dati Unito. Per utilizzare l'Unione, inserire testo comune nel campo unione nelle due condizioni di filtro che si desidera collegare.

## <a name="default-report-breakdown"></a>Ripartizione del rapporto predefinita

Se la tecnologia wireless è gestita internamente, è possibile ricreare i rapporti wireless nel bucket gestito.

![Ripartizione del report di CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processi operativi

Esaminare e correggere prima i flussi gestiti. La qualità in quest'area dovrebbe essere 100% all'interno del controllo e quindi più facile da correggere.

### <a name="managed-streams"></a>Flussi gestiti

Esaminare e correggere i flussi gestiti nell'ordine seguente:

1. Server-Server
2. Server-Wired-interno
3. Wired-Wired-interno

### <a name="unmanaged-streams"></a>Flussi non gestiti

Esaminare e correggere i flussi non gestiti nell'ordine seguente:

1. Server-WiFi-interno
2. Server-Wired-esterno
3. Server-Wi-Fi esterno
4. Cablato-esterno-diretto
5. Inoltro cablato esterno
6. Altre non gestite
