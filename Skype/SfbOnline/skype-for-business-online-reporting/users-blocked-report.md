---
title: Report utenti bloccati
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: "Questo report, insieme ad altri report Skype for Business, fornisce dettagli sull'attività, incluso l'utilizzo di PSTN nell'intera organizzazione. "
ms.openlocfilehash: f2708512dfb1cf03e367af09abb288e62329eaf0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606725"
---
# <a name="users-blocked-report"></a>Report utenti bloccati

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Il nuovo dashboard Skype for Business **report** mostra la panoramica delle attività nei Skype for Business prodotti dell'organizzazione. Consente di eseguire il drill-in di singoli report a livello di prodotto per fornire informazioni più dettagliate sulle attività all'interno di ogni prodotto. Ad esempio, è possibile usare il **report** Skype for Business utenti bloccati per visualizzare gli utenti dell'organizzazione a cui è stato impedito di effettuare chiamate PSTN. Questo report, insieme ad altri report Skype for Business, fornisce dettagli sull'attività, incluso l'utilizzo di PSTN nell'intera organizzazione.
  
 Vedere la [panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
> [!NOTE]
> È possibile visualizzare tutti i report Skype for Business quando si accede come amministratore al interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Come accedere al report Skype for Business utenti bloccati

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

- Passare all'interfaccia di amministrazione > **di amministrazione Skype for Business** di amministrazione  >  **Segnala**  >  **gli** utenti  >  **bloccati**.
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretare il report Skype for Business utenti bloccati

È possibile visualizzare gli utenti bloccati esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report. 
  
![Report utenti bloccati](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

La tabella mostra una suddivisione di tutti gli utenti a cui è impedito di effettuare chiamate. Mostra tutti gli utenti a cui sono Sistema telefonico o audioconferenze. È possibile aggiungere/rimuovere colonne dalla tabella.
***
![Numero 1](../images/sfbcallout1.png)
*   **L'ID** utente è l'accesso dell'utente.
*   **Telefono numero** è il numero assegnato a un utente. 
*   **Tempo azione blocco** è l'ora (UTC) in cui all'utente è stato impedito di effettuare chiamate.
*   **Azione di** blocco è il tipo di azione eseguita per bloccare l'utente.
*   **Il motivo dell'azione** di blocco è il motivo per cui all'utente è stato impedito di effettuare chiamate.
***
![Numero 2](../images/sfbcallout2.png)<br/>
Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
***
![Numero 3](../images/sfbcallout3.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype for Business attività dei partecipanti alla conferenza](conference-participant-activity-report.md) È possibile vedere il numero di conferenze di messaggistica istantanea, audio/video, condivisione di applicazioni, Web e conferenza telefonica con accesso esterno/esterno a cui si partecipa.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype for Business utilizzo PSTN](pstn-usage-report.md) È possibile visualizzare il numero di minuti trascorsi nelle chiamate in ingresso/in uscita e il costo per queste chiamate.

- Skype for Business pool di minuti [PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Skype for Business dei dettagli della sessione](session-details-report.md) Puoi visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.
   
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
