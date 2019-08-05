---
title: Attivazione e utilizzo di Call Quality Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: 'Informazioni su come attivare e usare il dashboard di qualità delle chiamate di Skype for business online e ottenere report riepilogativi sulla qualità delle chiamate. '
ms.openlocfilehash: a4fc0875e9c9672a53f6399aac344285b070855a
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183709"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online

Informazioni su come configurare l'organizzazione di Office 365 in modo da usare il dashboard qualità chiamata per monitorare la qualità delle chiamate.
  
Il dashboard qualità chiamata (Call Quality Dashboard) per Microsoft teams e Skype for business online consente di ottenere informazioni approfondite sulla qualità delle chiamate effettuate con i servizi Microsoft teams e Skype for business. Questo argomento descrive i passaggi che è necessario completare per iniziare a raccogliere dati.
  
  
## <a name="latest-changes-and-updates"></a>Ultime modifiche e aggiornamenti

Le modifiche più recenti a Call Quality dashboard sono le seguenti:
  
- Include i dati di Microsoft teams oltre ai dati di Skype for business online.
    
- I report di riepilogo includono un filtro prodotto per selezionare tutti i dati, i dati di Microsoft teams o i dati di Skype for business online.

- La logica di classificazione della qualità del flusso video e VBSS è stata aggiornata. Vedere la [classificazione in Stream in dashboard qualità chiamata](stream-classification-in-call-quality-dashboard.md) per le definizioni di classificatore più recenti.

