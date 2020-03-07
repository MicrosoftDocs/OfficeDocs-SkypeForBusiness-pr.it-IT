---
title: Attivare e usare il dashboard qualità chiamata
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 'Informazioni su come attivare e usare il dashboard qualità chiamata e ottenere report riepilogativi sulla qualità delle chiamate. '
ms.openlocfilehash: 9e9c70c88aec9fcdf898d94a17f46f76bd2c608a
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559897"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Attivare e usare la chiamata Quality dashboard per Microsoft teams e Skype for business online

Informazioni su come configurare l'organizzazione di Office 365 in modo da usare il dashboard qualità chiamata per monitorare la qualità delle chiamate.
  
Call Quality Dashboard (Call Quality Dashboard) offre informazioni sulla qualità delle chiamate effettuate con i servizi Microsoft teams e Skype for business online. In questo argomento vengono illustrati i passaggi per iniziare a raccogliere i dati che è possibile usare per risolvere i problemi di qualità delle chiamate.

Attualmente, Advanced Call Quality dashboard e Call Quality dashboard sono entrambi disponibili per l'uso. Advanced Call Quality dashboard è disponibile all' <span>https://cqd.teams.microsoft.com</span>indirizzo. Nuovo URL, ma lo stesso accesso con le credenziali di amministratore.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Call Quality dashboard

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.

Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.


## <a name="latest-changes-and-updates"></a>Ultime modifiche e aggiornamenti


L'aggiornamento di Call Quality Dashboard (a partire dall'inizio di novembre 2019) offre un dashboard di Call Quality dashboard quasi in tempo reale. I dati di Call Quality dashboard sono ora disponibili in media in 30 minuti (in confronto alla Call Quality dashboard precedente, in media 24 ore).  L'aggiornamento di Call Quality dashboard usa le informazioni di identificazione dell'utente finale (EUII), dando agli amministratori la possibilità di eseguire il drill-down e lo zoom avanti fino al livello dell'utente. È inoltre possibile segnalare l'interattività per supportare nuovi scenari, ad esempio:


- Qualità delle chiamate per area geografica:
  - Data per area geografica
  - aggregato fino a ora per area geografica
  - posizioni specifiche
  - subnet specifica
  - utente o utenti interessati

- Affidabilità delle chiamate/errore per area geografica:
  - Data per area geografica
  - aggregato fino a ora per area geografica
  - posizioni specifiche
  - subnet specifica
  - utente o utenti interessati

- Valuta la mia chiamata (RMC) per area geografica: da mese per area geografica aggregata fino a posizioni specifiche per gli utenti che prevedono valutazioni RMC basse. Call Quality dashboard v3 include anche feedback Verbatim.
- Helpdesk: disponibile per un utente specifico su chiamate o riunioni P2P oppure per tutti i partecipanti e i dettagli delle chiamate. Consente di identificare i possibili problemi di sistema in base a posizione di rete, dispositivi o firmware.  
- Versioni client: visualizzare la sessione e gli utenti conta per ogni versione del client oppure eseguire il drill-down in nomi utente per ogni versione del client. I filtri predefiniti per il tipo di prodotto e client consentono di mettere a punto le versioni a specifici client.
- Endpoint: Mostra gli endpoint del computer mappati per creare/modellare il PC/Mac. Mostra la qualità aggregata per creazione/modello. I dati di mapping vengono caricati in modo simile alla creazione di dati.

Advanced Call Quality Dashboard (v3) offre anche il supporto RBAC, se EUII Access non è disponibile.  

Un amministratore può gestire Skype for Business Server 2019 (non solo Skype for business online e Microsoft Teams) tramite Call Quality dashboard versione 3. Questo richiede un'implementazione ibrida e l'uso del connettore dati chiamata. Per altre informazioni, vedere [pianificare il connettore dati](/SkypeForBusiness/hybrid/plan-call-data-connector) per le chiamate.

Call Quality dashboard versione 2 aggiunta:

- Dati per Microsoft teams e Skype for business online
- I report di riepilogo includono un filtro prodotto per selezionare tutti i dati, i dati di Microsoft teams o i dati di Skype for business online
- Aggiornamento della logica di classificazione della qualità del flusso video e VBSS. Vedere la [classificazione del flusso nel dashboard qualità chiamata](stream-classification-in-call-quality-dashboard.md) per le definizioni del classificatore.

