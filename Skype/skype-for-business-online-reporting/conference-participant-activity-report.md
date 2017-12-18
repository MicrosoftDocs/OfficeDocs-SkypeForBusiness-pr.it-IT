---
title: "Report attività partecipante di conferenze in Skype for Business"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_ReportsS4BPartActivity
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_UI_Elements
ms.custom: Adm_O365_FullSet
ms.assetid: c3c89995-65dd-4715-9e38-bb244c742c6b

description: "Learn how to get the Skype for Business Conference Participant Activity report, and how to interpret and customize it. "
---

# Report attività partecipante di conferenze in Skype for Business

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Gli amministratori di Office 365, il nuovo dashboard **report** sono visualizzati i dati sull'utilizzo dei prodotti Office 365 all'interno dell'organizzazione. È possibile utilizzare il report di **Skype per attività dei partecipanti conferenza** per vedere quante la messaggistica Istantanea, audio/video, condivisione, di applicazioni Web ed e conferenze dial-in e all'esterno sono vengano Partecipate dagli utenti dell'organizzazione.
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività di conferenza in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## Come ottenere i report sui partecipanti alle conferenze di Skype for Business

1. Passare all'interfaccia ** di amministrazione di Office 365** > **report** > **l'uso**.
    
2. Nella pagina **utilizzo** fare clic su **Skype per attività dei partecipanti conferenza** in **Selezionare un elenco di report** sulla sinistra. O, fare clic su widget **Skype per attività** e quindi fare clic su **Skype per attività dei partecipanti conferenza** presenti nell'elenco di **Skype per attività**.
    
     ![Skype conference participant activity menu item selected](../images/4033059e-dd2d-447d-8ee8-7515a5c26672.PNG)
  
    > [!IMPORTANT]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei report su prodotti e attività illustrati in questo articolo potrebbero non essere disponibili. 
  
## Interpretazione del report Attività partecipante di conferenze in Skype for Business

![Skype conference participant activity report](../images/a5fb6a3f-d8bc-402e-850e-87a75fbc2546.PNG)
  
|||
|:-----|:-----|
|**1** <br/> |Il report **Attività partecipante di conferenze in Skype for Business** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. <br/> |
|**2** <br/> |Ogni report è una data per quando è stato generato il report. I report riflettono in genere una latenza 24 - 48 ore dall'ora dell'attività.  <br/> |
|**3** <br/> |Usare i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero totale di conferenze che hanno avuto partecipanti e il tipo di conferenze tenute nella propria organizzazione. Mostra il numero totale e il tipo di conferenze di **Messaggistica istantanea**, **Audio/video**, **Condivisione applicazioni**, **Web** e **Accesso esterno - terze parti** a cui hanno partecipato membri della propria organizzazione. <br/> |
|**4** <br/> | Usare i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero totale di utenti unici che hanno partecipato a conferenze tenute nella propria organizzazione. Mostra il numero totale di utenti e il tipo di conferenze di **Messaggistica istantanea**, **Audio/video**, **Condivisione applicazioni**, **Web** e **Accesso esterno - terze parti** organizzate. <br/> |
|**5** <br/> |Utilizzare i dati del grafico interattive del grafico **minuti** per comprendere le tendenze di utilizzo e per visualizzare il numero di minuti che vengono utilizzati dagli utenti quando consentono di organizzare una conferenza con audio/video e dial-in ingresso e in uscita a Microsoft come le conferenze audio provider. Verrà visualizzato è il numero totale di minuti di **Audio/video** utilizzati durante le conferenze coinvolti nella. <br/> |
|**6** <br/> |È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **Attività** toccare o fare clic su **Messaggistica istantanea**, **Audio/video**, **Condivisione applicazioni**, **Web** e **Accesso esterno - terze parti** per visualizzare solo le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. <br/> |
|**7** <br/> | Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale). <br/>  Nel grafico **Attività**, l'asse Y è il numero totale di conferenze di Messaggistica istantanea, Audio/video, Condivisione applicazioni, Web e Accesso esterno - terze parti a cui hanno partecipato membri della propria organizzazione.  <br/>  Nel grafico **Utenti**, l'asse Y è il numero totale di utenti che hanno tenuto conferenze di Messaggistica istantanea, Audio/video, Condivisione applicazioni, Web e Accesso esterno - terze parti a cui hanno partecipato membri della propria organizzazione.  <br/>  Nel grafico **Minuti**, l'asse Y è il numero totale di minuti di audio/video usati in conferenze a cui hanno partecipato membri della propria organizzazione.  <br/>  L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. <br/> |
|**8** <br/> | La tabella illustra le conferenze in cui hanno partecipato gli utenti, suddivise per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le conferenze a cui hanno partecipato. È possibile aggiungere altre colonne alla tabella. <br/> **Nome utente** è il nome dell'utente. <br/> **Eliminato** indica che la licenza dell'utente è stata rimossa. <br/> > [!NOTE]>  L'attività per un utente eliminato continuerà a essere visualizzata in un report se durante il periodo di tempo selezionato all'utente è stata assegnata una licenza. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.          **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa. <br/> **Data di ultima attività (UTC)** è la data dell'ultima attività (UTC) per quell'utente. <br/> **Messaggistica istantanea** mostra il numero totale di conferenze di messaggistica istantanea a cui l'utente ha partecipato. <br/> **Audio/video** mostra il numero totale di conferenze audio/video a cui l'utente ha partecipato. <br/> **Condivisione applicazioni** mostra il numero totale di conferenze di condivisione applicazioni a cui l'utente ha partecipato. <br/> **Web** mostra il numero totale di conferenze web a cui l'utente ha partecipato. <br/> **Accesso esterno - terze parti** mostra il numero totale di conferenze in accesso esterno organizzate che usano un provider di servizi di audioconferenza di terza parte. <br/> **Minuti audio/video** mostra il numero totale di minuti usati quando l'utente ha partecipato a conferenze che utilizzano audio/video. <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i dettagli dell'utente nei report** in[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).  <br/> |
|**9** <br/> |È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|**10** <br/> |Toccare o fare clic su **Colonne** per aggiungere o rimuovere colonne dal report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)|
   
## Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](skype-for-business-activity-report.md) È possibile vedere quanto gli utenti utilizzano peer-to-peer, l'organizzazione e partecipato sessioni di conferenza.
    
- [Skype per report di utilizzo del dispositivo Business](skype-for-business-device-usage-report.md) È possibile per visualizzare i dispositivi inclusi sistemi operativi basati su Windows e dispositivi mobili con Skype for Business app installate e usano per messaggistica Istantanea e le riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](skype-for-business-conference-organizer-activity-report.md) È possibile vedere quanto gli utenti sono organizzare conferenze che utilizzano messaggistica Istantanea, audio/video, condivisione, Web, festa - 3 dial-in e all'esterno di applicazioni e dial-in e all'esterno a Microsoft.
    
- [Report attività peer-to-peer in Skype for Business](skype-for-business-peer-to-peer-activity-report.md) È possibile vedere quanto gli utenti utilizzano messaggistica Istantanea, audio/video, la condivisione delle applicazioni e trasferimento di file.
    
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