Fare riferimento a questo articolo per un elenco di [dimensioni e misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Le informazioni sugli aggiornamenti e le modifiche apportate al dashboard possono essere trovate facendo clic sul collegamento nella **buona notizia.** banner quando viene visualizzato nel dashboard.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Attivare i report di riepilogo di Microsoft Call Quality Dashboard (Call Quality Dashboard)

Prima di poter iniziare a usare Call Quality dashboard, è necessario attivarlo per l'organizzazione di Office 365.

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**
 
1. Accedere all'organizzazione di Office 365 tramite l'account di amministratore del servizio Microsoft teams e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
    
2. Nel riquadro sinistro, in **centri di amministrazione**, selezionare **Microsoft teams** per aprire l'interfaccia di amministrazione di Microsoft teams.
    
3. Nell'interfaccia di amministrazione di Microsoft teams selezionare **chiamata dashboard qualità** nel riquadro sinistro.
    
  
4. Nella pagina visualizzata accedere con l'account di amministratore globale o con l'account di amministrazione del servizio Microsoft teams e quindi specificare le credenziali per l'account quando richiesto.
    
     ![Schermata che mostra il prompt delle credenziali](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Dopo aver effettuato l'accesso, una volta attivato, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.  
> [!NOTE]
> Potrebbe essere necessario un paio di ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report. 

![Icona che mostra il logo](media/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**
 
1. Accedere all'organizzazione di Office 365 con un account di amministratore e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
    
2. Nel riquadro sinistro, in **centri di amministrazione**, seleziona **Skype for business** per aprire l'interfaccia di amministrazione di Skype for business.
    
3. Nell'interfaccia di amministrazione di Skype for Business seleziona **strumenti** nel riquadro sinistro e quindi scegli **Skype for business online Call Quality dashboard**.
    
     ![Schermata che mostra la selezione del dashboard qualità chiamata](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Nella pagina visualizzata accedere con l'account di amministratore globale e quindi specificare le credenziali per l'account quando richiesto.
    
     ![Schermata che mostra il prompt delle credenziali](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Dopo aver effettuato l'accesso, una volta attivato, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Caratteristiche del dashboard qualità chiamata per Microsoft teams e Skype for business online 
<a name="BKMKFeaturesOfTheCQD"> </a>

I report di riepilogo di Call Quality dashboard includono un sottoinsieme delle funzionalità pianificate per i report dettagliati. Di seguito sono riepilogate le differenze tra le due edizioni:
  
|**Funzionalità**|**Report di riepilogo**|**Report dettagliati**|
|:-----|:-----|:-----|
|Metrica di condivisione applicazioni  <br/> |No  <br/> |Sì  <br/> |
|Supporto per informazioni sulla creazione di clienti  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |
|Supporto per le informazioni sull'endpoint cliente  <br/> |Solo in cqd.teams.microsoft.com  <br/> |Solo in cqd.teams.microsoft.com  <br/> |
|Supporto analisi drill-down  <br/> |No  <br/> |Sì  <br/> |
|Metriche per l'affidabilità multimediale  <br/> |No  <br/> |Sì  <br/> |
|Report di out-of-the-box  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |
|Report generali  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |
|Set di report per utente  <br/> |No  <br/> |Sì  <br/> |
|Personalizzazione del set di report (aggiunta, eliminazione, modifica di report)  <br/> |No  <br/> |Sì  <br/> |
|Metriche di condivisione dello schermo basate su video  <br/> |No  <br/> |Sì  <br/> |
|Metriche video  <br/> |No  <br/> |Sì  <br/> |
|Quantità di dati disponibili  <br/> |Ultimi 6 mesi  <br/> |Ultimi 6 mesi  <br/> |
|Dati di Microsoft Teams  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |
   
### <a name="out-of-the-box-reports"></a>Report di out-of-the-box

Entrambe le edizioni di Call Quality dashboard offrono un'esperienza fuori sede, fornendo le metriche di qualità delle chiamate senza la necessità di creare nuovi report. Una volta elaborati i dati nel back-end, è possibile iniziare a visualizzare i dati relativi alla qualità delle chiamate nei report.
  
### <a name="overview-reports"></a>Report generali

Entrambe le edizioni di Call Quality dashboard costituiscono un punto di ingresso di alto livello per le informazioni generali sulla qualità delle chiamate, ma il modo in cui vengono presentate le informazioni in rapporti di riepilogo è diverso da quello dei report dettagliati.
  
I report di riepilogo includono una visualizzazione semplificata del rapporto di pagina a schede che consente agli utenti di esplorare e comprendere rapidamente lo stato e le tendenze della qualità delle chiamate complessive.
  
Le quattro schede includono:
  
- **Qualità complessiva delle chiamate** : fornisce informazioni su tutti i flussi, ovvero un'aggregazione di flussi client-server e flussi client-client, oltre a flussi client server e client distinti, sotto forma di tendenze mensili e quotidiane.
    
- **Server-client** : fornisce dettagli aggiuntivi per i flussi tra endpoint server e client.
    
- **Client-client** : fornisce dettagli aggiuntivi per i flussi tra due endpoint client.
    
- **SLA qualità vocale** -fornisce informazioni sulle chiamate incluse nel contratto di qualità vocale di Skype for business online.
    
### <a name="overall-call-quality-tab"></a>Scheda qualità complessiva delle chiamate

Usare i dati in questa scheda per valutare lo stato e le tendenze della qualità delle chiamate esaminando i conteggi dei flussi e le percentuali scarse. La legenda nell'angolo in alto a destra mostra il colore e gli elementi visivi che rappresentano queste metriche.
  
![Screenshot che mostra la scheda qualità chiamata](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
I flussi sono classificati in tre gruppi: Buono, scadente e non classificato. Vengono inoltre calcolati valori di *% poveri* che consentono di ottenere il rapporto tra i flussi classificati come *poveri* e il conteggio totale del flusso classificato. Poiché il *povero% = flussi poveri/(flussi poveri + flussi buoni) * 100* , questo rende il *povero%* inalterato dalla presenza di più flussi non *classificati* . Per ciò che viene usato per classificare un flusso come povero o buono, vedere [classificazione dello stream in Dashboard Quality](stream-classification-in-call-quality-dashboard.md).
  
Usare la scala a sinistra per misurare i valori del conteggio del flusso.
  
![Schermata che mostra i valori del conteggio dei flussi](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Usare la scala a destra per misurare i valori di% poveri.
  
![Screenshot che mostra i valori di% poveri](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Puoi anche ottenere i valori numerici effettivi passando il puntatore del mouse su una barra.
  
> [!NOTE]
> L'esempio seguente è costituito da un set di dati di esempio molto piccolo e i valori non sono realistici per una distribuzione effettiva. 
  
![Screenshot che mostra l'uso del mouse per accedere ai dati](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume complessivo del flusso è un fattore importante per determinare la pertinenza delle percentuali di scarsità calcolate. Minore è il volume dei flussi generali, meno affidabili sono i valori di percentuale di scarsità segnalati.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Scheda client-server e schede client-client

Queste due schede contengono dettagli aggiuntivi per i flussi che hanno avuto luogo negli scenari endpoint-to-endpoint. Entrambe le schede hanno quattro sezioni comprimibili, che rappresentano quattro scenari in cui i flussi multimediali scorrono.
  
- Cablato all'interno
    
- Cablata all'esterno
    
- WiFi all'interno
    
- WiFi all'esterno
    
#### <a name="inside-test"></a>Test all'interno

Durante l'elaborazione, il back-end Call Quality Dashboard classifica un flusso come *all'interno* o *all'esterno* usando le informazioni sulla creazione, se esiste. Gli endpoint di ogni flusso sono associati a un indirizzo di subnet. Se la subnet si trova nell'elenco delle subnet contrassegnate InsideCorp nelle informazioni di compilazione caricate, viene considerato *all'interno*. Se le informazioni sulla compilazione non sono ancora state caricate, i flussi verranno sempre classificati all' *esterno*. Tieni presente che l'endpoint client in test per server-client viene considerato solo. Poiché i server sono sempre esterni dal punto di vista dell'utente, questo non viene contabilizzato nel test.
  
#### <a name="wired-vs-wifi"></a>Wi-Fi cablato

Come indicano i nomi, si tratta di un criterio di classificazione basato sul tipo di connessioni client. Anche in questo caso, il server è sempre cablato e non è incluso nel calcolo.
  
> [!NOTE]
> Dato un flusso, se uno dei due endpoint è connesso a una rete Wi-Fi, viene classificato come WiFi in Call Quality dashboard. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selezione dei dati del prodotto da visualizzare nei report
<a name="BKMKProductFilter"></a>

Nei report di riepilogo e posizione avanzata è possibile usare l'elenco a discesa **filtro prodotto** per visualizzare tutti i dati del prodotto, solo i dati di Microsoft teams o solo i dati di Skype for business online.
  
![Screenshot che mostra le opzioni di controllo del filtro prodotto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In report dettagliati è possibile usare la dimensione **is teams** per filtrare i dati in Microsoft teams o nei dati di Skype for business online nell'ambito della definizione del report.
  
## <a name="upload-tenant-data-information"></a>Caricare informazioni sui dati del tenant
<a name="BKMKTenantDataInformationUpload"></a>

Il dashboard report di riepilogo di Call Quality dashboard include una pagina di **caricamento dei dati del tenant** , a cui si accede selezionando **Carica dati tenant** dal menu impostazioni nell'angolo in alto a destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio il mapping di indirizzi IP e informazioni geografiche, la mappatura di ogni punto di accesso wireless e il relativo indirizzo MAC, la mappatura dell'endpoint all'endpoint marca/modello/tipo e così via.
  
![Screenshot che mostra il dashboard qualità chiamata](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Nella pagina **caricamento dati tenant** usare il menu a discesa per scegliere un tipo di file di dati per il caricamento. Il tipo di dati del file denota il contenuto del file, ad esempio "Building" si riferisce al mapping dell'indirizzo IP e dell'edificio, oltre ad altre informazioni geografiche, "endpoint" fa riferimento al mapping del nome dell'endpoint all'endpoint marca/modello/tipo... informazioni). Attualmente supportiamo il caricamento dei tipi di dati "Building" e "endpoint" per Call Quality dashboard. teams. Microsoft. com (nella fase di anteprima e non ancora ufficialmente disponibile), cqd.lync.com supporta solo il caricamento del tipo di dati "Building". Verranno aggiunti altri tipi di dati con le versioni successive.
    
2. Dopo aver selezionato il tipo di dati file, fare clic su **Sfoglia** per scegliere un file di dati.
    
   - Il file di dati deve essere un file con estensione TSV (valori separati da tabulazioni) o un file CSV (delimitato da virgole). Se si usa un file CSV, qualsiasi campo che contiene una virgola deve essere racchiuso tra virgolette o avere la virgola rimossa. Ad esempio, se il nome dell'edificio è NY, NY, nel file CSV deve essere immesso come "NY, NY".
    
   - Le dimensioni del file di dati non devono essere superiori a 50 MB.

   - File caricato in cqd.teams.microsoft.com ha esteso il limite di riga di 1 milione per velocizzare le prestazioni delle query. Potremmo imporre il limite anche a cqd.lync.com.
    
   - Per ogni file di dati, ogni colonna del file deve corrispondere a un tipo di dati predefinito, descritto più avanti in questo argomento.
    
3. Dopo aver selezionato un file di dati, specificare **Data di inizio** e, facoltativamente, **specificare una data di fine**.
    
4. Dopo aver selezionato **Data inizio**, selezionare **carica** per caricare il file nel server Call Quality dashboard.
    
    Prima che il file venga caricato, viene prima convalidato. Una volta convalidato, viene archiviato in un BLOB di Azure. Se la convalida non riesce o il file non viene archiviato in un BLOB di Azure, viene visualizzato un messaggio di errore che richiede una correzione al file. L'immagine seguente mostra un errore che si verifica quando il numero di colonne nel file di dati non è corretto.
    
     ![Screenshot che mostra un errore di convalida del caricamento](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se non si verificano errori durante la convalida, il caricamento del file avrà esito positivo. È quindi possibile visualizzare il file di dati caricati nella **** tabella uploads, che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.
    
    Ogni record Mostra un file di dati del tenant caricato, con il tipo di file, l'ora dell'ultimo aggiornamento, il periodo di tempo, la descrizione, un'icona di rimozione e un'icona di download. Per rimuovere un file, selezionare l'icona del cestino nella tabella. Per scaricare un file, selezionare l'icona download nella colonna **Scarica** della tabella.
    
     ![Screenshot che mostra la tabella uploads](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a>Formato e struttura del file di dati tenant
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Creazione di file di dati
Call Quality dashboard usa il file di dati della costruzione per derivare prima la colonna subnet dalla colonna Expanding Network + NetworkRange, quindi unire la colonna subnet alla prima colonna subnet/Second subnet di record di chiamata per mostrare l'edificio/città/paese/area geografica... informazioni. Il formato del file di dati caricato deve soddisfare quanto segue per passare il controllo di convalida prima del caricamento.
  
- Il file deve essere un file con estensione TSV, ovvero in ogni riga le colonne sono separate da una TABULAzione o da un file CSV con ogni colonna separata da una virgola.
    
- Il contenuto del file di dati non include le intestazioni di tabella. Questo significa che la prima riga del file di dati deve essere dati reali, non intestazioni come "rete" e così via.
    
- Per ogni colonna, il tipo di dati può essere solo String, Number o bool. Se si tratta di un numero, il valore deve essere un valore numerico; Se è bool, il valore deve essere 0 o 1.
    
- Per ogni colonna, se il tipo di dati è stringa, i dati possono essere vuoti (ma deve essere comunque separato da un delimitatore appropriato, ad esempio una tabulazione o una virgola). Questo assegna un valore di stringa vuoto solo al campo.
    
- Devono essere presenti 14 colonne per ogni riga, ogni colonna deve avere il tipo di dati seguente e le colonne devono essere nell'ordine elencato nella tabella seguente:
    
|**Nome colonna**|**Tipo di dati**|**Esempio**|
|:-----|:-----|:-----|
|Rete  <br/> |Stringa  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |Stringa  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Numero  <br/> |26  <br/> |
|Buildingname  <br/> |Stringa  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |Stringa  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Stringa  <br/> |Terminazione IT  <br/> |
|BuildingOfficeType  <br/> |Stringa  <br/> |Ingegneria  <br/> |
|Città  <br/> |Stringa  <br/> |Seattle  <br/> |
|ZipCode  <br/> |Stringa  <br/> |98001  <br/> |
|Paese  <br/> |Stringa  <br/> |NOI  <br/> |
|Stato  <br/> |Stringa  <br/> |WA  <br/> |
|Area geografica  <br/> |Stringa  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una SuperNet (combinazione di più subnet con un unico prefisso di routing). Tutti gli upload di nuovi edifici verranno controllati per gli intervalli sovrapposti. Se in precedenza è stato caricato un file di costruzione, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e correggere il problema prima del caricamento. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare l'errata mappatura delle subnet agli edifici nei report. Alcune implementazioni VPN non segnalano in modo accurato le informazioni sulla subnet. Si consiglia di aggiungere voci separate per ogni indirizzo della subnet VPN in una rete a 32 bit separata per l'aggiunta di una subnet VPN al file di compilazione, anziché una voce per la subnet. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, dovresti avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32, incluso. 

### <a name="endpoint-data-file"></a>File di dati endpoint
Call Quality dashboard usa il file di dati dell'endpoint unendo la relativa colonna EndpointName alla prima colonna nome endpoint client/secondo endpoint client del record di chiamata per visualizzare le informazioni sul tipo o il modello di endpoint. Il formato del file di dati caricato deve soddisfare quanto segue per passare il controllo di convalida prima del caricamento.

- Il file deve essere un file con estensione TSV, ovvero in ogni riga le colonne sono separate da una TABULAzione o da un file CSV con ogni colonna separata da una virgola.

- Il contenuto del file di dati non include le intestazioni di tabella. Questo significa che la prima riga del file di dati deve essere dati reali, non intestazioni come "EndpointName" e così via.

- Per ogni colonna, il tipo di dati può essere solo stringa e non deve avere più di 64 caratteri, che è la lunghezza massima consentita.

- Per ogni colonna, i dati possono essere vuoti (ma devono comunque essere separati da un delimitatore appropriato, ad esempio una tabulazione o un punto e virgola). Questo assegna un valore di stringa vuoto solo al campo.

- Devono essere presenti 7 colonne per ogni riga e le colonne devono essere nell'ordine elencato nella tabella seguente.

- EndpointName deve essere univoco in caso contrario, il caricamento non riuscirà a causa di una riga duplicata perché causerà l'Unione errata.

-  EndpointLabel1, EndpointLabel2, EndpointLable3 sono etichette personalizzabili dall'utente, possono essere stringhe vuote o valori che gli utenti preferiscono, ad esempio "reparto IT designato 2018 laptop", "asset tag 5678"... e così via.

|**Nome colonna**|**Tipo di dati**|**Esempio**|
|:-----|:-----|:-----|
|EndpointName  <br/> |Stringa  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |Stringa  <br/> |Fabrikam Inc  <br/> |
|EndpointModel  <br/> |Stringa  <br/> |Modello Fabrikam 123  <br/> |
|EndpointType   <br/> |Stringa  <br/> |Portatile  <br/> |
|EndpointLabel1  <br/> |Stringa  <br/> |HA designato il portatile di 2018  <br/> |
|EndpointLabel2  <br/> |Stringa  <br/> |Tag asset 5678  <br/> |
|EndpointLabel3  <br/> |Stringa  <br/> |Acquistare 2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>Selezione del tipo di elemento multimediale in report dettagliati
<a name="BKMKMediaType"></a>

I report dettagliati supportano la ricerca di qualità e affidabilità multimediale per i tipi di elementi multimediali per la condivisione di audio, video, applicazioni e video. Le dimensioni, le misure e i filtri specifici di un singolo tipo di elemento multimediale hanno "audio", "video", "condivisione applicazioni" o "VBSS" come prefisso.
  
![Screenshot che mostra le dimensioni del dashboard qualità chiamata.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Per visualizzare le dimensioni e le misure per un singolo tipo di supporto, è possibile che siano necessarie la nuova dimensione MediaType e il filtro. Ad esempio, per avere un report che mostra i conteggi totali delle sessioni tra diversi tipi di elementi multimediali, Includi la dimensione MediaType.
  
![Schermata che mostra il conteggio Total Stream di Call Quality dashboard.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Argomenti correlati
[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Usare la chiamata analitica per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
