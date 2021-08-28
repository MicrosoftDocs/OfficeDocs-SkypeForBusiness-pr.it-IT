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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: bdb7f0df8148b89b90eac073a1d709aa658f06d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605655"
---
# <a name="activity-report"></a>Report attività

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Il **dashboard Report** mostra la panoramica delle attività in Microsoft 365 o Office 365 prodotti dell'organizzazione. Consente di eseguire il drill-in di singoli report a livello di prodotto per fornire informazioni più dettagliate sulle attività all'interno di ogni prodotto. Ad esempio, è possibile usare il report attività di Skype for Business per vedere quanto gli utenti usano sessioni di conferenza peer-to-peer o organizzate o quanto partecipano **alle** sessioni di conferenza. 

Per altre informazioni, [vedere La](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) panoramica dei report.
  
Questo report, insieme agli altri report Skype for Business, fornisce informazioni dettagliate sulle attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione.
  
> [!NOTE]
> È possibile visualizzare tutti i report Skype for Business quando si accede come amministratore nel interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Come ottenere il report attività in Skype for Business

1. Passare all'interfaccia di amministrazione > **utilizzo dei**  >  **report.**
    
2. Nella pagina **Utilizzo** scegliere Skype for Business attività nell'elenco Selezionare un report a sinistra oppure fare clic sul widget Skype for Business  >   **attività.** 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpretazione del report attività in Skype for Business

Puoi consultare il report attività in Skype for Business dell'utente, visualizzando i grafici **Attività** e **Utenti**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>
Il **report Skype for Business attività** di posta elettronica attività può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si fa clic in un giorno specifico nel report, la tabella (vedere il numero 7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).

> [!NOTE]
> Se si fa clic nei dettagli di un giorno specifico, nella tabella verranno visualizzati solo i dati relativi ai 30 giorni fino alla data in cui è stato generato il report.

***
![Numero 2](../images/sfbcallout2.png)<br/>
Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza da 24 a 48 ore dal momento dell'attività. 
***
![Numero 3](../images/sfbcallout3.png)<br/>Usa i dati del grafico interattivo **Attività** per comprendere le tendenze di utilizzo e vedere il numero delle attività di conferenze tenute nella tua organizzazione. Il grafico mostra il numero totale e i tipi di **Sessioni peer-to-peer**, sessioni di conferenze **Organizzate** e **Frequentate** tenute nella tua organizzazione.  
***
![Numero 4](../images/sfbcallout4.png)<br/>
Usa i dati del grafico interattivo **Utenti** per comprendere le tendenze di utilizzo e vedere il numero di utenti univoci che partecipano ad attività di conferenze tenute nella tua organizzazione. Mostra il numero totale di utenti insieme ai tipi di sessioni **peer-to-peer,** **Organizzate** e **Partecipate** alle sessioni di conferenza.
***
![Numero 5](../images/sfbcallout5.png)<br/>
È possibile filtrare la serie visualizzata nel grafico facendo clic su un elemento nella legenda. Ad esempio, nel grafico Attività **toccare** o fare clic su  Sessioni **peer-to-peer** **,** Organizzato o Partecipato per visualizzare solo le informazioni correlate a ognuna. La modifica di questa selezione non modifica le informazioni nella tabella della griglia. 
***
![Numero 6](../images/sfbcallout6.png)<br/>
Ciascun grafico ha un asse X (orizzontale) e un asse Y (verticale).
*    Nel grafico **Attività** l'asse Y è il numero totale di sessioni di conferenza peer-to-peer, organizzate e partecipate.
*    Nel grafico **attività Utenti,** l'asse Y è il numero di utenti univoci che partecipano a ogni tipo di conferenza peer-to-peer, organizzata e partecipata.

L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico. 
***
![Numero 7](../images/sfbcallout7.png)<br/>
La tabella mostra una suddivisione di tutte le attività di conferenza per utente. Mostra tutti gli utenti a cui sono Skype for Business e le loro attività di conferenza. È possibile aggiungere altre colonne alla tabella.
* **Nomeutente** è il nome dell'utente.
* **Eliminato** indica che la licenza dell'utente è stata rimossa.<br/><br/>
  > [!NOTE]
  > Le attività per un utente eliminato verranno comunque visualizzate in un report, purché gli sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.
     
* **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.
* **Data di ultima attività (UTC)** indica l'ultima volta in cui l'utente ha avviato una sessione peer to peer o ha organizzato o partecipato a una conferenza.
* **Peer-to-peer** mostra il numero totale di sessioni di conferenza peer-to-peer usate dall'utente.
* **Conferenze organizzate** mostra il numero totale di conferenze che sono state organizzate dall'utente.
* **Conferenze frequentate** mostra il numero totale di conferenze a cui ha partecipato questo utente.
* **Prodotto assegnato** è il Microsoft 365 o Office 365 prodotti assegnati all'utente.<br/>

Se i criteri dell'organizzazione impediscono la visualizzazione di report in cui le informazioni utente sono identificabili, è possibile modificare l'impostazione di privacy per tutti questi report. Vedere la sezione **Nascondere i dettagli dell'utente nella** sezione Report attività [nell'interfaccia di amministrazione.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
***
![Numero 8](../images/sfbcallout8.png)<br/>
Toccare o fare clic **sull'icona** Colonne in una delle colonne per aggiungere o rimuovere colonne dal report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numero 9](../images/sfbcallout9.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic o toccando **Esporta**.           <br/> ![Skype for Business Pulsante Esporta report.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Skype for Business utilizzo dei dispositivi](device-usage-report.md) È possibile visualizzare i dispositivi, inclusi i Windows e i dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la usano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype for Business attività peer-to-peer](peer-to-peer-activity-report.md) È possibile vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione di applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Skype for Business utilizzo PSTN](pstn-usage-report.md) È possibile visualizzare il numero di minuti trascorsi nelle chiamate in ingresso/in uscita e il costo per queste chiamate.

- [Skype for Business pool di minuti PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Skype for Business dei dettagli della sessione](session-details-report.md) Puoi visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.

    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
