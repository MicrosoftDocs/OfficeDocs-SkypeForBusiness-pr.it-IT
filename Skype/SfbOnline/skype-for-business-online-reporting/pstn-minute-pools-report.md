---
title: Rapporto pool minuto PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Nuovo Skype per area Business Admin Center report mostra è chiamante e audio conferencing attività all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile utilizzare Skype per report pool minuto Business PSTN per visualizzare il numero di minuti utilizzati durante il mese corrente all'interno dell'organizzazione.
ms.openlocfilehash: be1b3cbea37f8d66c25ef6c1e75f18e7473a299e
ms.sourcegitcommit: 0a0fd436d4d732710bb65e1809ac28dd2e0df41a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2018
ms.locfileid: "19526945"
---
# <a name="pstn-minute-pools-report"></a>Rapporto pool minuto PSTN

>[!NOTE]
>In questo report è disponibile solo in anteprima i clienti.

Nuovo Skype per area Business Admin Center **report** Mostra è chiamante e audio conferencing attività all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile utilizzare il rapporto **Skype per i pool minuti Business PSTN** per visualizzare il numero di minuti utilizzati durante il mese corrente all'interno dell'organizzazione.
  
Consultare la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per i report più disponibili.
  
La relazione, nonché altri Skype per i report di Business, offre informazioni dettagliate sull'attività all'interno dell'organizzazione. Queste informazioni sono molto utili quando analisi dei, pianificazione e altre decisioni strategiche, per l'organizzazione e per la configurazione di [Comunicazioni titoli di coda](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Come ottenere Skype per report pool minuto Business PSTN

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

- Accedere **all'interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per Business admin center** > **report** > **pool minuto PSTN**.
    
> [!NOTE]
> A seconda la sottoscrizione a Office 365 che si dispone, si potrebbero non visualizzare gli stessi dettagli riportati di seguito. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretazione Skype per report pool minuto Business PSTN

È possibile ottenere una visualizzazione in Skype dell'utente per i pool minuti Business esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.
  
## 

![Skype per minuto Business PSTN pool report](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella mostra suddivisione dei pool minuto con licenza (funzionalità) e la posizione di utilizzo. 
*    **Capacità** è il piano di licenza/servizio utilizzato per la chiamata. I piani di servizio di licenza e che potrebbe essere riportato in questo report sono:
     * MCOPSTN1 - nazionale chiamata pianificare (minuto 3000 1200/US-minuto UE piani
     * MCOPSTN2 - piano chiamate internazionali
     * MCOPSTN5 - nazionale chiamata Plan (piano di chiamata di 120 minuti)
     * MCOPSTN6 - nazionale chiamata Plan (piano chiamante 240 minuti)
     * MCOMEETADD - audioconferenze con accesso esterno
*    **Descrizione delle funzionalità** è una descrizione del tipo di licenza utilizzata per la chiamata.
*    **Paese minuto Pool** è il percorso di utilizzo di licenza di uno o più utenti che condividono il pool minuto. 
*    **Minuti utilizzato** è il numero di minuti utilizzati ogni mese.
*    **Totale minuti** è il numero totale di minuti disponibili per il mese. 
*    **Percentuale utilizzata** è la percentuale di minuti per il mese. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si dispone di meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Skype per rapporto attività di organizzatore della conferenza aziendali](conference-organizer-activity-report.md) È possibile visualizzare quanto gli utenti sono organizzare conferenze che utilizzano la messaggistica immediata, audio/video, condivisione di applicazioni, Web, /dial le parti - 3rd e /dial out - Microsoft.
    
- [Skype per rapporto attività partecipante di conferenza aziendali](conference-participant-activity-report.md) È possibile visualizzare il numero messaggistica immediata, audio/video, la condivisione delle applicazioni, server Web e chiamate in uscita audioconferenze sono viene ha partecipati.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Skype per rapporto Dettagli sessione Business](session-details-report.md) È possibile visualizzare informazioni dettagliate sull'esperienza di chiamata dell'utente singolo.
    
## <a name="related-topics"></a>See also
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
