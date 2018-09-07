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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: d13ca7f70880d7ad0f3c6376e167c6222682887d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855576"
---
# <a name="activity-report"></a>Report attività

[] Il nuovo dashboard **Report** di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella tua organizzazione. Consente di eseguire il drill-ai singoli report a livello di prodotto per assegnare più granulare delle conoscenze relative alle attività all'interno di ogni prodotto. Ad esempio, si può utilizzare il report **Skype per l'attività aziendale** per visualizzare gli utenti utilizzano la quantità peer-to-peer o organizzati in sessioni di conferenza o la quantità sta che partecipano alle sessioni di conferenza. 

Consultare la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per ulteriori informazioni.
  
La relazione, nonché altri Skype per i report di Business, offre informazioni dettagliate sull'attività all'interno dell'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> Quando effettua l'accesso come amministratore nell'interfaccia di amministrazione di Office 365, è possibile visualizzare tutti i Skype per i report di Business. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Come ottenere il report attività in Skype for Business

1. Vai al **Centro di amministrazione di Office 365** > **report** > **dati di utilizzo**.
    
2. Nella pagina **utilizzo** , fare clic su **Skype per attività di Business** in **Selezionare un elenco dei report** sinistra oppure fare clic su widget **Skype per l'attività aziendale** .
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > A seconda della sottoscrizione di Office 365 che si dispone, non è possibile visualizzare tutti i prodotti e i rapporti riportati di seguito. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretazione del report attività in Skype for Business

Puoi consultare il report attività in Skype for Business dell'utente, visualizzando i grafici **Attività** e **Utenti**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>
Il rapporto attività di posta elettronica **Skype per l'attività aziendali** può essere visualizzato per le tendenze negli ultimi 7 giorni, 30 giorni, 90 giorni o 180 giorni. Tuttavia, se si fa clic su in un giorno particolare del rapporto di tabella (vedere numero 7) verrà visualizzati i dati fino a 28 giorni dalla data corrente (non la data della generazione del report).

> [!NOTE]
> Se fa clic su nei dettagli di un giorno specifico, la tabella verrà visualizzati solo i dati per 30 giorni fino alla data quando è stato generato il rapporto.

***
![Numero 2](../images/sfbcallout2.png)<br/>
Ogni report riporta la data in cui è stato generato. I report riflettono in genere una latenza 24 a 48 ore di tempo di attività. 
***
![Numero 3](../images/sfbcallout3.png)<br/>Usa i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero delle attività di conferenze tenute nella tua organizzazione. Il grafico mostra il numero totale e i tipi di **Sessioni peer-to-peer**, sessioni di conferenze **Organizzate** e **Frequentate** tenute nella tua organizzazione.  
***
![Numero 4](../images/sfbcallout4.png)<br/>
Usa i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero di utenti univoci che partecipano ad attività di conferenze tenute nella tua organizzazione. Descritto il numero totale di utenti e i tipi di **sessioni Peer-to-peer**, **organizzata**e **Participated** nelle sessioni di conferenza.
***
![Numero 5](../images/sfbcallout5.png)<br/>
Puoi filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico **attività** , fare clic o toccare **sessioni Peer-to-peer**, **organizzata**o **Participated** per visualizzare solo le informazioni relative a ciascuno di essi. La modifica di questa selezione non cambia le informazioni nella tabella della griglia. 
***
![Numero 6](../images/sfbcallout6.png)<br/>
Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale).
*    Nel grafico **attività** all'asse Y è il numero totale di peer-to-peer, organizzati e partecipato alle sessioni di conferenza che vengono mantenute.
*    Nel grafico attività **degli utenti** , all'asse Y è il numero di utenti univoci partecipazione a ogni tipo di peer-to-peer, organizzati e partecipato alla conferenza.

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. 
***
![Numero 7](../images/sfbcallout7.png)<br/>
La tabella mostra suddivisione di tutte le attività di conferenza per utente. Mostra tutti gli utenti che dispongono di Skype per le aziende assegnata e le attività di conferenza. Puoi aggiungere altre colonne alla tabella.
*    **Nome utente** è il nome dell'utente.
*    **Eliminato** indica che la licenza dell'utente è stata rimossa.<br/><br/>
    > [!NOTE]
    > Attività per un utente eliminato sarà comunque visualizzata in un rapporto, purché potrà è stato concesso in licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.
     
*    **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.
*    **Data di ultima attività (UTC)** indica l'ultima volta in cui l'utente ha avviato una sessione peer to peer o ha organizzato o partecipato a una conferenza.
*    **-To-peer** Visualizza il numero totale di sessioni di conferenze peer-to-peer utilizzato dall'utente.
*    **Conferenze organizzate** mostra il numero totale di conferenze che sono state organizzate dall'utente.
*    **Conferenze frequentate** mostra il numero totale di conferenze a cui ha partecipato questo utente.
*    **Prodotto assegnato** si riferisce ai prodotti di Office 365 assegnati all'utente.<br/>

Se i criteri dell'organizzazione impediscano la visualizzazione dei report in cui sono identificabili informazioni utente, è possibile modificare l'impostazione di privacy per tutti questi rapporti. Consultare la sezione **nascondere dettagli utente nei rapporti** nei [Rapporti sull'attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Numero 8](../images/sfbcallout8.png)<br/>
Fare clic o toccare l'icona di **colonne** in una delle colonne da aggiungere o rimuovere colonne dal rapporto.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numero 9](../images/sfbcallout9.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Pulsante Esporta Skype per i report di Business.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si dispone di meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Skype per report sull'utilizzo dei dispositivi Business](device-usage-report.md) È possibile per visualizzare i dispositivi, inclusi sistemi operativi Windows e dispositivi mobili con Skype per applicazioni aziendali installati e utilizzano per la messaggistica Istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype per report attività peer-to-peer aziendale](peer-to-peer-activity-report.md) È possibile visualizzare quanto gli utenti utilizzano la messaggistica immediata, audio/video, condivisione dell'applicazione e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Skype per i report di utilizzo PSTN Business](pstn-usage-report.md) È possibile visualizzare il numero di minuti, trascorso per le chiamate in ingresso/in uscita e dei costi per le chiamate.

- [Skype per report pool minuto Business PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti utilizzati durante il mese corrente all'interno dell'organizzazione.

- [Skype per rapporto Dettagli sessione Business](session-details-report.md) È possibile visualizzare informazioni dettagliate sull'esperienza di chiamata dell'utente singolo.

    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
