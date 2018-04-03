---
title: Activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 419bb60a40271c6680193841c175cb86860a2a0e
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="activity-report"></a>Activity report

[] Il nuovo dashboard **Report** di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella tua organizzazione. It enables you to drill in to individual product-level reports to give you more granular insight about the activities within each product. For example, you can use the **Skype for Business activity** report to see how much your users are using peer-to-peer or organized conferencing sessions, or how much they're participating in conferencing sessions. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) to learn more.
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> You can see all of the Skype for Business reports when you log on as an administrator in the Office 365 admin center. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Come ottenere il report attività in Skype for Business

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business activity** on the **Select a report list** on the left, or click the **Skype for Business activity** widget.
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Depending on the Office 365 subscription you have, you might not see all the products and reports shown here. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretazione del report attività in Skype for Business

Puoi consultare il report attività in Skype for Business dell'utente, visualizzando i grafici **Attività** e **Utenti**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>
Il report **attività in Skype for Business** può essere visualizzato per individuare le tendenze degli ultimi 7, 30, 90 o 180 giorni.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>
Ogni report riporta la data in cui è stato generato. The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>Usa i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero delle attività di conferenze tenute nella tua organizzazione. Il grafico mostra il numero totale e i tipi di **Sessioni peer-to-peer**, sessioni di conferenze **Organizzate** e **Frequentate** tenute nella tua organizzazione.  
***
![Number 4](../images/sfbcallout4.png)<br/>
Usa i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero di utenti univoci che partecipano ad attività di conferenze tenute nella tua organizzazione. It will show you the total number of users along with the types of **Peer-to-peer sessions**, **Organized**, and **Participated** in conference sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>
Puoi filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. For example, on the **Activity** chart, click or tap **Peer-to-peer sessions**, **Organized**, or **Participated** to see only the info related to each one. La modifica di questa selezione non cambia le informazioni nella tabella della griglia. 
***
![Number 6](../images/sfbcallout6.png)<br/>
Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale).
*    On the **Activity** chart, the Y axis is the total number of peer-to-peer, organized, and participated in conference sessions that are held.
*    On the **Users** activity chart, the Y axis is the number of unique users attending in each type of peer-to-peer, organized, and participated in conference.

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. 
***
![Number 7](../images/sfbcallout7.png)<br/>
The table shows you a breakdown of all the conferencing activities per user. This shows all users who have Skype for Business assigned to them and their conferencing activities. Puoi aggiungere altre colonne alla tabella.
*    **Username** is the name of the user.
*    **Eliminato** indica che la licenza dell'utente è stata rimossa. <br/> <br/> **Note:** Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.<br/><br/>
*    **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.
*    **Data di ultima attività (UTC)** indica l'ultima volta in cui l'utente ha avviato una sessione peer to peer o ha organizzato o partecipato a una conferenza.
*    **Peer-to-peer** shows the total number of peer-to-peer conference sessions that the user used.
*    **Conferenze organizzate** mostra il numero totale di conferenze che sono state organizzate dall'utente.
*    **Conferenze frequentate** mostra il numero totale di conferenze a cui ha partecipato questo utente.
*    **Prodotto assegnato** si riferisce ai prodotti di Office 365 assegnati all'utente.<br/>

If your organization's policies prevent you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **Hide user details in the reports** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Number 8](../images/sfbcallout8.png)<br/>
Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Number 9](../images/sfbcallout9.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. If you have fewer than 2000 users, you can sort and filter within the table in the report itself. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Skype for Business device usage report](device-usage-report.md) You can to see the devices, including Windows-based operating systems and mobile devices, that have the Skype for Business app installed and are using it for IM and meetings.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype for Business peer-to-peer activity report](peer-to-peer-activity-report.md) You can see how much your users are using IM, audio/video, application sharing, and transferring files.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.

- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.

    
## <a name="related-topics"></a>See also
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 