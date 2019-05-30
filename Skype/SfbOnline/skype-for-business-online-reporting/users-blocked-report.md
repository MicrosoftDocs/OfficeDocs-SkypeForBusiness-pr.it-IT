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
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "Questo report, insieme ad altri report di Skype for business, fornisce informazioni dettagliate sull'attività, incluso l'utilizzo PSTN nell'organizzazione. "
ms.openlocfilehash: 77ce7a5ff05c4302be875a16519c2dc1a3a994de
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494006"
---
# <a name="users-blocked-report"></a>Report utenti bloccati

Il nuovo dashboard **report** di Skype for business Mostra la panoramica delle attività in tutti i prodotti Skype for business dell'organizzazione. Consente di eseguire il drill-up dei singoli report a livello di prodotto per ottenere informazioni più dettagliate sulle attività all'interno di ogni prodotto. Ad esempio, puoi usare il report **utenti bloccati di Skype for business** per vedere gli utenti dell'organizzazione bloccati dall'esecuzione di chiamate PSTN. Questo report, insieme ad altri report di Skype for business, fornisce informazioni dettagliate sull'attività, incluso l'utilizzo PSTN nell'organizzazione.
  
 Vedere la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for business quando si accede come amministratore all'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Come ottenere il report bloccati degli utenti di Skype for business

![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**

- Accedere all'interfaccia di amministrazione di **Office 365** > **** > per gli amministratori dell'interfaccia di amministrazione di**Skype for business** > **segnala** > **gli utenti bloccati**.
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretare il report degli utenti di Skype for business bloccati

Per visualizzare gli utenti bloccati, è possibile osservare tutte le colonne visualizzate.
  
Questo è l'aspetto del report. 
  
![Report utenti bloccati](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

La tabella mostra una ripartizione di tutti gli utenti bloccati dall'esecuzione di chiamate. In questo articolo vengono assegnati tutti gli utenti con sistema telefonico o audioconferenza. È possibile aggiungere/rimuovere colonne dalla tabella.
***
![Numero 1](../images/sfbcallout1.png)
*   **ID utente** è l'accesso dell'utente.
*   **Numero di telefono** è il numero assegnato a un utente. 
*   **Blocca il tempo di azione** è l'ora UTC in cui l'utente è stato bloccato dall'esecuzione delle chiamate.
*   **Azione blocca** è il tipo di azione che è stata eseguita per bloccare l'utente.
*   Il **motivo dell'azione blocca** è il motivo per cui l'utente è stato bloccato dall'esecuzione delle chiamate.
***
![Numero 2](../images/sfbcallout2.png)<br/>
Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
***
![Numero 3](../images/sfbcallout3.png)<br/>
È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se si hanno meno di 2000 utenti, è possibile ordinare e filtrare all'interno della tabella nel report stesso. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività partecipante di conferenze di Skype for business](conference-participant-activity-report.md) Puoi vedere il numero di partecipazioni a conferenze di messaggistica istantanea, audio/video, condivisione applicazioni, Web e accesso esterno in entrata/uscita.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Report sull'utilizzo PSTN di Skype for business](pstn-usage-report.md) È possibile visualizzare il numero di minuti di chiamate in ingresso/in uscita e il costo per queste chiamate.

- [Report pool di minuti PSTN di Skype for business](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report Dettagli sessione di Skype for business](session-details-report.md) È possibile visualizzare i dettagli sulle singole esperienze delle chiamate degli utenti.
   
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 