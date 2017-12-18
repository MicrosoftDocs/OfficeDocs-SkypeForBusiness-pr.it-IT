---
title: "Report attività peer-to-peer in Skype for Business"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_UI_Elements
ms.custom: Adm_O365_FullSet
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713

description: "Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. "
---

# Report attività peer-to-peer in Skype for Business

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Nuovo dashboard di Office 365 **report** Mostra la panoramica di attività per i prodotti Office 365 all'interno dell'organizzazione. Consente di eseguire il drill-i report di livello singolo prodotto per conferire maggiore comprendere le attività all'interno di ogni prodotto. Ad esempio, è possibile utilizzare il report di **Skype per attività di Business - to-peer** per visualizzare gli utenti utilizzano quantità messaggistica Istantanea, audio, video e di applicazioni condivisione e il trasferimento di file. Vedere[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## Come ottenere il report Attività peer-to-peer Skype for Business

1. Passare all'interfaccia ** di amministrazione di Office 365** > **report** > **l'uso**.
    
2. Nella pagina **utilizzo** fare clic su **Skype per attività di Business - to-peer** in **Selezionare un elenco di report** sulla sinistra. Oppure fare clic su widget **Skype per attività** e quindi fare clic su **Skype for Business - to-peer activity** presenti nell'elenco di **Skype per attività**.
    
     ![Skype peer to peer menu selected](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei report su prodotti e attività illustrati in questo articolo potrebbero non essere disponibili. 
  
## Interpretare il report Attività peer-to-peer Skype for Business

È possibile consultare il report Attività peer-to-peer Skype for Business leggendo i grafici **Attività**, **Utenti** e **Minuti**.
  
![Skype peer to peer report with callouts.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
|||
|:-----|:-----|
|**1** <br/> |Il report **Attività peer-to-peer Skype for Business** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. <br/> |
|**2** <br/> |Ogni report è una data per quando è stato generato il report. I report riflettono in genere una latenza 24 - 48 ore dall'ora dell'attività.  <br/> |
|**3** <br/> |Usare i dati del grafico interattive del grafico di **attività** per comprendere le tendenze di utilizzo e per visualizzare il numero totale di sessioni per tipo di sessione gestiti all'interno dell'organizzazione. Verrà visualizzato è il numero totale e tipi di sessioni di **messaggistica Istantanea**, **Audio**, **Video**, **la condivisione delle applicazioni** e **trasferimento di File** all'interno dell'organizzazione. <br/> |
|**4** <br/> |Usare i dati del grafico interattive del grafico di **utenti** per comprendere le tendenze di utilizzo e per visualizzare il numero di utenti univoci che fanno parte di attività peer-to-peer utilizzate all'interno dell'organizzazione. È il numero totale di utenti, nonché i tipi di **messaggistica Istantanea**, **Audio**, **Video**, **la condivisione delle applicazioni** e **trasferimento di File** verrà visualizzato in sessioni peer-to-peer. <br/> |
|**5** <br/> |Utilizzare i dati del grafico interattivi del grafico **minuti** per comprendere le tendenze di utilizzo e per visualizzare il numero di minuti che sono utilizzati dagli utenti sulle attività peer-to-peer uso di audio e video. Verrà visualizzato è il numero totale di minuti di **Audio** e **Video** che viene utilizzata per le sessioni peer-to-peer. <br/> |
|**6** <br/> | Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale). <br/>  Nel grafico **Attività**, l'asse Y è il numero totale di sessioni di messaggistica istantanea, audio, video, condivisione applicazioni e trasferimento file tenute da utenti della propria organizzazione.  <br/>  Nel grafico attività **utente**, l'asse Y è gli utenti di numero totali di messaggistica Istantanea, audio, video e di applicazioni condivisione e il trasferimento delle sessioni di file.  <br/>  Nel grafico **Minuti**, l'asse Y è il numero totale di minuti di usati dagli utenti della propria organizzazione nelle sessioni peer-to-peer audio e video.  <br/>  L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. <br/> |
|**7** <br/> |È possibile filtrare la serie visualizzate nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **attività** fare clic o toccare **messaggistica Istantanea**, **Audio**, **Video**, **la condivisione delle applicazioni** e **trasferimento di File** per visualizzare solo le informazioni relative a ciascuno di essi. La modifica di questa selezione non modificare le informazioni nella tabella. <br/> |
|**8** <br/> | La tabella illustra tutte le attività peer-to-peer per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le loro attività peer-to-peer. È possibile aggiungere ulteriori colonne dalla tabella. <br/> **Nome utente** è il nome dell'utente. <br/> **Eliminato** indica che la licenza dell'utente è stata rimossa. <br/> > [!NOTE]>  L'attività per un utente eliminato continuerà a essere visualizzata in un report se durante il periodo di tempo selezionato all'utente è stata assegnata una licenza. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.          **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa. <br/> **Data di ultima attività (UTC)** è la data dell'ultima attività (UTC) per quell'utente. <br/> **Messaggistica istantanea** indica il numero totale di sessioni peer-to-peer che l'utente ha utilizzato. <br/> **Audio** indica il numero totale di sessioni peer-to-peer che hanno utilizzato l'audio. <br/> **Video** indica il numero totale di sessioni peer-to-peer che hanno utilizzato il video. <br/> **Condivisione applicazioni** mostra il numero totale di sessioni di condivisione applicazioni peer-to-peer. <br/> **Trasferimento file** mostra il numero totale di sessioni di trasferimento file peer-to-peer. <br/> **Minuti audio** mostra il numero totale di minuti audio utilizzati in tutta l'organizzazione. <br/> **Minuti video** mostra il numero totale di minuti video utilizzati in tutta l'organizzazione. <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i dettagli dell'utente nei report** in[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).  <br/> |
|**9** <br/> |È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|**10** <br/> |![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)Fare clic o toccare l'icona di **colonne** in una delle colonne da aggiungere o rimuovere colonne dal report.           <br/> |
   
## Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](skype-for-business-activity-report.md) È possibile vedere quanto gli utenti utilizzano peer-to-peer, l'organizzazione e partecipato sessioni di conferenza.
    
- [Skype per report di utilizzo del dispositivo Business](skype-for-business-device-usage-report.md) È possibile per visualizzare i dispositivi inclusi sistemi operativi basati su Windows e dispositivi mobili con Skype for Business app installate e usano per messaggistica Istantanea e le riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](skype-for-business-conference-organizer-activity-report.md) È possibile vedere quanto gli utenti sono organizzare conferenze che utilizzano messaggistica Istantanea, audio/video, condivisione, Web, festa - 3 dial-in e all'esterno di applicazioni e dial-in e all'esterno a Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](skype-for-business-conference-participant-activity-report.md) È possibile vedere quante messaggistica Istantanea, audio/video, la condivisione di applicazioni, Web ed e le conferenze telefoniche con accesso esterno dial-in e all'esterno sono vengano partecipate.
    
- [Skype per gli utenti aziendali bloccati report](skype-for-business-users-blocked-report.md) È possibile visualizzare gli utenti dell'organizzazione che sono stati bloccati da effettuare chiamate PSTN.
    
- [Report di utilizzo PSTN di Skype for Business](skype-for-business-pstn-usage-report.md) È possibile visualizzare il numero di minuti trascorso in chiamate in ingresso/uscita e dei costi per le chiamate.
    
- [Skype per gli utenti aziendali bloccati report](skype-for-business-users-blocked-report.md) mostra i dettagli del supporto usato, della durata della sessione, del client usato e dell'URL di conferenza.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

