---
title: Peer-to-peer activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: ad2e9745d68a3c47e60aa03f957054a1eeef1deb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="peer-to-peer-activity-report"></a>Peer-to-peer activity report

[] Il nuovo dashboard **Report** di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella tua organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto. For example, you can use the **Skype for Business peer-to-peer activity** report to see how much your users are using IM, audio, video, application sharing, and transferring files. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione. 
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Come ottenere il report Attività peer-to-peer Skype for Business

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business peer-to-peer activity** on the **Select a report list** on the left. Or, click the **Skype for Business activity** widget and then click **Skype for Business peer-to-peer activity** on the **Skype for Business activity** list.
    
     ![Skype peer to peer menu selected](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei report su prodotti e attività illustrati in questo articolo potrebbero non essere disponibili. 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Interpretare il report Attività peer-to-peer Skype for Business

È possibile consultare il report Attività peer-to-peer Skype for Business leggendo i grafici **Attività**, **Utenti** e **Minuti**.
  
![Skype peer to peer report with callouts.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Number 1](../images/sfbcallout1.png)<br/>Il report **Attività peer-to-peer Skype for Business** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>Ogni report riporta la data in cui è stato generato. The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>Usare i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero totale di sessioni, per tipo di sessione, nella propria organizzazione. It will show you the total number and types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** sessions across your organization. 
***
![Number 4](../images/sfbcallout4.png)<br/>Usare i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero totale di utenti unici che hanno partecipato ad attività peer-to-peer tenute nella propria organizzazione. It will show you the total number of users along with the types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** in peer-to-peer sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>Usare i dati del grafico interattivo **Minuti** per comprendere le tendenze di utilizzo e vedere il numero totale di minuti utilizzati dagli utenti quando eseguono attività peer-to-peer con audio e video. Mostra il numero totale di minuti di **Audio** e **Video** utilizzati nelle sessioni peer-to-peer. 
***
![Number 6](../images/sfbcallout6.png)<br/>Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale). 
*    Nel grafico **Attività**, l'asse Y è il numero totale di sessioni di messaggistica istantanea, audio, video, condivisione applicazioni e trasferimento file tenute da utenti della propria organizzazione.
*    On the **Users** activity chart, the Y axis is the total number users that held IM, audio, video, application sharing, and transferring files sessions. 
*    Nel grafico **Minuti**, l'asse Y è il numero totale di minuti di usati dagli utenti della propria organizzazione nelle sessioni peer-to-peer audio e video. 

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico.
***
![Number 7](../images/sfbcallout7.png)<br/>Puoi filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. For example, on the **Activity** chart, click or tap **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** to see only the info related to each one. La modifica di questa selezione non cambia le informazioni nella tabella della griglia. 
***
![Number 8](../images/sfbcallout8.png)<br/>La tabella illustra tutte le attività peer-to-peer per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le loro attività peer-to-peer. È possibile aggiungere ulteriori colonne dalla tabella.
*    **Nome utente** è il nome dell'utente.
*    **Eliminato** indica che la licenza dell'utente è stata rimossa. <br/> <br/> **Note:**  Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/><br/>
*    **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa. 
*    **Data di ultima attività (UTC)** è la data dell'ultima attività (UTC) per quell'utente.
*    **Messaggistica istantanea** indica il numero totale di sessioni peer-to-peer che l'utente ha utilizzato.
*    **Audio** indica il numero totale di sessioni peer-to-peer che hanno utilizzato l'audio.
*    **Video** indica il numero totale di sessioni peer-to-peer che hanno utilizzato il video.
*    **Condivisione applicazioni** mostra il numero totale di sessioni di condivisione applicazioni peer-to-peer.
*    **Trasferimento file** mostra il numero totale di sessioni di trasferimento file peer-to-peer.
*    **Minuti audio** mostra il numero totale di minuti audio utilizzati in tutta l'organizzazione. 
*    **Minuti video** mostra il numero totale di minuti video utilizzati in tutta l'organizzazione. 

Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
***
![Number 9](../images/sfbcallout9.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
***
![Number 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](conference-participant-activity-report.md) - Visualizza il numero di partecipazioni a conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web e accesso esterno in ingresso/uscita.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.
    
- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.
    
## <a name="related-topics"></a>See also
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 