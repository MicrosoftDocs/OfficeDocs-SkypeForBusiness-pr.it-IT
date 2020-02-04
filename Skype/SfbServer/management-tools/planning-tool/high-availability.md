---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
ms.openlocfilehash: 53b98b72c70fcb624ab59fc7bfc3fbffadbd231a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696291"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
  
Skype for Business Server 2015 richiede almeno due server front-end per consentire l'elevata disponibilità. Lo strumento di pianificazione usa i criteri seguenti per determinare se verranno aggiunti server aggiuntivi per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più server front-end, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene Edge Server, viene aggiunto un altro server. 
    
- Se la distribuzione contiene una chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool. Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool. 
    
Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database. Ad esempio, se c'è un database di SQL Server front-end, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo nome e lo definirà come "database SQL front-end mirror".
  
Per altre informazioni su come preparare l'ambiente per una disponibilità elevata, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

