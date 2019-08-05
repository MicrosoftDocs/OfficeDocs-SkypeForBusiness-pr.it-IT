---
title: Usare il dashboard qualità chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Riepilogo: informazioni su come usare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: b89f766cfcbfbc9fe2c700162f3c0b4e69a7e6bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186860"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usare il dashboard qualità chiamata per Skype for Business Server
 
**Riepilogo:** Informazioni su come usare il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Call Quality dashboard consente ai professionisti IT di usare i dati aggregati per identificare le aree di interesse nell'ambiente in cui si verificano problemi di qualità multimediale. Consente a un professionista IT di confrontare le statistiche per diversi gruppi di utenti e identificare tendenze e modelli. Non è focalizzato sulla risoluzione dei singoli problemi di chiamata, ma sull'individuazione di problemi e soluzioni che verranno applicati a molti utenti in un ambiente specifico.
  
## <a name="call-quality-dashboard-user-guide"></a>Guida per l'utente del dashboard qualità chiamata

Il dashboard qualità chiamata (Call Quality Dashboard) è un portale Web per la creazione e l'organizzazione di report basati su dati di qualità dell'esperienza (QoE). Call Quality dashboard distribuisce un cubo SSAS per aggregare i dati nel database delle metriche QoE. Questo consente agli utenti di creare e modificare report e di eseguire indagini in tempo reale. Anche se è possibile usare Excel per connettersi direttamente al cubo, il portale è ottimizzato per diversi flussi di lavoro che coinvolgono i dati QoE. Questi dati includono la memorizzazione nella cache dei dati del report per l'accesso rapido, collegamenti profondi alle pagine del report per la condivisione e la pubblicazione di informazioni, la modifica e la creazione di report semplificati e i metadati modificabili per le descrizioni del report. Inoltre, Call Quality dashboard espone le API Web che offrono agli utenti l'accesso a livello di codice ai dati del cubo per l'uso nei dashboard personalizzati. 
  
### <a name="feature-overview"></a>Panoramica delle caratteristiche

Quando un utente visita il dashboard qualità chiamata, ecco cosa vedrà:
  
