---
title: Attivazione e l'utilizzo del Dashboard di qualità delle chiamate
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Informazioni su come attivare e utilizzare il Skype per Business Online i Dashboard qualità delle chiamate e ottenere rapporti di riepilogo di qualità delle chiamate. '
ms.openlocfilehash: 856cf70085bbd0c7ca5cd5e253aec991bb970d62
ms.sourcegitcommit: dfcdb18d0eb3205ef9180f048674f586aac92de0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570317"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Attivazione e l'utilizzo del Dashboard di qualità delle chiamate per Microsoft Teams e Skype Business online

Informazioni su come configurare l'organizzazione Office 365 per utilizzare il Dashboard di qualità delle chiamate per monitorare la qualità delle chiamate.
  
La chiamata qualità Dashboard (CQD) per Microsoft Teams e Skype Business online consente di ottenere informazioni di base sulla qualità delle chiamate effettuate con Microsoft Teams e Skype per servizi di Business. In questo argomento vengono descritti i passaggi che necessari per completare per avviare la raccolta dei dati.
  
> [!NOTE]
> CQD dettagliati report sono attualmente disponibile come anteprima tecnica, ma è disponibile per tutti i clienti. 
  
## <a name="latest-changes-and-updates"></a>Aggiornamenti e modifiche più recenti

Le modifiche più recenti per CQD sono i seguenti:
  
- Include i dati di Microsoft Teams oltre Skype per dati Business in linea.
    
- Rapporti di riepilogo includono un filtro prodotti per selezionare tutti i dati, dati di Microsoft Teams o Skype per dati Business in linea.
    
