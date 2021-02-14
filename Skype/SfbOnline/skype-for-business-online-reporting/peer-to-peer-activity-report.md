---
title: Report attività peer-to-peer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: 3708bff31f0034347c23d67d58cf4be7cb3bc956
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205057"
---
# <a name="peer-to-peer-activity-report"></a>Report attività peer-to-peer

Il **dashboard** Report mostra una panoramica delle attività per tutti i prodotti Microsoft 365 o Office 365 nell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto. Ad esempio, è possibile utilizzare il report Attività **peer-to-peer di Skype for Business** per vedere quanto gli utenti usano messaggistica istantanea, audio, video, condivisione applicazioni e trasferimento di file. 

Vedere la panoramica [dei report.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione. 
  
> [!NOTE]
> Puoi visualizzare tutti i rapporti di Skype for Business quando accedi come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Come ottenere il report Attività peer-to-peer Skype for Business

1. Accedere all'interfaccia di amministrazione > **utilizzo dei**  >  **report.**
    
2. Nella pagina **Utilizzo** selezionare Attività   >  **peer-to-peer** Skype for Business nell'elenco Selezionare **un report a** sinistra. In caso contrario, fare clic sul widget attività di **Skype for Business** e quindi fare clic su Attività **peer-to-peer Skype for Business** nell'elenco attività di Skype for **Business.**

## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Interpretare il report Attività peer-to-peer Skype for Business

È possibile consultare il report Attività peer-to-peer Skype for Business leggendo i grafici **Attività**, **Utenti** e **Minuti**.
  
![Report peer-to-peer Skype con callout.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>Il report **Attività peer-to-peer Skype for Business** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un giorno specifico nel report, la tabella (vedere il numero 7) mostrerà dati per 30 giorni, fino alla data (vedere il numero 2) per la data in cui è stato generato il report.

> [!NOTE]
> Se si fa clic nei dettagli di un giorno specifico, la tabella visualizza solo i dati relativi ai 30 giorni successivi alla data in cui è stato generato il report.

***
![Numero 2](../images/sfbcallout2.png)<br/>Ogni report riporta la data in cui è stato generato. In genere, i report hanno una latenza di 24-48 ore dal momento dell'attività. 
***
![Numero 3](../images/sfbcallout3.png)<br/>Usare i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero totale di sessioni, per tipo di sessione, nella propria organizzazione. Mostra il numero totale e i tipi di sessioni di messaggistica **istantanea,** **audio,** **video,** condivisione applicazioni e trasferimenti di **file** nell'intera organizzazione. 
***
![Numero 4](../images/sfbcallout4.png)<br/>Usare i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero totale di utenti unici che hanno partecipato ad attività peer-to-peer tenute nella propria organizzazione. Mostra il numero totale di utenti e i tipi di messaggistica **istantanea,** **audio,** **video,** condivisione applicazioni e trasferimenti di **file** nelle sessioni peer-to-peer.
***
![Numero 5](../images/sfbcallout5.png)<br/>Usare i dati del grafico interattivo **Minuti** per comprendere le tendenze di utilizzo e vedere il numero totale di minuti utilizzati dagli utenti quando eseguono attività peer-to-peer con audio e video. Mostra il numero totale di minuti di **Audio** e **Video** utilizzati nelle sessioni peer-to-peer. 
***
![Numero 6](../images/sfbcallout6.png)<br/>Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale). 
*    Nel grafico **Attività**, l'asse Y è il numero totale di sessioni di messaggistica istantanea, audio, video, condivisione applicazioni e trasferimento file tenute da utenti della propria organizzazione.
*    Nel grafico **Attività degli** utenti, l'asse Y è il numero totale di utenti che hanno tenuto sessioni di messaggistica istantanea, audio, video, condivisione applicazioni e trasferimento di file. 
*    Nel grafico **Minuti**, l'asse Y è il numero totale di minuti di usati dagli utenti della propria organizzazione nelle sessioni peer-to-peer audio e video. 

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico.
***
![Numero 7](../images/sfbcallout7.png)<br/>È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio,  nel grafico Attività toccare o fare clic su Messaggistica **istantanea,** **Audio,** **Video,** Condivisione applicazioni e **Trasferimento file** per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. 
***
![Numero 8](../images/sfbcallout8.png)<br/>La tabella illustra tutte le attività peer-to-peer per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le loro attività peer-to-peer. È possibile aggiungere ulteriori colonne dalla tabella.
*    **Nome utente** è il nome dell'utente.
*    **Eliminato** indica che la licenza dell'utente è stata rimossa. <br/> <br/> **Nota:**  L'attività per un utente eliminato continuerà a essere visualizzata in un report se durante il periodo di tempo selezionato all'utente è stata concessa una licenza. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/><br/>
*    **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa. 
*    **Data di ultima attività (UTC)** è la data dell'ultima attività (UTC) per quell'utente.
*    **Messaggistica istantanea** indica il numero totale di sessioni peer-to-peer che l'utente ha utilizzato.
*    **Audio** indica il numero totale di sessioni peer-to-peer che hanno utilizzato l'audio.
*    **Video** indica il numero totale di sessioni peer-to-peer che hanno utilizzato il video.
*    **Condivisione applicazioni** mostra il numero totale di sessioni di condivisione applicazioni peer-to-peer.
*    **Trasferimento file** mostra il numero totale di sessioni di trasferimento file peer-to-peer.
*    **Minuti audio** mostra il numero totale di minuti audio utilizzati in tutta l'organizzazione. 
*    **Minuti video** mostra il numero totale di minuti video utilizzati in tutta l'organizzazione. 

Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i dettagli dell'utente** nella sezione [Report attività nell'interfaccia di amministrazione.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
***
![Numero 9](../images/sfbcallout9.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Pulsante di esportazione dei report di Skype for Business.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
***
![Numero 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Toccare o fare clic **sull'icona** Colonne in una delle colonne per aggiungere o rimuovere colonne dal report.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](conference-participant-activity-report.md) È possibile visualizzare il numero di partecipanti a conferenze con messaggistica istantanea, audio/video, condivisione applicazioni, web e accesso esterno in ingresso/uscita.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Report di utilizzo PSTN di Skype for Business](pstn-usage-report.md) È possibile visualizzare il numero di minuti speso per le chiamate in entrata/in uscita e i costi per queste chiamate.
    
- [I pool di minuti PSTN di Skype for Business riportano](pstn-minute-pools-report.md) il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report dei dettagli della sessione di Skype for Business](session-details-report.md) Puoi vedere i dettagli sulle esperienze di chiamata di un singolo utente.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 