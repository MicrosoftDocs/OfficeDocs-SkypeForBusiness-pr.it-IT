---
title: Report pool minuti PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: La nuova area report dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report pool di minuti PSTN di Skype for business per visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
ms.openlocfilehash: bfbc21453732d338c4d0cf6355903df344c826f4
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494016"
---
# <a name="pstn-minute-pools-report"></a>Report pool minuti PSTN

>[!NOTE]
>Questo report è disponibile solo per i clienti in anteprima.

La nuova area **report** dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report **pool di minuti PSTN di Skype for business** per visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
  
Vedere la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report di Skype for business, fornisce informazioni dettagliate sulle attività in tutta l'organizzazione. Questi dettagli sono molto utili quando si esaminano, progettano e prendono le altre decisioni aziendali per la propria organizzazione e per la configurazione dei crediti per le [comunicazioni](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Come ottenere il report dei pool di minuti PSTN di Skype for business

![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**

- Accedere all'interfaccia di amministrazione di **Office 365** > **** > per l'interfaccia di amministrazione di**Skype for business** > **segnala** > i**pool di minuti PSTN**.
    
> [!NOTE]
> A seconda dell'abbonamento a Office 365, potresti non vedere tutti gli stessi dettagli visualizzati qui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretare il report pool di minuti PSTN di Skype for business

È possibile visualizzare i pool di minuti Skype for business dell'utente esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.
  
## 

![Report dei pool di minuti PSTN di Skype for business](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella mostra una ripartizione dei pool di minuti in base alla licenza (funzionalità) e alla posizione di utilizzo. 
*    **Funzionalità** è il piano di licenza/servizio usato per la chiamata. I piani di licenza/servizio che potrebbero essere visualizzati in questo report includono:
     * MCOPSTN1-piano per chiamate nazionali (3000-minuti US/1200-minute EU plans
     * MCOPSTN2-piano nazionale di chiamate internazionali & da cui si vedrà una piscina nazionale (3000 minuti Stati Uniti/Canada/PR, 1200 minuti in paesi europei) e un pool internazionale (600 minuti). Viene raggiunto il limite di minuti ogni volta che viene raggiunto il limite nazionale o internazionale entro il mese del calendario. 
     * MCOPSTN5-piano per chiamate nazionali (piano per chiamate di 120-minute)
     * MCOPSTN6-piano per chiamate nazionali (piano per chiamate di 240-minute)
     * MCOMEETADD-audioconferenza
*    **Descrizione funzionalità** è una descrizione del tipo di licenza utilizzata per la chiamata.
*    **Paese minute pool** è la posizione di utilizzo della licenza dell'utente o degli utenti che condividono il pool di minuti. 
*    **Minuti usati** indica il numero di minuti usati ogni mese.
*    **Minuti totali** indica il numero totale di minuti disponibili per il mese. 
*    **Percentuale usata** è la percentuale di minuti usata per il mese. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella nel report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze di Skype for business](conference-organizer-activity-report.md) Puoi vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, Web,/dial out-3rd party e/dial out-Microsoft.
    
- [Report attività partecipante di conferenze di Skype for business](conference-participant-activity-report.md) È possibile vedere il numero di partecipazioni a conferenze audio, audio/video, condivisione applicazioni, Web e dial-out.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Report Dettagli sessione di Skype for business](session-details-report.md) È possibile visualizzare i dettagli sulle singole esperienze delle chiamate degli utenti.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