Fare riferimento a questo articolo per un elenco di [dimensioni e misure disponibile nel Dashboard di qualità delle chiamate](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Sono disponibili informazioni sugli aggiornamenti e le modifiche apportate al dashboard facendo clic sul collegamento nella **buona notizia!** banner quando viene visualizzato nel dashboard.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Attivare i rapporti di riepilogo di chiamata Microsoft Quality Dashboard (CQD)

Prima di iniziare a utilizzare il CQD, è necessario attivarlo per l'organizzazione Office 365.
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
 
1. Accedere all'organizzazione Office 365 utilizzando un account di amministrazione e quindi selezionare le sezioni di **amministrazione** per aprire l'interfaccia di amministrazione.
    
2. Nel riquadro sinistro, in **Admin Center**, selezionare **Skype for Business** per aprire Skype per interfaccia di amministrazione di Business.
    
3. In Skype per interfaccia di amministrazione di Business, selezionare **Strumenti** nel riquadro sinistro e quindi selezionare **Skype per Business Online i Dashboard qualità delle chiamate**.
    
     ![Skype per gli strumenti di Business](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Nella pagina visualizzata accedere con l'account amministratore globale e quindi specificare le credenziali dell'account quando viene richiesto.
    
     ![Account di accesso CQD](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Dopo l'accesso dopo l'attivazione, la CQD verrà avviata la raccolti e l'elaborazione dei dati.
  
> [!NOTE]
> Potrebbe richiedere alcune ore per l'elaborazione di dati sufficiente per visualizzare i risultati significativi nei report. 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>Funzionalità del Dashboard di qualità chiamata per Skype per le aziende Online
<a name="BKMKFeaturesOfTheCQD"> </a>

Rapporti di riepilogo CQD offre un sottoinsieme delle funzionalità pianificate per rapporti dettagliati. Di seguito vengono riepilogate le differenze tra le due edizioni:
  
|**Funzionalità**|**Rapporti di riepilogo**|**Rapporti dettagliati**|
|:-----|:-----|:-----|
|Metrica condivisione applicazioni  <br/> |No  <br/> |Sì  <br/> |
|Creazione di supporto per le informazioni dei clienti  <br/> |Sì  <br/> |Sì  <br/> |
|Supporto per il drill-down analisi  <br/> |No  <br/> |Sì  <br/> |
|Metriche di affidabilità multimediale  <br/> |No  <br/> |Sì  <br/> |
|Report di predefiniti  <br/> |Sì  <br/> |Sì  <br/> |
|Relazioni di riepilogo  <br/> |Sì  <br/> |Sì  <br/> |
|Set di report per utente  <br/> |No  <br/> |Sì  <br/> |
|Rapporto imposta personalizzazione (aggiungere, eliminare, modificare i report)  <br/> |No  <br/> |Sì  <br/> |
|Metriche di condivisione dello schermo basate su video  <br/> |No  <br/> |Sì  <br/> |
|Metriche del video  <br/> |No  <br/> |Sì  <br/> |
|Quantità di dati disponibili  <br/> |Ultimi sei mesi  <br/> |Ultimi sei mesi  <br/> |
|Dati Teams Microsoft  <br/> |Sì  <br/> |Sì  <br/> |
   
### <a name="out-of-the-box-reports"></a>Report di predefiniti

Entrambe le edizioni di CQD offrono un-the-pronte esperienza, avendo chiama metriche di qualità senza la necessità di creare un nuovo report. Dopo l'elaborazione dei dati nel server back-end, è possibile iniziare a ricevere dati sulla qualità delle chiamate nei report.
  
### <a name="overview-reports"></a>Relazioni di riepilogo

Entrambe le edizioni del CQD offrono un punto di ingresso generale per le informazioni sulla qualità chiamata globale, ma il modo in cui vengono presentate informazioni nei report di riepilogo è diverso da quello del report dettagliati.
  
Rapporti di riepilogo offrono una visualizzazione di report pagina schede semplificato che consente agli utenti di individuare rapidamente e acquisire familiarità con lo stato di qualità chiamata generale e le tendenze.
  
Le quattro schede includono:
  
- **Qualità delle chiamate globale** - vengono fornite informazioni su tutti i flussi, ovvero un insieme di flussi di Client a Server e flussi Client a, nonché Client Server separato e flussi di Client a, sotto forma di tendenze giornaliere e mensile.
    
- **Server - Client** - fornisce dettagli aggiuntivi per i flussi tra endpoint Client e Server.
    
- **Client - Client** - fornisce dettagli aggiuntivi per i flussi tra due endpoint Client.
    
- **SLA qualità vocale** - vengono fornite informazioni sulle chiamate incluse nel Skype per Business Online vocale qualità contratto di servizio.
    
### <a name="overall-call-quality-tab"></a>Scheda Generale di qualità delle chiamate

Utilizzare i dati in questa scheda per valutare lo stato di qualità chiamata e le tendenze esaminando i conteggi di flusso e percentuali insufficiente. La legenda nell'angolo superiore destro mostra i colori e gli elementi visivi rappresentano queste metriche.
  
![Chiave CQD dati](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
I flussi sono classificati in tre gruppi: buona scadente e non classificati. Sono disponibili anche calcolata *che scadente %* i valori che consentono di è il rapporto tra i flussi classificata come *insufficiente* per il conteggio totale flusso classificati. Poiché *% scadente = scadente flussi / (scadente flussi + flussi buona) * 100* , in questo modo diventa *insufficiente %* non modifica la presenza con più flussi *Unclassified* . Per viene utilizzato per la classificazione di un oggetto stream come insufficiente o buona, consultare [Le soglie di qualità delle chiamate](https://aka.ms/cqd_quality_thresholds).
  
Utilizzare la scala sinistra per misurare i valori di conteggio flusso.
  
![Numero di dati CQD](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilizzare la scala destra per misurare i valori di una scarsa %.
  
![Dati CQD percentuale](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
È inoltre possibile ottenere i valori numerici effettivi si posiziona il puntatore del mouse su una barra.
  
> [!NOTE]
> L'esempio seguente è un set di dati di un numero ridotto di esempio e i valori non realistici per una distribuzione effettiva. 
  
![Valore numerico CQD dati](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume flusso generale è un fattore importante nel determinare sono le percentuali scadente calcolate come pertinenti. Minore il volume di flussi complessivo, meno affidabile sono i valori di percentuale scadente segnalate.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Scheda Client a server e Client a schede

Queste due schede di fornire informazioni aggiuntive per i flussi che è stata effettuata in scenari relativi endpoint-endpoint. Entrambe le schede sono presenti quattro sezioni comprimibile, che rappresentano quattro scenari in cui verrebbero flusso flussi multimediali.
  
- Cablata interno
    
- Cablata esterno
    
- Inside WiFi
    
- WiFi esterno
    
#### <a name="inside-test"></a>Test interno

Durante l'elaborazione, CQD back-end classifica un flusso *all'interno* o *esterno* utilizzando le informazioni predefinito, se esistente. Endpoint di ciascun flusso sono associati a un indirizzo di subnet. Se la subnet sia presente nell'elenco delle subnet contrassegnato InsideCorp nelle informazioni sulla creazione caricati, viene considerato *interno*. Se la creazione di informazioni non è ancora stata caricata, quindi all'interno di Test verrà sempre classificare i flussi come *esterno*. Si noti che all'interno di Test per uno scenario Client a Server considera solo l'endpoint client. Poiché i server sono sempre di fuori dal punto di vista dell'utente, questo non viene conteggiato nel test.
  
#### <a name="wired-vs-wifi"></a>Cablata e wifi

Come i nomi indicano, si tratta di un criterio di classificazione in base al tipo di connessioni client. Nuovamente, è sempre cablata server e non è incluso nel calcolo.
  
> [!NOTE]
> Dato un oggetto stream, se uno dei due endpoint è connessa a una rete Wifi, quindi viene classificata come Wifi in CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>La selezione dei dati di prodotto vengano visualizzati nel report
<a name="BKMKFeaturesOfTheCQD"> </a>

In riepilogo e posizione Enhanced report, è possibile utilizzare l'elenco a discesa **Filtro prodotti** per visualizzare tutti i dati del prodotto, solo i dati di Microsoft Teams o Skype solo per dati Business in linea.
  
![Schermata che mostra il controllo filtro prodotti con le opzioni per tutti, Microsoft Teams e Skype per le aziende.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Nei rapporti dettagliati, è possibile utilizzare la quota **È team** per filtrare i dati a Microsoft Teams o Skype per dati Business in linea durante la definizione del report.
  
## <a name="upload-building-information"></a>Informazioni di creazione di caricamento
<a name="BKMKFeaturesOfTheCQD"> </a>

Il dashboard i report di riepilogo CQD include una pagina **Di caricamento dei dati Tenant** , accessibile selezionando **Tenant di caricamento dei dati** dal menu Impostazioni nell'angolo superiore destro. Questa pagina viene utilizzata per gli amministratori per caricare le proprie informazioni, ad esempio mapping di indirizzo IP e dati geografici, il mapping di ogni punto di accesso e il suo indirizzo MAC, ecc.
  
![Dashboard CQD](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Nella pagina **Tenant di caricamento dei dati** , utilizzare il menu a discesa scegliere un tipo di file di dati per il caricamento. Il tipo di file di dati indica il contenuto del file (ad esempio, "Building" si riferisce al mapping dell'indirizzo IP e la creazione e altri dati geografici). Supporto attualmente solo il tipo di dati "Predefinito". Alcuni tipi di dati verranno aggiunto con le versioni successive.
    
2. Dopo aver selezionato il tipo di dati di file, fare clic su **Sfoglia** per selezionare un file di dati.
    
  - Il file di dati deve essere un file TSV (valori delimitati da tabulazioni) o un file con estensione CSV (delimitato da virgole). Se si utilizza un file CSV, tutti i campi che contiene una virgola deve essere racchiuso tra virgolette o la virgola rimosso. Ad esempio, se il nome predefinito è NY, NY, nel file CSV di deve essere immesso come "NY, NY".
    
  - Il file di dati deve essere non superiore a 50MB di dimensioni.
    
  - Per ogni file di dati, ogni colonna del file deve corrispondere a un tipo di dati predefinito, descritto più avanti in questo argomento.
    
3. Dopo aver selezionato un file di dati, specificare **la data di inizio** e, facoltativamente, **specificare una data di fine**.
    
4. Dopo aver selezionato **la data di inizio**, selezionare **Carica** per caricare il file nel server CQD.
    
    Prima di caricare il file, viene innanzitutto convalidato. Dopo aver convalidato, viene archiviato in un blob di Azure. Se la convalida ha esito negativo o il file ha esito negativo essere archiviato in un blob di Azure, viene visualizzato un messaggio di errore che richiede una correzione per il file. Nell'immagine seguente viene illustrato l'errore si verifica quando il numero di colonne nel file di dati non è corretto.
    
     ![Errore di convalida per il caricamento di esempio CQD](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se non si verificano errori durante la convalida, il caricamento del file verrà eseguito correttamente. È quindi possibile visualizzare il file di dati caricati nella tabella **i caricamenti** , che viene visualizzato l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.
    
    Ogni record Mostra tenant caricato un file di dati, con il tipo di file, ora ultimo aggiornamento, il periodo di tempo, descrizione, un'icona Rimuovi e un'icona di download. Per rimuovere un file, selezionare l'icona di collocazione Cestino della tabella. Per scaricare un file, selezionare l'icona download nella colonna **Download** della tabella.
    
     ![Tabella CQD le mie online](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>Formato di file di dati tenant e la struttura dei file dei dati predefinito
<a name="BKMKTenantDataFile"> </a>

Il formato del file di dati che carica deve soddisfare le seguenti operazioni per passare il controllo di convalida prima del caricamento.
  
- Il file deve essere un file TSV, pertanto, in ogni riga, le colonne sono separate da una scheda o un file CSV con tutte le colonne separate da una virgola.
    
- Il contenuto del file di dati non include le intestazioni di tabella. Che indica che la prima riga del file di dati devono essere dati reali, le intestazioni non like ", rete" e così via.
    
- Per ogni colonna, il tipo di dati può solo essere Bool, numero o stringa. Se la proprietà numero, il valore deve essere un valore numerico. Se si tratta Bool, il valore deve essere uguale a 0 o 1.
    
- Per ogni colonna, se il tipo di dati stringa, i dati possono essere vuoti (ma ancora devono essere separati da un delimitatore appropriato (ad esempio, una scheda o da virgole). Si assegna semplicemente tale campo un valore stringa vuota.
    
- Deve esistere 14 colonne per ogni riga, ogni colonna deve avere i seguenti dati di tipo e le colonne devono essere nell'ordine indicato nella tabella seguente:
    
|**Nome colonna**|**Tipo di dati**|**Esempio**|
|:-----|:-----|:-----|
|Rete  <br/> |Stringa  <br/> |192.168.1.0  <br/> |
|Risorse NetworkName  <br/> |Stringa  <br/> |USA/Seattle/SEATTLE-mare-1  <br/> |
|NetworkRange  <br/> |Numero  <br/> |26  <br/> |
|BuildingName  <br/> |Stringa  <br/> |SEATTLE-MARE-1  <br/> |
|OwnershipType  <br/> |Stringa  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Stringa  <br/> |Terminazione IT  <br/> |
|BuildingOfficeType  <br/> |Stringa  <br/> |Engineering  <br/> |
|Città  <br/> |Stringa  <br/> |Seattle  <br/> |
|Codice postale  <br/> |Stringa  <br/> |98001  <br/> |
|Paese  <br/> |Stringa  <br/> |STATI UNITI  <br/> |
|Informazioni sullo stato  <br/> |Stringa  <br/> |WA  <br/> |
|Area  <br/> |Stringa  <br/> |MSU  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> L'intervallo di rete può essere utilizzato per rappresentare un supernet (combinazione di più subnet con un prefisso di routing singolo). Tutti i caricamenti di creazione nuovo verranno controllati per gli intervalli che si sovrappongono. Se in precedenza è stato caricato un file predefinito, è necessario scaricare il file corrente e caricare nuovamente per individuare eventuali sovrapposizioni e risolvere il problema prima del caricamento nuovamente. Qualsiasi sovrapposizione tra i file caricati in precedenza può determinare i mapping di un problema di subnet di edifici nei report. Alcune implementazioni VPN non segnalano accuratamente le informazioni sulla subnet. È consigliabile che quando si aggiunge una subnet di rete VPN per il file predefinito, anziché una voce per la subnet, vengono aggiunte voci separate per ogni indirizzo della subnet di rete VPN come una rete a 32 bit separata. Ogni riga può avere gli stessi metadati predefinito. Ad esempio, invece di una riga per 172.16.18.0/24, è necessario disporre 256 righe, con una riga per ogni indirizzo tra 172.16.18.0/32 e 172.16.18.255/32, inclusi. 
  
## <a name="selecting-media-type-in-detailed-reports"></a>La selezione tipo di supporto nel report dettagliati
<a name="BKMKFeaturesOfTheCQD"> </a>

Rapporti dettagliati supportano osservando affidabilità qualità e i contenuti multimediali per audio, video, condivisione di applicazioni e video in tipi di contenuto multimediale condivisione dello schermo. Le dimensioni, le misure e i filtri specifici di un tipo di supporto singolo sono "Audio", "Video", "AppSharing" o "VBSS" come prefisso.
  
![Le dimensioni del Dashboard di qualità delle chiamate.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Se si desidera visualizzare le dimensioni e misure per un tipo multimediale singolo, il filtro e la nuova dimensione MediaType può essere necessari. Ad esempio, per un rapporto che mostra che il numero totale di sessioni conta tra diversi tipi di supporti, includere la dimensione MediaType.
  
![Conteggio totale flusso Dashboard di qualità delle chiamate.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>See also
[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Utilizzare chiamate Analitica per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Chiamata Analitica e Dashboard qualità chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 