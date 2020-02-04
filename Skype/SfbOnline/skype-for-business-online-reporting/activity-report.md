---
title: Report attività
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 1da7ea7b826d5a8f86691cda8b41b49298114d50
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692451"
---
# <a name="activity-report"></a>Report attività

Il dashboard di **report** di Office 365 Mostra la panoramica delle attività nei prodotti Office 365 dell'organizzazione. Consente di eseguire il drill-up dei singoli report a livello di prodotto per ottenere informazioni più dettagliate sulle attività all'interno di ogni prodotto. Ad esempio, puoi usare il report **attività di Skype for business** per vedere quanto gli utenti usano sessioni di conferenza peer-to-peer o organizzate, o quanto partecipano alle sessioni di conferenza. 

Per altre informazioni, vedere [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) .
  
Questo report, insieme agli altri report di Skype for business, fornisce informazioni dettagliate sulle attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for business quando si accede come amministratore nell'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Come ottenere il report attività in Skype for Business

1. Accedere all'interfaccia di amministrazione > **segnala** > l'**utilizzo**.
    
2. Nella pagina **uso** scegliere**attività** **Skype for business** > nell' **elenco Seleziona un report** a sinistra oppure fare clic sul widget **attività di Skype for business** .

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretazione del report attività in Skype for Business

Puoi consultare il report attività in Skype for Business dell'utente, visualizzando i grafici **Attività** e **Utenti**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>
Il report attività di posta elettronica **attività di Skype for business** può essere visualizzato per le tendenze degli ultimi 7 giorni, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un determinato giorno del report, la tabella (Vedi numero 7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).

> [!NOTE]
> Se si fa clic nei dettagli di un giorno specifico, nella tabella verranno visualizzati solo i dati per i 30 giorni fino alla data in cui è stato generato il report.

***
![Numero 2](../images/sfbcallout2.png)<br/>
Ogni report riporta la data in cui è stato generato. I report riflettono in genere una latenza da 24 a 48 ore dal momento dell'attività. 
***
![Numero 3](../images/sfbcallout3.png)<br/>Usa i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero delle attività di conferenze tenute nella tua organizzazione. Il grafico mostra il numero totale e i tipi di **Sessioni peer-to-peer**, sessioni di conferenze **Organizzate** e **Frequentate** tenute nella tua organizzazione.  
***
![Numero 4](../images/sfbcallout4.png)<br/>
Usa i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero di utenti univoci che partecipano ad attività di conferenze tenute nella tua organizzazione. Verrà visualizzato il numero totale di utenti insieme ai tipi di **sessioni peer-to-peer**, **organizzati**e **partecipato** alle sessioni di conferenza.
***
![Numero 5](../images/sfbcallout5.png)<br/>
È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **attività** fare clic o toccare **sessioni peer-to-peer**, **organizzate**o **partecipate** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. 
***
![Numero 6](../images/sfbcallout6.png)<br/>
Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale).
*    Nel grafico **attività** l'asse Y è il numero totale di peer-to-peer, organizzati e partecipato alle sessioni di conferenza che si svolgono.
*    Nel grafico attività **utenti** l'asse Y rappresenta il numero di utenti univoci che partecipano a ogni tipo di peer-to-peer, organizzati e partecipati alla conferenza.

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. 
***
![Numero 7](../images/sfbcallout7.png)<br/>
La tabella mostra una ripartizione di tutte le attività di conferenza per ogni utente. Questo Mostra tutti gli utenti che hanno assegnato Skype for business e le loro attività di conferenza. È possibile aggiungere altre colonne alla tabella.
* **Username** è il nome dell'utente.
* **Eliminato** indica che la licenza dell'utente è stata rimossa.<br/><br/>
  > [!NOTE]
  > Le attività per un utente eliminato verranno comunque visualizzate in un report a condizione che sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.
     
* **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.
* **Data di ultima attività (UTC)** indica l'ultima volta in cui l'utente ha avviato una sessione peer to peer o ha organizzato o partecipato a una conferenza.
* **Peer-to-peer** Mostra il numero totale di sessioni di conferenza peer-to-peer che l'utente ha usato.
* **Conferenze organizzate** mostra il numero totale di conferenze che sono state organizzate dall'utente.
* **Conferenze frequentate** mostra il numero totale di conferenze a cui ha partecipato questo utente.
* **Prodotto assegnato** si riferisce ai prodotti di Office 365 assegnati all'utente.<br/>

Se i criteri dell'organizzazione impediscono di visualizzare i report in cui le informazioni utente sono identificabili, è possibile modificare l'impostazione di privacy per tutti questi report. Per visualizzare i **dettagli degli utenti** , vedere la sezione report nei [report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Numero 8](../images/sfbcallout8.png)<br/>
Toccare o fare clic sull'icona **colonne** in una delle colonne per aggiungere o rimuovere colonne dal report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numero 9](../images/sfbcallout9.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Pulsante Esporta report di Skype for business.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella nel report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report sull'utilizzo di dispositivi Skype for business](device-usage-report.md) Puoi vedere i dispositivi, inclusi i sistemi operativi basati su Windows e i dispositivi mobili, che hanno installato l'app Skype for business e lo usano per la messaggistica istantanea e le riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività peer-to-peer di Skype for business](peer-to-peer-activity-report.md) Puoi vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Report sull'utilizzo PSTN di Skype for business](pstn-usage-report.md) È possibile visualizzare il numero di minuti di chiamate in ingresso/in uscita e il costo per queste chiamate.

- [Report pool di minuti PSTN di Skype for business](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report Dettagli sessione di Skype for business](session-details-report.md) È possibile visualizzare i dettagli sulle singole esperienze delle chiamate degli utenti.

    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