Fare riferimento a questo articolo per un elenco di [dimensioni e misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Per visualizzare le informazioni sugli aggiornamenti e le modifiche apportate al dashboard, fare clic sul collegamento nella **buona notizia.** banner quando viene visualizzato nel dashboard.

Call Quality dashboard versione 1 ha fornito agli amministratori di Skype for Business Server 2015 le caratteristiche seguenti:

- Accesso ai dati del report memorizzati nella cache per l'accesso rapido
- Collegamenti profondi alle pagine del report per informazioni sulla condivisione e la pubblicazione
- Modifica e creazione di report semplificati e metadati modificabili per le descrizioni dei report
- API Web che forniscono l'accesso a livello di codice ai dati del cubo per l'uso nei dashboard personalizzati

## <a name="cqd-near-real-time-nrt-data"></a>Dati di Call Quality dashboard near-Real-Time (NRT)

Advanced Call Quality Dashboard (v3, rilasciata il 2019 novembre) usa un feed di dati quasi in tempo reale. I record di chiamata sono disponibili presso il portale di Call Quality dashboard entro 30 minuti dalla fine della chiamata. I record di chiamata della pipeline NRT sono disponibili solo per alcuni mesi prima di essere rimossi dal set di dati. Call Quality dashboard V3 unisce i dati della pipeline V2 corrente con i dati della NRT della pipeline V3. Le query sui portali V2 e V3 per i dati del periodo di archiviazione producono gli stessi risultati. Le query di dati V2 e V3 per i dati NRT e NRT data + PII periodi saranno diverse.

### <a name="piieuii-data"></a>Dati personali/EUII

I dati PII o EUII provengono solo dalla pipeline V3. A causa di motivi di conformità, i dati personali/EUII vengono conservati solo per 30 giorni. Dato che i dati della NRT attraversano il contrassegno di 30 giorni, i campi PII/EUII vengono cancellati, ottenendo dati della NRT senza informazioni personali. I campi PII/EUII sono:

- Indirizzo IP completo
- Indirizzo MAC (Media Access Control)
- ID set di servizi di base (BSSID)
- URI SIP (Session Initiation Protocol) (solo Skype for business)
- Nome dell'entità utente (UPN)
- Nome endpoint computer
- Feedback Verbatim dell'utente
- ID oggetto (l'ID oggetto Active Directory dell'utente dell'endpoint)

### <a name="date-controls"></a>Controlli data

Call Quality dashboard V3 aggiunge i nuovi tipi di tendenza a rotazione seguenti:

- 5 giorni
- 7 giorni
- 30 giorni
- 60-giorno
- 90-giorno

Il parametro data URL ora può accettare un campo Day. I report di giorni lavorativi usano le date specificate nel formato AAAA-MM-DD come ultimo giorno della tendenza.  Il parametro data URL "00" indica "oggi".

|URL| Data di fine dell'andamento del giorno di rotolamento|
|:---|:---|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02/</span>   |Giorno corrente di feb 2019|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02-15/</span>|15 feb 2019|
|<span>https://<cqdv3>/SPD/#/dashboard/<reportid>/00/</span>        |Giorno corrente|
|||

Per impostazione predefinita, il giorno corrente del mese viene usato come ultimo giorno dell'andamento del giorno di rotolamento.

### <a name="drill-thru-functionality"></a>Funzionalità drill-through

Call Quality dashboard V3 supporta l'uso dei campi drill-through o drill-down nei report SPD. Se sono selezionati questi campi di dimensione, il report apre automaticamente una scheda report diversa e filtra il valore selezionato. I campi con il filtro drill-through assegnato sono distinti da un'icona di cursore diversa (il puntatore) quando si passa il mouse su di essi.

Quando viene selezionato un campo drill-through, il dashboard passa automaticamente alla nuova scheda specificata e applica un filtro con il valore selezionato. Se la scheda include i campi drill-through personalizzati e uno è selezionato, i filtri drill-through precedenti e quelli nuovi vengono propagati in avanti. In questo modo è possibile creare un report che limita progressivamente il set di dati risultante.

Ad esempio, in un report drill-through di qualità delle chiamate, un utente può fare clic sulla data a cui si vuole eseguire il drill-through, che porta alla scheda posizione.

![Screenshot: Mostra il report drill-through](media/CQD-drill-thru-report.png)

È possibile aggiungere più date dalla scheda posizione, ad esempio l'aggiunta di 2019-09-22 alla data: 2019-09-24: 

![Screenshot: aggiungere una data al report drill-through](media/CQD-add-date.png)

> [!NOTE]
> Non passare direttamente all'ultima scheda. Senza filtri selezionati da un precedente drill-through i risultati sarebbero troppo grandi per essere visualizzati in una tabella.

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Attivare i report di riepilogo di Microsoft Call Quality Dashboard (Call Quality Dashboard)

Prima di poter iniziare a usare Call Quality dashboard, attivarlo per l'organizzazione di Office 365 come segue:

![Icona che mostra il logo](media/teams-logo-30x30.png) Microsoft teams con l'interfaccia di amministrazione di **Microsoft teams**

1. Accedere all'organizzazione di Office 365 tramite l'account di amministratore del servizio Microsoft teams e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
2. Nel riquadro sinistro, in **centri di amministrazione**, selezionare **Microsoft teams** per aprire l'interfaccia di amministrazione di Microsoft teams.
3. Nell'interfaccia di amministrazione di Microsoft teams selezionare **chiamata dashboard qualità** nel riquadro sinistro.
4. \(Nella pagina che apre https://<span>CQD.teams.Microsoft.com<span/>\)fare clic su **Accedi** e immettere l'account di amministratore globale o le informazioni dell'account di amministratore del servizio Microsoft teams.

    ![Screenshot: Mostra il prompt delle credenziali](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Dopo aver effettuato l'accesso, una volta attivato, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.  
> [!NOTE]
> Potrebbe essere necessario uno o più ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report.

![Icona del logo](media/sfb-logo-30x30.png) Skype for business **con il portale legacy di Skype for business**

1. Accedere all'organizzazione di Office 365 con un account di amministratore e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
2. Nel riquadro sinistro, in **centri di amministrazione**, selezionare **Microsoft teams** per aprire l'interfaccia di amministrazione di Microsoft teams.
3. Nell'interfaccia di amministrazione di Microsoft teams selezionare **portale legacy** nel riquadro sinistro, selezionare **strumenti**e quindi selezionare **Skype for business online Call Quality dashboard**.

     ![Screenshot: selezionare il dashboard qualità chiamata](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Nella pagina visualizzata accedere con l'account di amministratore globale e quindi specificare le credenziali per l'account quando richiesto.

Dopo aver effettuato l'accesso, una volta attivato, il dashboard qualità chiamata inizierà a raccogliere ed elaborare i dati.

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Caratteristiche del dashboard qualità chiamata per Microsoft teams e Skype for business online

<a name="BKMKFeaturesOfTheCQD"> </a>


I report di riepilogo di Call Quality dashboard includono un sottoinsieme delle funzionalità pianificate per i report dettagliati. Di seguito sono riepilogate le differenze tra le edizioni:
  
|Funzionalità|Report di riepilogo|Report dettagliati|
|:--- |:--- |:--- |
|Metrica di condivisione applicazioni | No | Sì |
|Supporto per informazioni sulla creazione di clienti | Sì | Supporto per più paesi |
|Supporto per le informazioni sull'endpoint cliente | Solo in <span>CQD.teams.Microsoft.com<span/> | Solo in <span>CQD.teams.Microsoft.com<span/> |
|Supporto analisi drill-down   | No   | Sì   |
|Metriche per l'affidabilità multimediale   | No   | Sì   |
|Report di out-of-the-box   | Sì   | Supporto per più paesi   |
|Report generali   | Sì   | Supporto per più paesi   |
|Set di report per utente   | No   | Sì   |
|Personalizzazione del set di report (aggiunta, eliminazione, modifica di report)   | No   | Sì   |
|Metriche di condivisione dello schermo basate su video   | No   | Sì   |
|Metriche video   | No   | Sì   |
|Quantità di dati disponibili   | Ultimi 12 mesi   | Ultimi 12 mesi   |
|Dati di Microsoft Teams   | Sì   | Supporto per più paesi   |
| | | |

### <a name="out-of-the-box-reports"></a>Report di out-of-the-box

Tutte le edizioni di Call Quality dashboard offrono un'esperienza che consente di definire le metriche di qualità senza la necessità di creare nuovi report. Una volta elaborati i dati nel back-end, vengono visualizzati i dati relativi alla qualità delle chiamate nei report.

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.
  
### <a name="overview-reports"></a>Report generali

Tutte le edizioni di Call Quality dashboard costituiscono un punto di ingresso di alto livello per le informazioni generali sulla qualità delle chiamate, ma il modo in cui vengono presentate le informazioni in rapporti di riepilogo è diverso dai report dettagliati.  
  
I report di riepilogo includono una visualizzazione semplificata del report di pagina in cui è possibile esplorare e comprendere rapidamente lo stato e le tendenze generali della qualità delle chiamate.

Le quattro schede includono:
  
- **Qualità complessiva delle chiamate** : fornisce informazioni su tutti i flussi, un'aggregazione che mostra le tendenze mensili e quotidiane per
  - Flussi client server
  - Flussi client client
  - Flussi distinti client e client server-client
- **Server-client** : fornisce dettagli per i flussi tra endpoint server e client.
- **Client-client** : fornisce dettagli per i flussi tra due endpoint client.
- **SLA qualità vocale** : fornisce informazioni sulle chiamate incluse nell'SLA sulla qualità vocale di Skype for business online.

> [!NOTE]
> Call Quality dashboard versione 3 funziona con Microsoft teams, Skype for business online e Skype for Business Server. Per usare Call Quality Dashboard con Skype for Business Server 2019, sarà necessario configurare il [connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Vedere [pianificare il connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.

- Qualità delle chiamate per area geografica:

  - Data per area geografica
  - aggregato fino a ora per area geografica
  - posizioni specifiche
  - subnet specifica
  - utente o utenti interessati

- Affidabilità delle chiamate/errore per area geografica:
  - Data per area geografica
  - aggregato fino a ora per area geografica
  - posizioni specifiche
  - subnet specifica
  - utente o utenti interessati

- Valuta la mia chiamata (RMC) per area geografica: da mese per area geografica aggregata fino a posizioni specifiche per gli utenti che prevedono valutazioni RMC basse. Call Quality dashboard v3 include anche feedback Verbatim.
- Helpdesk: disponibile per un utente specifico su chiamate o riunioni P2P oppure per tutti i partecipanti e i dettagli delle chiamate. Consente di identificare i possibili problemi di sistema in base a posizione di rete, dispositivi o firmware.  
- Versioni client: visualizzare la sessione e gli utenti conta per ogni versione del client oppure eseguire il drill-down in nomi utente per ogni versione del client. I filtri predefiniti per il tipo di prodotto e client consentono di mettere a punto le versioni a specifici client.
- Endpoint: Mostra gli endpoint del computer mappati per creare/modellare il PC/Mac. Mostra la qualità aggregata per creazione/modello. I dati di mapping vengono caricati in modo simile alla creazione di dati.

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

#### <a name="inside-test"></a>Test all'interno

Durante l'elaborazione, il back-end Call Quality Dashboard classifica un flusso come *all'interno* o *all'esterno* usando le informazioni sulla creazione, se esiste. Gli endpoint di ogni flusso sono associati a un indirizzo di subnet. Se la subnet si trova nell'elenco delle subnet contrassegnate InsideCorp nelle informazioni di compilazione caricate, viene considerato *all'interno*. Se le informazioni sulla compilazione non sono ancora state caricate, in test vengono sempre classificati i flussi come *all'esterno*.  

> [!NOTE]
> Il test interno per uno scenario server-client considera solo l'endpoint client. Poiché i server sono sempre esterni dal punto di vista dell'utente, questo non viene contabilizzato nel test.
  
#### <a name="wired-vs-wifi"></a>Wi-Fi cablato

Come indicano i nomi, i criteri di classificazione si basano sul tipo di connessioni client. Anche in questo caso, il server è sempre cablato e non è incluso nel calcolo.
  
> [!NOTE]
> Dato un flusso, se uno dei due endpoint è connesso a una rete Wi-Fi, viene classificato come WiFi in Call Quality dashboard.
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selezione dei dati del prodotto da visualizzare nei report

<a name="BKMKProductFilter"></a>

Nei report di riepilogo e posizione avanzata è possibile usare l'elenco a discesa **filtro prodotto** per visualizzare tutti i dati del prodotto, solo i dati di Microsoft teams o solo i dati di Skype for business online.
  
![Screenshot: Mostra le opzioni di controllo del filtro prodotto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In report dettagliati è possibile usare la dimensione **is teams** per filtrare i dati in Microsoft teams o nei dati di Skype for business online.
  
## <a name="upload-tenant-data-information"></a>Caricare informazioni sui dati del tenant

<a name="BKMKTenantDataInformationUpload"></a>

Il dashboard report di riepilogo di Call Quality dashboard include una pagina di **caricamento dei dati del tenant** , a cui si accede selezionando **Carica dati tenant** dal menu impostazioni nell'angolo in alto a destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio:

- Mappa dell'indirizzo IP e delle informazioni geografiche
- Mappa di ogni punto di accesso wireless e del relativo indirizzo MAC
- Una mappa di endpoint da fare/modello/tipo di endpoint e così via.
  
> [!NOTE]
> Le etichette di segnalazione che si caricano in Call Quality dashboard verranno gestite come *dati di supporto* sotto il contratto per Office 365, incluse le eventuali informazioni che altrimenti verrebbero considerate dati *dei clienti* o *dati personali*. Non includere dati che non si desidera concedere a Microsoft come *dati di supporto*, queste informazioni saranno visibili agli ingegneri Microsoft per scopi di supporto.

![Screenshot: Mostra i dati del tenant di Call Quality dashboard](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Nella pagina **caricamento dati tenant** usare il menu a discesa per scegliere un tipo di file di dati da caricare. Il tipo di dati del file denota il contenuto del file, ad esempio "Building" fa riferimento al mapping dell'indirizzo IP e dell'edificio e ad altre informazioni geografiche, "endpoint" si riferisce al mapping del nome dell'endpoint alle informazioni sul tipo o sul modello o sul testo dell'endpoint. Attualmente Call Quality dashboard supporta i tipi di dati "Building" e "endpoint" per cqd.teams.microsoft.com (in anteprima e non ancora ufficialmente disponibile), cqd.lync.com supporta solo il tipo di dati "Building".



2. Dopo aver selezionato il tipo di dati file, fare clic su **Sfoglia** per scegliere un file di dati.

   - Un file di dati deve essere un file con estensione TSV (valori separati da tabulazioni) o un file CSV (valore delimitato da virgole). Con un file CSV, qualsiasi campo che contiene una virgola deve essere racchiuso tra virgolette o avere la virgola rimossa. Ad esempio, se il nome dell'edificio è NY, NY, immettere "NY, NY" nel file CSV.
   - Il file di dati non deve essere maggiore di 50 MB.
   - I file caricati in cqd.teams.microsoft.com hanno un limite di riga espanso di 1 milione per semplificare le prestazioni delle query. Questo limite si applica anche a Call Quality dashboard V2 in<span></span>Call Quality dashboard.<span></span>Lync. com.
   - Per ogni file di dati, ogni colonna del file deve corrispondere a un tipo di dati predefinito, descritto più avanti in questo argomento.
3. Specificare quindi una **Data di inizio** e, facoltativamente, **specificare una data di fine**.
4. Infine, seleziona **carica** per caricare il file nel server Call Quality dashboard.
    Prima che il file venga caricato, viene prima convalidato. Una volta convalidato, viene archiviato in un BLOB di Azure. Se la convalida non riesce o il file non viene archiviato in un BLOB di Azure, un messaggio di errore richiede una correzione al file. L'immagine seguente mostra un errore di esempio con un numero errato di colonne nel file di dati.

     ![Screenshot: Mostra un errore di convalida upload](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se non si verificano errori durante la convalida, il caricamento del file viene eseguito correttamente. È quindi possibile **visualizzare il file** di dati caricati nella tabella uploads. Nella parte inferiore della pagina viene visualizzato anche un elenco completo di tutti i file caricati per il tenant corrente.
    Ogni record Mostra un file di dati del tenant caricato, con il tipo di file, l'ora dell'ultimo aggiornamento, il periodo di tempo, la descrizione, un'icona di rimozione e un'icona di download. Per rimuovere un file, selezionare l'icona del cestino nella tabella. Per scaricare un file, selezionare l'icona download nella colonna **Scarica** della tabella.

     ![Screenshot: Mostra la tabella uploads](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Se si sceglie di usare più file di dati dell'edificio o più file di dati dell'endpoint, alcuni report generano più lentamente.

### <a name="tenant-data-file-format-and-structure"></a>Formato e struttura del file di dati tenant

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Creazione di file di dati

Call Quality dashboard usa un file di dati dell'edificio, che consente di ottenere dettagli utili per le chiamate. La colonna subnet viene derivata espandendo la colonna Network + NetworkRange, quindi unendo la colonna subnet alla prima subnet o alla seconda colonna subnet del record di chiamata per visualizzare le informazioni su edifici, città, Paesi o aree geografiche. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

È possibile scaricare un modello di esempio [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)
  
- Il file deve essere un file TSV (le colonne sono separate da una TABULAzione) o un file CSV (le colonne sono separate da una virgola).
- Il file di dati non include una riga di intestazione di tabella. La prima riga del file di dati dovrebbe essere dati reali, non etichette di intestazione come "rete".
- I tipi di dati nel file possono essere solo stringa, Integer o Boolean. Per il tipo di dati Integer, il valore deve essere un valore numerico. I valori booleani devono essere 0 o 1.
- Se una colonna usa il tipo di dati stringa, un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore di stringa vuoto.
- Devono essere presenti 14 colonne per ogni riga (o 15 se si vuole aggiungere la colonna facoltativa), ogni colonna deve avere il tipo di dati appropriato e le colonne devono essere nell'ordine elencato nella tabella seguente:

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**Nome campo colonna**|NetworkIP  |NetworkName              |NetworkRange|Buildingname  |OwnershipType| BuildingType  |BuildingOfficeType|Città   |ZipCode|Paese|Stato |Area|InsideCorp&dagger;|ExpressRoute&Dagger;|VPN (facoltativo)|
|**Tipo di dati**        | Stringa    | Stringa                  |Numero      | Stringa       | Stringa      | Stringa        |Stringa            |Stringa |Stringa |Stringa |Stringa|Stringa|Boolean   |Boolean     |Boolean|
|**Valore di esempio**    |192.168.1.0|USA/Seattle/SEATTLE-SEA-1| 26         | SEATTLE-SEA-1| Contoso     | Terminazione IT|Ingegneria       |Seattle|98001  |NOI     |WA    |MSUS  | 1        |0           | 0|
|||||||||||||||||

&dagger;Questa impostazione può essere usata per riflettere se la subnet si trova o meno all'interno della rete aziendale. Puoi personalizzare l'utilizzo per altri scopi, se decidi di farlo.

&Dagger;Questa impostazione può essere usata per riflettere se la rete usa Azure ExpressRoute. Puoi personalizzare l'utilizzo per altri scopi, se decidi di farlo.  

**Riga di esempio:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una SuperNet (combinazione di più subnet con un unico prefisso di routing). Tutti gli upload di nuovi edifici verranno controllati per gli intervalli sovrapposti. Se in precedenza è stato caricato un file di costruzione, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e correggere il problema prima del caricamento. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare l'errata mappatura delle subnet agli edifici nei report. Alcune implementazioni VPN non segnalano in modo accurato le informazioni sulla subnet. Si consiglia di aggiungere voci separate per ogni indirizzo della subnet VPN in una rete a 32 bit separata per l'aggiunta di una subnet VPN al file di compilazione, anziché una voce per la subnet. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, dovresti avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32, incluso.
>
> La colonna VPN è facoltativa e sarà impostata su 0.  Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da tale riga verrà espansa completamente in modo che corrisponda a tutti gli indirizzi IP nella subnet.  Usare questo metodo con parsimonia e solo per le subnet VPN poiché l'espansione completa di queste subnet avrà un impatto negativo sugli orari delle query per le query che coinvolgono i dati dell'edificio.

### <a name="endpoint-data-file"></a>File di dati endpoint

Call Quality dashboard usa un file di dati dell'endpoint. I valori della colonna vengono usati nel primo nome dell'endpoint client del record di chiamata o nella seconda colonna nome endpoint client per visualizzare le informazioni sul tipo, il modello o la marca dell'endpoint. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

- Il file deve essere un file TSV (le colonne sono separate da una TABULAzione) o un file CSV (le colonne sono separate da una virgola).
- Il contenuto del file di dati non include le intestazioni di tabella. La prima riga del file di dati dovrebbe essere dati reali, non un'etichetta di intestazione come "EndpointName".
- Tutte e sette le colonne usano solo il tipo di dati stringa. La lunghezza massima consentita è di 64 caratteri.
- Un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore di stringa vuoto.
- EndpointName deve essere univoco, altrimenti il caricamento non riesce. Se è presente una riga duplicata o due righe che usano lo stesso EndpointName, il conflitto causerà l'Unione errata.
- EndpointLabel1, EndpointLabel2 e EndpointLabel3 sono etichette personalizzabili. Possono essere stringhe o valori vuoti, ad esempio "reparto IT designato 2018 laptop" o "asset tag 5678".
- Devono essere presenti sette colonne per ogni riga e le colonne devono essere nell'ordine seguente:

  **Ordine dei campi:**

EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Riga di esempio:**

' 1409W3534, 123 Manufacturer, Fabrikam Model 123, laptop, IT designed 2018 laptop, asset tag 5678, Purchase 2018

## <a name="migrate-reports-from-previous-version-of-cqd"></a>Eseguire la migrazione dei report da una versione precedente di Call Quality dashboard

Se hai creato report o caricato i file dei dati del tenant (mapping) in Call Quality dashboard per Skypehttps://cqd.lync.com) for business (e vuoi eseguire la migrazione a Call Quality dashboardhttps://cqd.teams.microsoft.com)for teams, ecco come:

1.  Passare a [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) e passare al set di report che si vuole esportare. 
2.  Posizionare il puntatore del mouse sul report e, nel "..." scegliere **Esporta albero report**. Salvare il file di esportazione.
3.  [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/) Passare al percorso in cui si vogliono importare i report.
4.  Dai collegamenti a sinistra fare clic su **Importa** e selezionare il file esportato. 
5.  Dopo aver importato i report, verrà visualizzato questo messaggio: "il rapporto di importazione è riuscito. Il nuovo report è stato aggiunto alla fine del set di report. 


## <a name="create-custom-detailed-reports"></a>Creare report dettagliati personalizzati

Se si vuole creare un report specifico che si concentri su una dimensione dei dati in modo che i report dettagliati forniti non siano disponibili, creare un report personalizzato.

Nell'elenco a discesa dei report nella parte superiore dello schermo visualizzato all'accesso \(la schermata **** \) Riepilogo report selezionare **report dettagliati** e quindi **nuovo** d fare clic su "modifica" nel menu azione di un report per visualizzare l'editor di query. Ogni report viene supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di query consente di modificare queste query e le opzioni di visualizzazione del report. Quando si apre l'editor di query per un nuovo report, viene visualizzato un elemento simile a questa schermata:

![Modificare nuovi report](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Le dimensioni, le misure e i filtri vengono scelti nel riquadro sinistro. Fare clic sul pulsante "più" accanto a un titolo per aprire la finestra di dialogo in cui è possibile aggiungere una dimensione, una misura o un filtro e selezionare la casella corrispondente. Se si modifica un report esistente, è possibile deselezionare i valori esistenti per rimuoverli. Per informazioni dettagliate, vedere [dimensioni e misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).
2. Le opzioni per la personalizzazione del grafico sono visualizzate nella parte superiore.
3. Un'anteprima del report è disponibile nell'editor di query.
4. Un nome di report dettagliato e una descrizione possono essere creati con la casella Modifica nella parte inferiore.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché Call Quality dashboard contrassegnare una chiamata come "buona" Se uno o più partecipanti alla riunione hanno avuto una cattiva esperienza?

Vedere le regole usate da Call Quality dashboard per la [classificazione del flusso](stream-classification-in-call-quality-dashboard.md).
 
Per i flussi audio, tutti e cinque i classificatori, calcolati per la media in base alla lunghezza della chiamata, potrebbero essere tutti all'interno dei parametri "buoni". Ciò non significa che gli utenti non abbiano sperimentato qualcosa che ha contribuito a una disattivazione audio, statica o glitch. 

Per determinare se si trattava di un problema di rete, esaminare il delta tra i valori medi per la sessione e i valori max. I valori max sono i massimi rilevati e segnalati durante la sessione.
 
Ecco un esempio di come risolvere questo problema. Supponiamo che tu prenda una traccia di rete durante una chiamata e i primi 20 minuti non ci siano pacchetti persi, ma allora hai una lacuna di 1,5 secondi di pacchetti e quindi buona per il resto della chiamata. La media sta per essere <perdita di pacchetti del 10% (0,1) anche in una analisi di Wireshark Trace RTP. Qual è stata la perdita di pacchetti max? 1,5 sec in un periodo di 5 secondi sarebbe 30% (0,3). Che si verificano nel periodo di campionamento di cinque secondi (forse può essere diviso nel periodo di campionamento)?
 
Se le metriche di rete hanno un aspetto ottimale nei valori medi e Max, cercare altri dati di telemetria: 
- Controllare il rapporto di eventi insufficienti della CPU per verificare se le risorse della CPU rilevate disponibili sono insufficienti e causano scarsa qualità. 
- Il dispositivo audio è in modalità half duplex per evitare di ricevere commenti e suggerimenti a causa dei microfoni da chiudere agli altoparlanti? 
- Controllare il rapporto tra l'evento AEC half duplex Device. È stato il dispositivo glitch o il microfono glitching introducendo rumore o statica a causa di rilasci audio USB quando è collegato a un hub o una stazione di ancoraggio:  
- Verificare le proporzioni degli eventi glitch e microfoni del dispositivo. Il dispositivo funzionava correttamente?  
- Controlla i rapporti di evento non funzionanti del dispositivo di acquisizione e rendering.


Per altre informazioni sulle dimensioni e le misure disponibili in telemetria Call Quality dashboard, leggere [le dimensioni e le misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).

Per il rumore di fondo, controllare il rapporto tra gli eventi per visualizzare la durata del disattivazione dei partecipanti.
 
Creare report dettagliati in Call Quality dashboard e filtrare l'ID riunione per esaminare tutti gli utenti e i flussi di una riunione e aggiungere i campi a cui si è interessati. Un utente che segnala il problema potrebbe non essere quello che ha avuto il problema. Stanno solo segnalando l'esperienza.
 
La telemetria non chiamerà necessariamente il problema, ma può aiutarti a capire meglio dove cercare e informare le tue decisioni. È la rete, il dispositivo, il driver o gli aggiornamenti del firmware, l'uso o l'utente?


### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Perché i dati del report Call Quality dashboard V2 hanno un aspetto diverso rispetto ai dati del report di Call Quality dashboard V3? 

Se vengono visualizzate differenze di dati tra Call Quality dashboard V2 e V3, verificare che il confronto o la convalida dei dati sia stata eseguita su un livello "mele-mele" e su uno stretto, non su un livello aggregato. Se ad esempio si filtrano entrambi i report per i dati client desktop di MSIT ' Building 30', la percentuale di qualità scadente dovrebbe essere uguale tra V2 e V3.

Call Quality dashboard V2 e Call Quality dashboard V3 hanno conteggi totali diversi poiché Call Quality dashboard V3 presenta nuovi scenari non presenti in Call Quality dashboard V2. Il totale di riepilogo o i numeri totali aggregati senza filtri dovrebbero essere diversi.  

Se lo scenario di utilizzo include le chiamate di Skype for Business Server 2019, i dati di Call Quality dashboard V3 includono chiamate Skype bot (operatore automatico, CVI, interfaccia desktop virtuale), eventi dinamici e chiamate PSTN. Call Quality dashboard V2 non usa questi dati. (Call Quality dashboard V3 richiede Skype for Business Server 2019 con il connettore di dati cloud configurato).

Ad esempio, se vengono visualizzati i flussi audio di 200.000 con gli errori di 5000 in un report di riepilogo di Call Quality dashboard V2, non sarebbe insolito vedere i flussi audio di 300.000 con gli errori di 5500 (la differenza può essere dovuta alle chiamate di Skype for Business Server di 2019, alle chiamate CVI, alle chiamate PSTN e così via) in un report di riepilogo di Call Quality dashboard V3.

Per evitare ambiguità tra le differenze impreviste, esaminare più di una scomposizione dei dati complessivi. Filtrare i dati in base a uno o più dei parametri seguenti:

- User Agent Category Pair
- Primo prodotto
- Secondo prodotto

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Altre differenze previste tra Call Quality dashboard V2 e Call Quality dashboard V3

Ci sono diversi miglioramenti di qualità e affidabilità in teams ma non in Skype for business online:

- Riconnessione automatica
- Roaming veloce
- Gestione BW migliorata

Quando si confrontano i dati per questi due servizi:

- Selezionare uno scenario con uno stato di priorità limitato, ad esempio connessioni cablate aziendali, desktop di Windows o una singola area geografica o un edificio.
- Controlla gli intervalli di indirizzi IP per i team MR, TR o MP. Gli intervalli di team sono più recenti di Skype for business online e questo può causare problemi di connettività che coinvolgono i firewall
- Non confrontare i numeri di riepilogo o di primo livello. Questi confronti ti consentiranno di confrontare un grande volume di chiamate Skype for business online su una connessione cablata aziendale a un piccolo volume di chiamate di Team su una rete LTE o privata.
- Attenzione alla distorsione della posizione e alle differenze di popolazione: esistono molti confronti troppo dissimili per essere utili:
  - NOAM: APAC
  - NY: Goa
  - Cablata : WiFi
  - Rete aziendale: rete domestica
  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non è possibile visualizzare EUII in Call Quality dashboard?

Questi ruoli di amministratore possono accedere a Call Quality dashboard, ma non possono visualizzare EUII (informazioni identificabili per gli utenti finali):
- Lettore di report di Office 365
- Specialista supporto comunicazioni Teams

Per altre informazioni sui ruoli che possono accedere a Call Quality dashboard, incluso EUII, vedere [assegnare ruoli per l'accesso a Call Quality dashboard](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché è possibile visualizzare le informazioni di Skype for business in Call Quality dashboard quando è stato filtrato solo per i team?

Quando si filtrano solo i team in report di Call Quality Dashboard (teams = 1), si filtrano tutte le chiamate in cui il *primo endpoint* è teams. Se il *secondo endpoint* è Skype for business, le informazioni verranno visualizzate nel report di Call Quality dashboard.

## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)
 