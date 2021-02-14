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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: La nuova area report dell'interfaccia di amministrazione di Skype for Business mostra le attività di chiamata e audioconferenza all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report pool di minuti PSTN di Skype for Business per vedere il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776251"
---
# <a name="pstn-minute-pools-report"></a>Report pool minuti PSTN

>[!NOTE]
>Questo report è disponibile solo per i clienti preview.

La nuova area report  dell'interfaccia di amministrazione di Skype for Business mostra le attività di chiamata e audioconferenza all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report pool di minuti **PSTN** di Skype for Business per vedere il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
  
Per altri [report disponibili,](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) vedere la panoramica dei report.
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puoi visualizzare tutti i rapporti di Skype for Business quando accedi come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Come ottenere il report pool di minuti PSTN di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

- Accedi all'interfaccia di amministrazione e > **di** amministrazione Skype for Business segnala i pool di  >    >    >  **minuti PSTN.**
    
> [!NOTE]
> A seconda dell'abbonamento a Microsoft 365 o Office 365 di cui si dispone, i dettagli visualizzati potrebbero non essere tutti uguali. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretare il report Pool di minuti PSTN di Skype for Business

È possibile ottenere una visione d'insieme dei pool di minuti per le chiamate Skype for Business degli utenti osservando le colonne visualizzate.
  
Questo è l'aspetto del report.
  
## 

![Report pool di minuti PSTN per Skype for Business](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella mostra un'analisi dei pool di minuti per licenza (funzionalità) e posizione di utilizzo. 
*    **La capacità** è il piano di licenza/servizio utilizzato per la chiamata. I piani di licenza/servizio inclusi in questo report includono:
     * MCOPSTN1 - Piano per chiamate nazionali (piani UE di 3000 minuti per gli Stati Uniti/1200 minuti)
     * MCOPSTN2 - Piano per chiamate internazionali & nazionali dal quale si riceverà un pool nazionale (3000 minuti in Stati Uniti/Canada/PR, paesi europei di 1200 minuti) e un pool internazionale (600 minuti). Il limite di minuti viene raggiunto ogni volta che si raggiunge il limite nazionale -OR- internazionale all'interno del mese di calendario. 
     * MCOPSTN5 - Piano per chiamate nazionali (piano per chiamate di 120 minuti)
     * MCOPSTN6 - Piano per chiamate nazionali (piano per chiamate di 240 minuti)
     * MCOMEETADD - Audioconferenza
*    **Descrizione funzionalità** è una descrizione del tipo di licenza utilizzato per la chiamata.
*    **Country Minute Pool è** la posizione di utilizzo delle licenze degli utenti che condividono il pool di minuti. 
*    **Minuti usati** è il numero di minuti utilizzati ogni mese.
*    **Minuti totali** è il numero totale di minuti disponibili per il mese. 
*    **Percentuale usata** è la percentuale di minuti utilizzati per il mese. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) È possibile vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, web, /chiamata in uscita di terze parti e /chiamata in uscita - Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](conference-participant-activity-report.md) È possibile visualizzare il numero di partecipanti a conferenze audio, audio/video, condivisione applicazioni, web e chiamata in uscita.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Report dei dettagli della sessione di Skype for Business](session-details-report.md) Puoi vedere i dettagli sulle esperienze di chiamata di un singolo utente.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
