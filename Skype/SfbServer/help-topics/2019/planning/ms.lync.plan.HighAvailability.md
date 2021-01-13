---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819796"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
  
Skype for Business Server richiede almeno due front end server per poter abilitare la disponibilità elevata. Lo strumento di pianificazione utilizza i seguenti criteri per determinare se verranno aggiunti altri server per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene server perimetrale, viene aggiunto un altro server. 
    
- Se la distribuzione contiene chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool. Ad esempio, se nella distribuzione sono già presenti quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool. 

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [aggiornamento di Skype for business to Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a utilizzare Skype for Business Server 2015. 

    
Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database. Ad esempio, se è presente un database front-end di SQL Server, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo e lo definirà come "database SQL front-end mirror.
  
Per ulteriori informazioni sulla preparazione dell'ambiente per la disponibilità elevata, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

