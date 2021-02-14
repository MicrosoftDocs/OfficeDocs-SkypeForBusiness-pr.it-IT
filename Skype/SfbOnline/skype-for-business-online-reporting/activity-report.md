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
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: f50b8c03304a308594fd7bd920ee92e8d38a1f43
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205557"
---
# <a name="activity-report"></a>Report attività

Il **dashboard** Report mostra una panoramica delle attività per tutti i prodotti Microsoft 365 o Office 365 nell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto per ottenere informazioni più dettagliate sulle attività all'interno di ogni prodotto. Ad esempio, puoi utilizzare il report attività di **Skype for Business** per vedere quanto gli utenti usano sessioni di conferenza peer-to-peer o organizzate o quanto partecipano alle sessioni di conferenza. 

Per altre informazioni, [vedere la](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) panoramica sui report.
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> Puoi visualizzare tutti i rapporti di Skype for Business quando accedi come amministratore nell'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Come ottenere il report attività in Skype for Business

1. Accedere all'interfaccia di amministrazione > **utilizzo dei**  >  **report.**
    
2. Nella pagina **Utilizzo** scegliere Attività **Skype for Business** nell'elenco Selezionare un report a sinistra oppure fare clic sul widget Attività di Skype for  >   **Business.** 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretazione del report attività in Skype for Business

Puoi consultare il report attività in Skype for Business dell'utente, visualizzando i grafici **Attività** e **Utenti**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>
Il report Attività di posta elettronica di **Skype for Business**  può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un giorno specifico nel report, la tabella (vedere il numero 7) mostrerà dati per un massimo di 28 giorni dalla data corrente (non dalla data in cui è stato generato il report).

> [!NOTE]
> Se si fa clic nei dettagli di un giorno specifico, la tabella visualizza solo i dati relativi ai 30 giorni successivi alla data in cui è stato generato il report.

***
![Numero 2](../images/sfbcallout2.png)<br/>
Ogni report riporta la data in cui è stato generato. In genere, i report hanno una latenza di 24-48 ore dal momento dell'attività. 
***
![Numero 3](../images/sfbcallout3.png)<br/>Usa i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero delle attività di conferenze tenute nella tua organizzazione. Il grafico mostra il numero totale e i tipi di **Sessioni peer-to-peer**, sessioni di conferenze **Organizzate** e **Frequentate** tenute nella tua organizzazione.  
***
![Numero 4](../images/sfbcallout4.png)<br/>
Usa i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero di utenti univoci che partecipano ad attività di conferenze tenute nella tua organizzazione. Mostra il numero totale di utenti e i tipi di sessioni  **peer-to-peer,** organizzate e partecipate **alle** conferenze.
***
![Numero 5](../images/sfbcallout5.png)<br/>
È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio,  nel grafico Attività toccare o fare clic su  Sessioni **peer-to-peer,** Organizzate o Organizzate per visualizzare solo le informazioni per ognuna di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. 
***
![Numero 6](../images/sfbcallout6.png)<br/>
Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale).
*    Nel grafico **Attività,** l'asse Y è il numero totale di sessioni di conferenze peer-to-peer, organizzate e vi partecipano.
*    Nel grafico **Attività** degli utenti, l'asse Y è il numero di utenti univoci che partecipano a ogni tipo di conferenza peer-to-peer, organizzata e frequentata.

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. 
***
![Numero 7](../images/sfbcallout7.png)<br/>
La tabella mostra un'analisi di tutte le attività di conferenza per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le loro attività di conferenza. È possibile aggiungere altre colonne alla tabella.
* **Nome** utente è il nome dell'utente.
* **Eliminato** indica che la licenza dell'utente è stata rimossa.<br/><br/>
  > [!NOTE]
  > L'attività per un utente eliminato continuerà a essere visualizzata in un report se durante il periodo di tempo selezionato all'utente è stata concessa una licenza. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.
     
* **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.
* **Data di ultima attività (UTC)** indica l'ultima volta in cui l'utente ha avviato una sessione peer to peer o ha organizzato o partecipato a una conferenza.
* **Peer-to-peer** mostra il numero totale di sessioni di conferenze peer-to-peer usate dall'utente.
* **Conferenze organizzate** mostra il numero totale di conferenze che sono state organizzate dall'utente.
* **Conferenze frequentate** mostra il numero totale di conferenze a cui ha partecipato questo utente.
* **Il prodotto** assegnato è quello di Microsoft 365 o Office 365 assegnato a questo utente.<br/>

Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Nascondere i dettagli utente nella sezione Report** attività [nell'interfaccia di amministrazione.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
***
![Numero 8](../images/sfbcallout8.png)<br/>
Toccare o fare clic **sull'icona** Colonne in una delle colonne per aggiungere o rimuovere colonne dal report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numero 9](../images/sfbcallout9.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Pulsante di esportazione dei report di Skype for Business.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report utilizzo dispositivi Skype for Business](device-usage-report.md) È possibile visualizzare i dispositivi, compresi i sistemi operativi e i dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la usano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) È possibile vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Report di utilizzo PSTN di Skype for Business](pstn-usage-report.md) È possibile visualizzare il numero di minuti speso per le chiamate in entrata/in uscita e i costi per queste chiamate.

- [I pool di minuti PSTN di Skype for Business riportano](pstn-minute-pools-report.md) il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report dei dettagli della sessione di Skype for Business](session-details-report.md) Puoi vedere i dettagli sulle esperienze di chiamata di un singolo utente.

    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
