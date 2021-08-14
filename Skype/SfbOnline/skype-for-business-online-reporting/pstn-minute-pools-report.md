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
description: La nuova area Skype for Business report dell'interfaccia di amministrazione mostra le chiamate e le attività di audioconferenza nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report Skype for Business pool di minuti PSTN per visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
ms.openlocfilehash: 8c69a0555c95a7cb700b31db04103a0f7f502729
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234041"
---
# <a name="pstn-minute-pools-report"></a>Report pool minuti PSTN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>Questo report è disponibile solo per i clienti in anteprima.

La nuova area Skype for Business **report** dell'interfaccia di amministrazione mostra le attività di chiamata e audioconferenza nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, è possibile usare il report Skype for Business pool di minuti **PSTN** per visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
  
Vedere la [panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report Skype for Business, fornisce informazioni dettagliate sulle attività in tutta l'organizzazione. Questi dettagli sono molto utili quando si analizzano, si pianificano e si prendono altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> È possibile visualizzare tutti i report Skype for Business quando si accede come amministratore al interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Come accedere al report dei Skype for Business minuti PSTN

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

- Passare all'interfaccia di amministrazione > **di amministrazione Skype for Business** di amministrazione Report pool di minuti  >    >    >  **PSTN**.
    
> [!NOTE]
> A seconda dell'Microsoft 365 o Office 365 abbonamento, è possibile che non venga visualizzato lo stesso dettaglio illustrato qui. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretare il report Skype for Business pool di minuti PSTN

È possibile ottenere una visualizzazione nel pool di Skype for Business minuti dell'utente esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.

![Skype for Business Report pool di minuti PSTN](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella mostra una suddivisione dei pool di minuti in base alla licenza (funzionalità) e alla posizione di utilizzo. 
*    **La funzionalità** è il piano di licenza/servizio usato per la chiamata. I piani di licenza/servizio che è possibile visualizzare in questo report includono:
     * MCOPSTN1 - Piano per chiamate nazionali (piani UE di 3000 minuti per gli Stati Uniti/1200 minuti)
     * MCOPSTN2 - Piano per chiamate internazionali di & nazionale da cui è possibile vedere una piscina nazionale (3000 minuti usa/Canada/PR, paesi europei di 1200 minuti) e una piscina internazionale (600 minuti). Il limite dei minuti viene raggiunto ogni volta che viene raggiunto il limite internazionale nazionale -OR entro il mese di calendario. 
     * MCOPSTN5 - Piano per chiamate nazionali (piano per chiamate di 120 minuti)
     * MCOPSTN6 - Piano per chiamate nazionali (piano per chiamate di 240 minuti)
     * MCOMEETADD - Audioconferenza
*    **Descrizione funzionalità** è una descrizione del tipo di licenza utilizzato per la chiamata.
*    **Country Minute Pool è** la posizione di utilizzo delle licenze degli utenti che condividono il pool di minuti. 
*    **Minuti usati** è il numero di minuti usati ogni mese.
*    **Totale minuti** è il numero totale di minuti disponibili per il mese. 
*    **Percentuale usata** è la percentuale di minuti usata per il mese. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Skype for Business attività dell'organizzatore della conferenza](conference-organizer-activity-report.md) È possibile vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, Web, /dial out - terze parti e /dial out - Microsoft.
    
- [Skype for Business attività dei partecipanti alla conferenza](conference-participant-activity-report.md) È possibile vedere il numero di conferenze audio, audio/video, condivisione di applicazioni, Web e chiamate in uscita a cui si sta partecipando.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Skype for Business dei dettagli della sessione](session-details-report.md) Puoi visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