![Usare Call Quality dashboard](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. Il "riquadro di riepilogo" è il punto in cui è possibile trovare il contesto per il "set di report" (a destra). 
    
2. Le proprietà del livello set di report (inclusa l'altezza dell'asse Y) possono essere impostate facendo clic su "modifica" nel riquadro di riepilogo.
    
3. Il pangrattato consente agli utenti di identificare la posizione corrente all'interno della gerarchia del set di report. 
    
4. I report con i report secondari vengono visualizzati con un collegamento blu. Facendo clic sul collegamento, il drill-down viene analizzato nei report figlio. 
    
Spostando il mouse sui grafici a barre e sulle linee di tendenza verranno visualizzati i valori dettagliati. Il report con lo stato attiva mostrerà il menu azione: "modifica", "clone", "Elimina" e "download". 
  
### <a name="default-reports"></a>Report predefiniti

Quando un utente accede per la prima volta al portale di Call Quality dashboard, viene creato automaticamente un set di report predefinito. Questi report vengono talvolta definiti report di sistema. L'utente può modificare o eliminare liberamente questi report. In genere, gli utenti li estendono creando nuovi rapporti di pari livello e figlio. 
  
Al primo livello, il report "audio streams Monthly trend" Mostra la tendenza mensile per tutti i flussi audio. Spostando il mouse sulle barre in un grafico a barre verrà visualizzata una visualizzazione più dettagliata dei dati rappresentati dal grafico a barre. Se si fa clic sul titolo del report flussi audio mensili, verrà visualizzato il report "flussi audio gestiti o non gestiti", in cui i report vengono divisi tra chiamate gestite e non gestite. Le chiamate gestite sono chiamate effettuate dall'interno del firewall aziendale tramite connessioni cablate. Le chiamate non gestite includono le chiamate effettuate all'esterno del firewall aziendale e tutte le chiamate effettuate tramite Wi-Fi.
  
L'altro report di primo livello è denominato "istogramma di valutazione della qualità delle chiamate segnalate dall'utente". Le valutazioni della qualità delle chiamate sono i numeri forniti dagli utenti di Skype for business alla fine di una chiamata per indicare la qualità della chiamata. I numeri di classificazione variano da 1 a 5, con 1 che sono i peggiori e 5 i migliori. L'istogramma mostra il numero di chiamate audio che avevano la classificazione indicata in un mese. 
  
In generale, se si fa clic sul titolo di uno dei report, verranno spostati in report con filtri aggiuntivi sui dati. Nei report di sistema ogni report figlio Visualizza un sottoinsieme dei dati disponibili nel report padre. Questo fornisce un modello concettualmente semplice per la risoluzione dei problemi: limitare lo spazio del problema analizzando il sottoreport a cui si limitano i dati o le tendenze problematiche. La possibilità di creare nuovi report secondari consente agli utenti di analizzare le proprie ipotesi in merito alla provenienza di specifiche tendenze dei dati.
  
### <a name="creating-and-editing-reports"></a>Creazione e modifica di report

Quando si fa clic su "modifica" nel menu azione di un report, gli utenti vedranno l'editor di report. Ogni report viene supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di report è un'interfaccia utente per la modifica di queste query, nonché le opzioni di visualizzazione del report. Quando un utente apre l'editor di report, questo è ciò che vedrà:
  
![Usare Call Quality dashboard](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. Le dimensioni, le misure e i filtri vengono scelti nel riquadro sinistro. In bilico su uno dei valori esistenti verrà visualizzato un pulsante "x" che consente di rimuovere il valore. Facendo clic sul pulsante "più" accanto a un titolo si aprirà la finestra di dialogo per l'aggiunta di una nuova dimensione, misura o filtro. 
    
2. Le opzioni per la personalizzazione del grafico sono visualizzate nella parte superiore.
    
3. Un'anteprima del report è disponibile nell'editor report. 
    
4. Una descrizione dettagliata del report può essere creata usando la casella Modifica nella parte inferiore. 
    
### <a name="sparklines-in-tables"></a>Grafici sparkline nelle tabelle

Quando StartDate. Month viene aggiunto come dimensione e viene eseguito il rendering dei dati come tendenza in una maschera di tabella, i grafici a barre e i grafici sparkline possono essere visualizzati all'interno delle celle della tabella. Spostando il puntatore del mouse sul grafico a barre e i grafici sparkline verranno visualizzati i valori per singoli mesi. 
  
![Usare Call Quality dashboard](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
Per visualizzare i grafici a barre e i grafici sparkline, la casella di controllo "Mostra grafici sparkline" nella parte superiore dell'editor report deve essere selezionata. In questo modo si seleziona l'opzione tendenza e si sposta il mese in giù in modo che sia l'ultima dimensione, che può essere eseguita anche facendo clic su mese e usando le frecce su e giù per spostare StartDate. mese verso l'alto o verso il basso. 
  
### <a name="settings"></a>Impostazioni

Situato nell'angolo in alto a destra del dashboard, il menu impostazioni contiene collegamenti a pagine utili come l'integrità del sistema e le pagine.
  
![Usare Call Quality dashboard](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
L'eventuale visualizzazione di descrizioni e timestamp dipende dai singoli utenti e queste impostazioni influenzano solo la versione individuale del dashboard, non la modifica del set di report o degli altri utenti. La cancellazione della cache fa sì che tutte le query ricarichino i loro dati dal cubo, mentre il ripristino delle impostazioni predefinite elimina tutti i report creati dall'utente o modificati e ricrea il set di report di sistema, cosa vedrebbe un utente durante l'accesso per la prima volta.
  
Il collegamento dashboard utenti Mostra una pagina in cui gli utenti possono visualizzare altri utenti di Call Quality dashboard e sfogliare i loro report. Quando si condivide un set di report, è sufficiente copiare il collegamento nella barra dell'URL e condividerlo con un altro utente di Call Quality dashboard. Questo collegamento sarà uguale a quello che altri utenti vedranno nella pagina del collegamento dashboard utenti sotto il nome utente.
  
### <a name="supplying-subnet-information"></a>Fornitura di informazioni sulla subnet

Altre informazioni approfondite possono essere rilevate se vengono immesse nel database di archiviazione dati specifici del sito per consentire la creazione di informazioni di mapping da subnet a compilazione (ad esempio la qualità della chiamata cablata/wireless tramite la creazione). 
  
È necessario compilare almeno le tabelle seguenti per creare questi report:
  
- CqdBuilding
    
- CqdNetwork
    
Altre informazioni possono essere fornite nelle tabelle CqdBuildingType e CqdBuildingOwnershipType per consentire ulteriori operazioni di filtro e drill-down. 
  
Lo schema per queste tabelle è definito come segue:
  
**CqdBuilding**

|**Colonna**|**Tipo di dati**|**Consenti valori null?**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|BuildingKey  <br/> |int  <br/> |No  <br/> |Chiave primaria per la tabella CqdBuilding.  <br/> |
|Buildingname  <br/> |varchar (80)  <br/> |No  <br/> |Nome dell'edificio.  <br/> |
|BuildingShortName  <br/> |varchar (10)  <br/> |No  <br/> |Versione più breve del nome dell'edificio.  <br/> |
|OwnershipTypeId  <br/> |int  <br/> |No  <br/> |Chiave esterna, deve corrispondere a uno dei entreis nella tabella CqdBuildingOwners.  <br/> |
|BuildingTypeId  <br/> |int  <br/> |No  <br/> |Chiave esterna, deve corrispondere a una delle voci nella tabella CqdBuildingType.  <br/> |
|Latitutde  <br/> |galleggiante  <br/> |Sì  <br/> |Latitudine dell'edificio.  <br/> |
|Longitudine  <br/> |galleggiante  <br/> |Sì  <br/> |Longitudine dell'edificio.  <br/> |
|CityName  <br/> |varchar (30)  <br/> |Sì  <br/> |Nome della città in cui si trova l'edificio.  <br/> |
|ZipCode  <br/> |varchar (25)  <br/> |Sì  <br/> |Codice postale in cui si trova l'edificio.  <br/> |
|CountryShortCode  <br/> |varchar (2)  <br/> |Sì  <br/> |Codici ISO 3166-1 Alpha-2 per il paese in cui si trova l'edificio.  <br/> |
|StateProvinceCode  <br/> |varchar (3)  <br/> |Sì  <br/> |abbreviazione di 3 lettere per lo stato o la provincia in cui si trova l'edificio.  <br/> |
|InsideCorp  <br/> |po'  <br/> |Sì  <br/> |Bit che indica se l'edificio fa parte della rete aziendale.  <br/> |
|BuildingOfficeType  <br/> |nvarchar (150)  <br/> |Sì  <br/> |Descrizione del tipo di Office Building.  <br/> |
|Area geografica  <br/> |varchar (25)  <br/> |Sì  <br/> |Area geografica in cui si trova l'edificio.  <br/> |
   
**CqdNetwork**

|**Colonna**|**Tipo di dati**|**Consenti valori null?**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|Rete  <br/> |varchar (25)  <br/> |No  <br/> |Indirizzo subnet.  <br/> |
|NetworkRange  <br/> |tinyint  <br/> |Sì  <br/> |Subnet mask.  <br/> |
|NetworkNameID  <br/> |int  <br/> |Sì  <br/> |Facoltativamente, esegue il mapping a una riga nella tabella CqdNetworkName.  <br/> |
|BuildingKey  <br/> |int  <br/> |Sì  <br/> |Chiave esterna, deve corrispondere a una delle voci nella tabella CqdBuilding.  <br/> |
|UpdatedDate  <br/> |DateTime  <br/> |No  <br/> |DateTime per quando la voce è stata aggiornata l'ultima volta.  <br/> |
   
Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ').
  
**CqdBuildingType**

|**Colonna**|**Tipo di dati**|**Consenti valori null?**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|BuildingTypeId  <br/> |int  <br/> |No  <br/> |Chiave primaria per la tabella CqdBuildingType.  <br/> |
|BuildingTypeDesc  <br/> |carattere (18)  <br/> |No  <br/> |Descrizione del tipo di edificio.  <br/> |
   
Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ', 0, null).
  
**CqdBuildingOwnershipType**

|**Colonna**|**Tipo di dati**|**Consenti valori null?**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId  <br/> |int  <br/> |No  <br/> |Chiave primaria per la tabella CqdBuildingOwnershipType.  <br/> |
|OwnershipTypeDesc  <br/> |varchar (25)  <br/> |No  <br/> |Descrizione del tipo di proprietà.  <br/> |
|LeaseInd  <br/> |tinyint  <br/> |Sì  <br/> |Indice che fa riferimento a un'altra riga nella tabella CqdBuildingOwnershipType, usata per identificare gli edifici affittati.  <br/> |
|Proprietario  <br/> |varchar (50)  <br/> |Sì  <br/> |Proprietario dell'edificio.  <br/> |
   
Per impostazione predefinita, la tabella successiva contiene una voce (0,' sconosciuto ', 0, null).
  
**CqdBssid**

|**Colonna**|**Tipo di dati**|**Consenti valori null?**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|BSS  <br/> |nvarchar (50)  <br/> |No  <br/> |Chiave primaria per la tabella CqdBssid. È l'BSSID del punto di accesso WiFi.  <br/> |
|ESS  <br/> |nvarchar (50)  <br/> |Sì  <br/> |Informazioni sul controller di Access Point WiFi.  <br/> |
|PHY  <br/> |nvarchar (50)  <br/> |Sì  <br/> |Informazioni PHY.  <br/> |
|AP  <br/> |nvarchar (50)  <br/> |Sì  <br/> |Nome punto di accesso WiFi.  <br/> |
|Predefiniti  <br/> |nvarchar (500)  <br/> |Sì  <br/> |Nome dell'edificio in cui si trova il punto di accesso WiFi.  <br/> |
   
## <a name="cqd-streams"></a>Flussi Call Quality dashboard

Un flusso Call Quality dashboard sarà valido, scadente o non classificato. CQM 1,5 ora usa la seguente definizione di Call Quality Dashboard: 
  
- Un flusso scadente è una combinazione delle metriche delle chiamate scadenti che vanno oltre la soglia.
    
- Quando un flusso in una chiamata è scadente, entrambi i flussi della chiamata vengono contrassegnati come poveri. Nelle conferenze ogni partecipante viene considerato come una chiamata univoca e viene segnalato indipendentemente da tutti gli altri utenti.
    
- I flussi non classificati sono flussi senza metriche di qualità (ad esempio transazioni sintetiche, chiamate brevi).
    
- Flussi validi = client non mobili
    
- Non è possibile modificare il classificatore
    
**Classificazione/classificatore delle chiamate non di qualità**

|**Metrica**|**Soglia**|
|:-----|:-----|
|DDegradationAvg  <br/> |Maggiore di 1,0 (MOS di rete-1)  <br/> |
|RoundTrip  <br/> |Maggiore di 500  <br/> |
|PacketLossRate  <br/> |Maggiore di 1 (10%)  <br/> |
|JitterInterArrival  <br/> |Maggiore di 30  <br/> |
|RRatioConcealedSamplesAvg  <br/> |Maggiore di. 07  <br/> |
   
Definizione di JPDR = definizione chiamata insufficiente meno RatioConcealedSamplesAvg 
  
## <a name="where-is-callercallee"></a>Dove si trova il chiamante/chiamato?

Call Quality Dashboard non usa campi chiamante/chiamato. Questi sono stati rinominati "First" e "Second" perché sono presenti passaggi intermedi tra il chiamante e il chiamato.
  
 **Primo** Sarà sempre l'endpoint del server, ad esempio MCU AV; Mediation Server) se un server è coinvolto nello stream.
  
 **Secondo** Sarà sempre l'endpoint client, a meno che non si tratta di un flusso Server-Server.
  
**Esempio di classificazione prima e seconda**

|**Endpoint 1 UAType**|**Endpoint 2 UUAType**|**Primo**|**Second**|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  <br/> |4 (Skype for business)  <br/> |Endpoint 1  <br/> |Endpoint 2  <br/> |
|2 (AVMCU)  <br/> |1 (mMediationServer)  <br/> |Endpoint 2  <br/> |Endpoint 1  <br/> |
|4 (Skype for business)  <br/> |4 (Skype for business)  <br/> |Il chiamante in MediaLine  <br/> |Il chiamato in MMediaLine  <br/> |
   
Se entrambi gli endpoint sono dello stesso tipo, Call Quality dashboard consentirà prima di tutto la voce del chiamante e il chiamato diventa il secondo. Per altre informazioni, vedere [questo Blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) .
  
## <a name="accounting-for-vpn"></a>Contabilità per VPN

Se la soluzione VPN è nota per impostare in modo accurato il contrassegno VPN, è tutto impostato. In caso contrario, usare uno dei metodi seguenti:
  
- Creare un tipo di rete denominato VPN (preferito), quindi associare subnet VPN a questo nuovo NetworkType VPN.
    
- Creare un edificio denominato VPN, quindi associare subnet VPN a questo edificio. 
    
## <a name="query-fundamentals"></a>Elementi fondamentali della query

Una query ben formata contiene tutti e tre i parametri seguenti: 
  
- Misura
    
- Dimensione
    
- Filter
    
Un esempio di query ben formata sarebbe "Mostra i flussi poveri [misura] per subnet [dimensione] per l'edificio 6 [filtro]."
  
## <a name="what-does-union-do"></a>Cosa fa l'Unione?

L'Unione consente di filtrare le condizioni con l'operatore AND. Esistono scenari in cui è necessario combinare contemporaneamente più condizioni di filtro per ottenere un risultato o simile
  
Esempio: quando devi ottenere tutti i flussi da un'Unione di edifici, offrirai una visualizzazione distinta del set di dati Unito. Per usare l'Unione, inserire testo comune nel campo unione sulle due condizioni di filtro che si desidera includere nell'Unione. 
  
## <a name="default-report-breakdown"></a>Ripartizione del report predefinita

Se la funzionalità wireless è gestita internamente, è possibile ricreare i report wireless nel contenitore gestito. 
  
![Ripartizione report di Call Quality dashboard](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a>Processi operativi

Iniziare rivedendo e rimediando i flussi gestiti. La qualità in quest'area dovrebbe essere di 100% all'interno del controllo e quindi più semplice da correggere. 
  
### <a name="managed-streams"></a>Flussi gestiti

Esaminare e correggere i flussi gestiti nell'ordine seguente: 
  
1. Server-Server 
    
2.  Server-cablato-interno
    
3. Cablato-cablato-interno 
    
### <a name="unmanaged-streams"></a>Flussi non gestiti

Esaminare e correggere i flussi non gestiti nell'ordine seguente: 
  
1. Server-WiFi-interno
    
2. Server-cablato-esterno
    
3. Server-WiFi-esterno
    
4. Cablato-esterno-diretto
    
5. Inoltro via cavo-esterno
    
6. Altri non gestiti
    

