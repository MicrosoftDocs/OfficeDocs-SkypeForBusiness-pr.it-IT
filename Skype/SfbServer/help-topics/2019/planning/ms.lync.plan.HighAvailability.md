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
description: Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza dei server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819796"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza dei server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
  
Skype for Business Server richiede almeno due Front End Server per abilitare la disponibilità elevata. Lo strumento di pianificazione utilizza i criteri seguenti per determinare se aggiungerà ulteriori server per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene un server perimetrale, viene aggiunto un server aggiuntivo. 
    
- Se la distribuzione contiene Persistent Chat, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool. Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un server aggiuntivo (per un totale di cinque server) ma manterrà un singolo pool. 

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Aggiornamento da Skype for Business a Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 

    
Lo strumento di pianificazione aggiunge inoltre un database SQL mirror per tutti i database. Ad esempio, se è presente un database front-end SQL Server, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo database e lo deno namerà come "Front End mirror SQL database.
  
Per ulteriori informazioni sulla preparazione dell'ambiente per la disponibilità elevata, vedere Pianificare la disponibilità elevata e il ripristino di emergenza [in Skype for Business Server.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  

