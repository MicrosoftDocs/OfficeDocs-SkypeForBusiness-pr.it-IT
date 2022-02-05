---
title: Rapporto riepilogativo qualità multimediale Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Riepilogo: informazioni sul Rapporto riepilogativo qualità multimediale in Skype for Business Server.'
---

# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Rapporto riepilogativo qualità multimediale Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto riepilogativo qualità multimediale in Skype for Business Server.
  
Il Rapporto riepilogativo qualità multimediale è probabilmente la risorsa migliore per analizzare la qualità delle chiamate nell'organizzazione: questo rapporto offre metriche QoE (Quality of Experience) dettagliate sulle chiamate, suddivise nelle categorie seguenti:
  
- Chiamate peer-to-peer uc (ad esempio, Skype for Business a Skype for Business chiamata)
    
- Sessioni conferenza UC
    
- Sessioni conferenza PSTN
    
- Chiamate PSTN: bypass multimediale
    
- Chiamate PSTN (senza bypass): coda UC
    
- Chiamate PSTN (senza bypass): coda gateway
    
- Altri tipi di chiamata
    
Quando si apre per la prima volta il rapporto, vengono visualizzate informazioni di riepilogo per ognuna delle categorie. Senza uscire dal report, è possibile espandere ogni categoria per esaminare sottocategorie, ad esempio le chiamate effettuate da Office Communicator 2007 R2 a Skype for Business. È quindi possibile eseguire il drill-down in queste sottocategorie per visualizzare dettagli su ogni chiamata effettuata.
  
In Skype for Business Server il Rapporto riepilogativo qualità multimediale suddivide ulteriormente i dati in tre tipi di chiamata: chiamate audio, videochiamate e chiamate di condivisione applicazioni. A ogni tipo di chiamata è associata una sezione del rapporto e un set personalizzato di metriche.
  
Il Rapporto riepilogativo qualità multimediale consente inoltre di applicare filtri in base ai quali confrontare la qualità delle chiamate cablate con quella delle chiamate wireless, di quelle interne con quelle esterne e delle chiamate VPN rispetto a quelle non VPN.
  
## <a name="accessing-the-media-quality-summary-report"></a>Accesso al Rapporto riepilogativo qualità multimediale

Il Rapporto riepilogativo qualità multimediale è accessibile dalla home page Rapporti di monitoraggio. È possibile eseguire il drill-down al [Rapporto elenco chiamate in Skype for Business Server](call-list-report-0.md) facendo clic su una delle metriche seguenti:
  
- Volume chiamata
    
- Percentuale chiamate di livello insufficiente
    
È inoltre possibile accedere al Rapporto distribuzione metriche di qualità multimediale facendo clic sulle metriche di chiamata audio seguenti:
  
- Roundtrip (ms)
    
- Degradazione (MOS)
    
- Perdita di pacchetti
    
- Instabilità (ms)
    
- Rapporto campioni nascosti utilità di ripristino
    
- Rapporto campioni estesi utilità di ripristino
    
- Rapporto campioni compressi utilità di ripristino
    
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il rapporto riepilogativo sulla qualità multimediale, ad esempio, consente di filtrare i dati restituiti in base a fattori come il tipo di accesso (interno o esterno) o il tipo di connessione di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo sulla qualità multimediale.
  
**Filtri per il rapporto riepilogativo sulla qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Tipo di accesso** <br/> | Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Interno <br/>  Esterno <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Cablata <br/>  Wireless <br/> |
|**VPN** <br/> | Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  VPN <br/>  Non VPN <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel rapporto riepilogativo sulla qualità multimediale.
  
**Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate audio**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata/Tipo di endpoint** <br/> |No  <br/> | Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono: <br/>  Chiamate peer-to-peer UC <br/>  Sessioni conferenza UC <br/>  Sessioni conferenza PSTN <br/>  Chiamate PSTN: bypass multimediale <br/>  Chiamate PSTN (senza bypass): coda UC <br/>  Chiamate PSTN (senza bypass): coda gateway <br/>  Altri tipi di chiamata <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate per ciascun tipo.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |No  <br/> |Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.  <br/> |
|**Volume chiamata (chiamata wireless)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione wireless.  <br/> |
|**Volume chiamata (chiamata VPN)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione VPN.  <br/> |
|**Volume chiamata (chiamata esterna)** <br/> |No  <br/> |Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.  <br/> |
|**Roundtrip (ms)** <br/> |No  <br/> |Tempo medio di roundtrip, in millisecondi, necessario per un pacchetto RTP (Real-Time Transport Protocol) per viaggiare fino a un altro endpoint e tornare indietro. Un roundtrip di 100 millisecondi o meno è considerato di qualità accettabile.  <br/> Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.  <br/> |
|**Degradazione (MOS)** <br/> |No  <br/> |Degradazione MOS (Mean Opinion Score) media sperimentata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Skype for Business Server un set di algoritmi prevede il modo in cui gli utenti avrebbero valutato una chiamata.  <br/> Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.  <br/> |
|**Perdita di pacchetti** <br/> |No  <br/> |Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video in Internet, non raggiungono la destinazione. Valori di perdita alti sono in genere dovuti a congestione, disponibilità di una larghezza di banda troppo ridotta, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.  <br/> |
|**Instabilità (ms)** <br/> |No  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni nascosti utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni estesi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.  <br/> |
|**Rapporto campioni compressi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.  <br/> |
   
**Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle videochiamate**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata/Tipo di endpoint** <br/> |No  <br/> | Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono: <br/>  Chiamate peer-to-peer UC <br/>  Sessioni conferenza UC <br/>  Sessioni conferenza PSTN <br/>  Chiamate PSTN: bypass multimediale <br/>  Chiamate PSTN (senza bypass): coda UC <br/>  Chiamate PSTN (senza bypass): coda gateway <br/>  Altri tipi di chiamata <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate per ciascun tipo.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |No  <br/> |Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.  <br/> |
|**Volume chiamata (chiamata wireless)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione wireless.  <br/> |
|**Volume chiamata (chiamata VPN)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione VPN.  <br/> |
|**Volume chiamata (chiamata esterna)** <br/> |No  <br/> |Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.  <br/> |
|**Velocità media in bit (Kbit/s)** <br/> |No  <br/> |Velocità in bit video media (in kilobit al secondo).  <br/> |
|**Bassa velocità in bit (%)** <br/> |No  <br/> |Percentuale della chiamata con velocità in bit bassa.  <br/> |
|**Perdita di pacchetti in uscita** <br/> |No  <br/> |Perdita di pacchetti RTP (Real-Time Transport Protocol) in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.  <br/> |
|**% fotogrammi bloccati** <br/> |No  <br/> |Percentuale di fotogrammi "bloccati". In un fotogramma bloccato, il video smette di avanzare mentre la parte audio della chiamata prosegue.  <br/> |
|**Frequenza media dei fotogrammi in uscita** <br/> |No  <br/> |Frequenza media dei fotogrammi per le trasmissioni in uscita durante la chiamata.  <br/> |
|**Frequenza media dei fotogrammi in ingresso** <br/> |No  <br/> |Frequenza media dei fotogrammi per le trasmissioni in arrivo durante la chiamata.  <br/> |
|**Bassa frequenza dei fotogrammi in ingresso (%)** <br/> |No  <br/> |Percentuale della chiamata con velocità in bit bassa per il video in arrivo.  <br/> |
|**Integrità client (%)** <br/> ||Indica l'integrità relativa del dispositivo client durante la chiamata.  <br/> |
   
**Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate di condivisione applicazioni**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata/Tipo di endpoint** <br/> |No  <br/> | Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono: <br/>  Chiamate peer-to-peer UC <br/>  Sessioni conferenza UC <br/>  Sessioni conferenza PSTN <br/>  Chiamate PSTN: bypass multimediale <br/>  Chiamate PSTN (senza bypass): coda UC <br/>  Chiamate PSTN (senza bypass): coda gateway <br/>  Altri tipi di chiamata <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate per ciascun tipo.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |No  <br/> |Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.  <br/> |
|**Volume chiamata (chiamata wireless)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione wireless.  <br/> |
|**Volume chiamata (chiamata VPN)** <br/> |No  <br/> |Numero totale di chiamate eseguite tramite una connessione VPN.  <br/> |
|**Volume chiamata (chiamata esterna)** <br/> |No  <br/> |Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.  <br/> |
|**Instabilità (ms)** <br/> |No  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Media unidirezionale relativa** <br/> |No  <br/> |Media unidirezionale relativa tra due endpoint multimediali. Si tratta di una misurazione della latenza a singolo hop.  <br/> |
|**Latenza media elaborazione sezioni RDP** <br/> |No  <br/> |Latenza media dell'elaborazione delle sezioni RDP in AS Conferencing Server per la durata della sessione di visualizzazione. Una media elevata riflette un ritardo più lungo nell'esperienza di visualizzazione e include la latenza di rete. In un server per conferenze sovraccaricato possono verificarsi ritardi medi maggiori.  <br/> |
|**% totale sezioni danneggiate** <br/> |No  <br/> |Percentuale totale di sezioni RDP danneggiate.  <br/> |
   

