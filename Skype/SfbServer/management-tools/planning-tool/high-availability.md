---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: b50ccf145f1197531fe91218d2e99c8b0739c15c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834746"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
  
Skype for Business Server 2015 richiede almeno due front end server per poter abilitare la disponibilità elevata. Lo strumento di pianificazione utilizza i seguenti criteri per determinare se verranno aggiunti altri server per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene server perimetrale, viene aggiunto un altro server. 
    
- Se la distribuzione contiene chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool. Ad esempio, se nella distribuzione sono già presenti quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool. 
    
Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database. Ad esempio, se è presente un database front-end di SQL Server, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo e lo definirà come "database SQL front-end mirror.
  
Per ulteriori informazioni sulla preparazione dell'ambiente per la disponibilità elevata, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

