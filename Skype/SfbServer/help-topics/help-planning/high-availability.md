---
title: Skype for Business Server Strumento di pianificazione a disponibilità elevata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: 8fe42fb60d6588eee7a62ec49aa33f46c9a2e535
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596750"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>Skype for Business Server Strumento di pianificazione a disponibilità elevata
 
Lo schema principale di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
  
Skype for Business Server 2015 richiede almeno due Front End Server per abilitare la disponibilità elevata. Lo strumento di pianificazione utilizza i criteri seguenti per determinare se aggiungerà ulteriori server per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene server perimetrali, viene aggiunto un altro server. 
    
- Se la distribuzione contiene Persistent Chat, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero di pool. Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server) ma manterrà un singolo pool. 
    
Lo strumento di pianificazione aggiunge inoltre un database SQL mirror per tutti i database. Ad esempio, se è presente un database front-end SQL Server, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo database e lo deno namerà come "Database SQL mirror front-end.
  
Per ulteriori informazioni sulla preparazione dell'ambiente per la disponibilità elevata, vedere [Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  

