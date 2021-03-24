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
description: Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093314"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
  
Skype for Business Server richiede almeno due Front End Server per abilitare la disponibilità elevata. Lo strumento di pianificazione utilizza i criteri seguenti per determinare se aggiungerà ulteriori server per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene server perimetrali, viene aggiunto un server aggiuntivo. 
    
- Se la distribuzione contiene Persistent Chat, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero di pool. Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un server aggiuntivo (per un totale di cinque server) ma manterrà un singolo pool. 

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Aggiornamento da Skype for Business a Microsoft Teams.](/MicrosoftTeams/upgrade-start-here) Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 

    
Lo strumento di pianificazione aggiunge inoltre un database SQL mirror per tutti i database. Ad esempio, se è presente un database di SQL Server Front End, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo database e lo deno namerà come "Database SQL mirror front-end.
  
Per ulteriori dettagli sulla preparazione dell'ambiente per la disponibilità elevata, vedere [Plan for high availability and disaster recovery in Skype for Business Server.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
