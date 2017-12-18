---
title: "Attivare e l'utilizzo di Dashboard di qualità di chiamata per Microsoft Teams e Skype for Business Online"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
description: "See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. "
---

# Attivare e l'utilizzo di Dashboard di qualità di chiamata per Microsoft Teams e Skype for Business Online

Informazioni su come configurare l'organizzazione Office 365 per utilizzare il Dashboard di qualità di chiamata per controllare la qualità di chiamata.
  
> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
La chiamata qualità Dashboard (CQD) per Microsoft Teams e Skype for Business online consente di ottenere informazioni di base sulla qualità delle chiamate effettuate servizi Microsoft Teams e Skype for Business. In questo argomento illustra i passaggi che necessari per completare per avviare la raccolta di dati.
  
> [!NOTE]
> I report dettagliati di Call Quality Dashboard sono al momento disponibili come Tech Preview ma per tutti i clienti. 
  
## Ultime modifiche e aggiornamenti.

Le modifiche più recenti per CQD sono i seguenti:
  
- Include i dati Microsoft Teams oltre Skype for Business online dati.
    
- Report riepilogo includono un filtro di prodotti per selezionare tutti i dati, i dati Microsoft Teams o i dati Skype for Business online.
    
Fare riferimento al presente articolo per un elenco di [Dimensioni e misure disponibili nel Dashboard di qualità di chiamata per Teams Microsoft e Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
> [!NOTE]
> Per trovare informazioni sugli aggiornamenti e le modifiche apportati al dashboard, fai clic su **Buone notizie!** nel dashboard. Inoltre, puoi accedere a[Call Quality Dashboard](https://aka.ms/CQDOnline). 
  
## Attivare i report di riepilogo di Microsoft chiamata qualità Dashboard (CQD)

Prima di iniziare con la CQD, sarà necessario attivarlo per l'organizzazione di Office 365.
  
1. Accedere alla propria organizzazione Office 365 utilizzando un account di amministratore e quindi selezionare il riquadro **amministratore** per aprire l'interfaccia di amministrazione.
    
2. Nel riquadro sinistro, in **amministrazione Centra**, selezionare **Skype per le aziende** per aprire l'interfaccia di amministrazione Skype for Business.
    
3. Nell'interfaccia di amministrazione di Skype for Business, selezionare **Strumenti** nel riquadro a sinistra e quindi selezionare **Skype for Business Online i Dashboard qualità di chiamata**.
    
     ![Skype for Business tools](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Nella pagina visualizzata, accedere con l'account di amministratore globale e quindi specificare le credenziali dell'account quando richiesto.
    
     ![CQD Login](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Dopo l'accesso, dopo l'attivazione, il CQD verrà avviata la raccolta ed elaborazione dati.
  
> [!NOTE]
> Potrebbe richiedere un paio di ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report. 
  
## Funzionalità di Call Quality Dashboard per Skype for Business online
<a name="BKMK_FeaturesOfTheCQD"> </a>

I report di riepilogo di Call Quality Dashboard forniscono un sottoinsieme delle funzionalità pianificate per i report dettagliati. Le differenze tra le due edizioni sono riepilogate di seguito.
  
|**Funzionalità**|**Report di riepilogo**|**Report dettagliati**|
|:-----|:-----|:-----|
|Metrica di condivisione applicazioni  <br/> |No  <br/> |Sì  <br/> |
|Supporto per le informazioni di tipo Building dei clienti  <br/> |Sì  <br/> |Sì  <br/> |
|Supporto di analisi drill-down  <br/> |No  <br/> |Sì  <br/> |
|Metriche di affidabilità contenuti multimediali  <br/> |No  <br/> |Sì  <br/> |
|Report di predefiniti  <br/> |Sì  <br/> |Sì  <br/> |
|Report di panoramica  <br/> |Sì  <br/> |Sì  <br/> |
|Set di report a livello di utente  <br/> |No  <br/> |Sì  <br/> |
|Personalizzazione set di report (aggiunta, eliminazione, modifica)  <br/> |No  <br/> |Sì  <br/> |
|Metriche di condivisione dello schermo basata su video  <br/> |No  <br/> |Sì  <br/> |
|Metriche video  <br/> |No  <br/> |Sì  <br/> |
|Quantità di dati disponibile  <br/> |Ultimi sei mesi  <br/> |Ultimi sei mesi  <br/> |
|Dati di Microsoft Teams  <br/> |Sì  <br/> |Sì  <br/> |
   
### Report di predefiniti

Entrambe le versioni di CQD forniscono un'-the-pronte esperienza, che consente di chiama metriche di qualità senza la necessità di creare un nuovo report. Dopo l'elaborazione dei dati in back-end, è possibile avviare la visualizzazione delle chiamate qualità dati nei report.
  
### Report di panoramica

Entrambe le edizioni di Call Quality Dashboard forniscono un punto di accesso generale alle informazioni sulla qualità delle chiamate, ma il modo in cui vengono presentate nei report di riepilogo è diverso rispetto ai report dettagliati.
  
I report di riepilogo forniscono una visualizzazione semplificata in una pagina a schede che consente agli utenti di esplorare e conoscere immediatamente lo stato e le tendenze della qualità delle chiamate.
  
Le quattro schede includono:
  
- **Qualità complessiva chiamata**-fornisce informazioni sulle tutti flussi, ovvero un insieme di flussi di Client Server flussi Client a, nonché Client Server distinto e flussi di Client a, sotto forma di tendenze mese e giorno.
    
- **Server - Client**: fornisce dettagli aggiuntivi sui flussi tra endpoint server e client.
    
- **Client - Client**: fornisce dettagli aggiuntivi sui flussi tra due endpoint client.
    
- **Contratto di servizio qualità vocale**-fornisce informazioni sulle chiamate inclusi in Skype for Business online contratto di servizio qualità vocale.
    
### Scheda Overall Call Quality

Utilizzare i dati in questa scheda per valutare lo stato di qualità di chiamata e tendenze esaminando i conteggi di flusso e le percentuali scarse. La legenda in alto a destra mostra quali colori e gli elementi visivi rappresentano queste metriche.
  
![CQD Data key](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Flussi sono classificati in tre gruppi: riservate, scarsa e ottimale. Sono inoltre calcolati  *che scarsa %*  i valori che consentono di è il rapporto tra flussi classificato come * scarsa*  al numero totale flusso classificati. Poiché *% scarsa = flussi scarsa / (scarsa flussi + flussi buoni) * 100*  , in questo modo influenzato dalla presenza di più flussi *Unclassified*  *% scarsa*  . Per quali viene utilizzato per la classificazione di un flusso come scarsa o utile consultare[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds).
  
Utilizza la scala sulla sinistra per misurare i valori del conteggio delle chiamate.
  
![CQD data count](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilizza la scala a destra per misurare i valori classificati come scarsi.
  
![CQD data per cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Puoi anche ottenere gli effettivi valori numerici posizionando il puntatore del mouse su una barra.
  
> [!NOTE]
> Nell'esempio seguente è stata inviata da un set di dati di esempio molto piccolo e i valori non realistici per una distribuzione effettiva. 
  
![CQD Data numeric](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume complessivo dei flussi è un fattore importante per determinare la rilevanza delle percentuali calcolate per i flussi classificati come scarsi. Minore è il volume complessivo dei flussi, meno affidabili saranno i valori delle percentuali.
  
### Scheda Server Client e Client a schede

Queste due schede forniscono ulteriori dettagli relativi ai flussi che hanno avuto luogo nei rispettivi scenari endpoint-endpoint. In entrambe le schede sono presenti quattro sezioni comprimibili, che rappresentano quattro scenari in cui si verifica il passaggio di flussi multimediali.
  
- Cablata interno
    
- Cablata esterno
    
- Wi-Fi Interno
    
- Wi-Fi esterno
    
#### Inside Test

Durante l'elaborazione, CQD back-end classifica flusso come  *all'interno*  o *esterno*  con informazioni predefiniti, se esistente. I punti finali di ciascun flusso sono associati a un indirizzo di subnet. Se la subnet è presente nell'elenco delle subnet le informazioni sulla creazione caricato, viene considerato all'interno. Se la creazione di informazioni non è ancora stata caricata, quindi all'interno di Test verrà sempre classificare i flussi come *esterno*  . Si noti che all'interno di Test per uno scenario di Server Client considera solo endpoint client. Poiché i server sono sempre di fuori dal punto di vista dell'utente, questo non viene conteggiato del test.
  
#### Wired e wifi

Come indica il nome, si tratta di un criterio di classificazione basato sul tipo di connessioni client. Di nuovo, il server è sempre cablato e non è incluso nel calcolo.
  
> [!NOTE]
> Dato un flusso se uno dei due endpoint è connesso a una rete Wifi, allora viene classificato come Wifi in CQD. 
  
## Selezione di dati di prodotto per visualizzare nei report
<a name="BKMK_FeaturesOfTheCQD"> </a>

In riepilogo e percorso Enhanced report, è possibile utilizzare l'elenco a discesa **Filtro prodotti** per visualizzare tutti i dati di prodotto, solo i dati di Microsoft Teams o solo i dati di Skype for Business online.
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In report dettagliati, è possibile utilizzare la dimensione di team per filtrare i dati per i dati Microsoft Teams o Skype for Business online come parte della definizione del report.
  
## Caricare informazioni di tipo Building
<a name="BKMK_FeaturesOfTheCQD"> </a>

Dashboard di report di riepilogo CQD include una pagina **Di caricamento dei dati Tenant**, che si accede selezionando **Tenant di caricamento dei dati** dal menu Impostazioni nell'angolo superiore destro. Questa pagina viene utilizzata per gli amministratori per caricare le proprie informazioni, ad esempio il mapping di indirizzi IP e informazioni geografiche, il mapping di ogni punto di accesso wireless e il proprio indirizzo MAC, e così via.
  
![CQD Dashboard](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Nella pagina **Di caricamento dei dati Tenant** usare il menu a discesa per scegliere un tipo di file di dati per il caricamento. Il tipo di dati di file indica il contenuto del file (ad esempio, "Creazione" fa riferimento a mapping di indirizzi IP e la creazione e altri dati geografici). Supporto attualmente solo il tipo di dati "Predefinito". Verranno aggiunti alcuni altri tipi di dati con le versioni successive.
    
2. Dopo aver selezionato il tipo di dati di file, fare clic su **Sfoglia** per scegliere un file di dati.
    
  - Il file di dati deve essere un file TSV (valori delimitati da tabulazioni) o un file con estensione CSV (delimitato da virgole). Se tramite un file CSV, qualsiasi campo che contiene un punto e virgola deve contenere virgolette o la virgola rimossi. Ad esempio, se il nome predefinito è NY, NY nel file CSV di esso deve essere immesse come "NY, NY".
    
  - Le dimensioni del file di dati non devono essere superiori a 50 MB.
    
  - Per ogni file di dati, ogni colonna nel file deve corrispondere a un tipo di dati predefinito, descritto più avanti in questo argomento.
    
3. Dopo aver selezionato un file di dati, specificare **la data di inizio** e, facoltativamente, è possibile **specificare una data di fine**.
    
4. Dopo aver selezionato la **data di inizio**, seleziona **Carica** per caricare il file nel server Call Quality Dashboard.
    
    Prima di caricare il file, viene convalidata prima di tutto. Una volta convalidata, questa viene archiviata in un archivio blob Azure. Se si verifica un errore di convalida o il file non si riesce a essere archiviata in un archivio blob Azure, viene visualizzato un messaggio di errore che richiede una correzione per il file. Nella figura seguente mostra un messaggio di errore che potrebbero verificarsi durante il numero di colonne nel file di dati non è corretto.
    
     ![CQD Example upload validation error](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se non si verificano errori durante la convalida, il caricamento del file avrà esito positivo. Sarà quindi possibile visualizzare il file di dati caricato nella tabella **Caricamenti personali**, che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.
    
    Ogni record Mostra un tenant caricati dati file con tipo di file, ora ultimo aggiornamento, periodo di tempo, descrizione, rimuovere e un'icona di download. Per rimuovere un file, selezionare l'icona di bin nel Cestino della tabella. Per scaricare un file, selezionare l'icona di download nella colonna **Download** della tabella.
    
     ![CQD My Uploads table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### Formato del file di dati tenant e struttura del file di dati di tipo Building
<a name="BKMK_TenantDataFile"> </a>

Il formato del file di dati da caricare deve soddisfare i seguenti requisiti per superare il controllo di convalida prima del caricamento.
  
- Il file deve essere un file TSV, vale a dire colonne sono separate da una scheda, in ogni riga o un file CSV con tutte le colonne separate da una virgola.
    
- Il contenuto del file di dati non include le intestazioni di tabella. Che indica che la prima riga del file di dati deve essere dati reali, senza intestazioni come "Rete", e così via.
    
- Per ogni colonna, il tipo di dati può essere solo stringa, numero o Bool. Se numero è il valore deve essere un valore numerico. Se è Bool, il valore deve essere uguale a 0 o 1.
    
- Per ogni colonna, se il tipo di dati è stringa, i dati possono essere vuoti (ma comunque devono essere separati da un appropriato delimitato (ad esempio una scheda o punto e virgola). Questo assegna semplicemente il campo un valore stringa vuota.
    
- Devono essere presenti 14 colonne per ogni riga. Ciascuna colonna deve avere il tipo di dati indicato di seguito e le colonne devono essere nell'ordine in cui sono elencate nella tabella seguente.
    
|**Nome di colonna**|**Tipo di dati**|**Esempio**|
|:-----|:-----|:-----|
|Rete  <br/> |Stringa  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |Stringa  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Numero  <br/> |26  <br/> |
|BuildingName  <br/> |Stringa  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |Stringa  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Stringa  <br/> |IT Termination  <br/> |
|BuildingOfficeType  <br/> |Stringa  <br/> |Engineering  <br/> |
|City  <br/> |Stringa  <br/> |Seattle  <br/> |
|ZipCode  <br/> |Stringa  <br/> |98001  <br/> |
|Country  <br/> |Stringa  <br/> |US  <br/> |
|State  <br/> |Stringa  <br/> |WA  <br/> |
|Region  <br/> |Stringa  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Booleano  <br/> |1  <br/> |
|ExpressRoute  <br/> |Booleano  <br/> |0  <br/> |
   
> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi upload di tipo Building verranno controllati per verificare se vi sono sovrapposizioni di intervalli. Se in precedenza hai inviato un file di tipo Building, scarica il file corrente e caricalo nuovamente per individuare eventuali sovrapposizioni e correggere il problema prima del nuovo upload. Una sovrapposizione nei file caricati in precedenza può portare a una mappatura errata tra le subnet e gli edifici nei report. > Alcune implementazioni VPN non restituire accuratamente le informazioni di subnet. È consigliabile che durante l'aggiunta di una subnet VPN per il file building, invece di una voce per subnet, vengono aggiunte voci separate per ciascun indirizzo subnet VPN come una rete separata versione a 32 bit. Ogni riga può includere gli stessi metadati predefiniti. Ad esempio, invece di una riga per 172.16.18.0/24, è necessario disporre di 256 righe, con una riga per ogni indirizzo tra 172.16.18.0/32 e 172.16.18.255/32, estremi inclusi. 
  
## Selezione del tipo di contenuto multimediale nei report dettagliati
<a name="BKMK_FeaturesOfTheCQD"> </a>

Report dettagliati supporta esamina l'affidabilità di qualità ed elementi multimediali per audio, video, la condivisione delle applicazioni e basato su video tipi di elementi multimediali condivisione dello schermo. Dimensioni, misure e i filtri specifici per un tipo di oggetto multimediale singola avere "Audio", "Video", "AppSharing" o "VBSS" come prefisso.
  
![Call Quality Dashboard Dimensions.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Se si desidera visualizzare le dimensioni e misure per un tipo di oggetto multimediale singola, la nuova dimensione MediaType e filtro potrebbe essere necessari. Ad esempio, per un report che mostra che il numero totale di sessioni conta tra diversi tipi di supporti, includere la dimensione MediaType.
  
![Call Quality Dashboard Total Stream Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

