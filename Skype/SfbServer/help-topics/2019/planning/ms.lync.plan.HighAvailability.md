---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
ms.openlocfilehash: 328d269e6d6694dc26be66bd3894094770562726
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797177"
---
# <a name="high-availability-planning-tool"></a>Disponibilità elevata (strumento di pianificazione)
 
Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
  
Skype for Business Server richiede almeno due server front-end per consentire l'elevata disponibilità. Lo strumento di pianificazione usa i criteri seguenti per determinare se verranno aggiunti server aggiuntivi per supportare la disponibilità elevata:
  
- Se la distribuzione contiene due o più server front-end, lo strumento di pianificazione non aggiunge un server aggiuntivo.
    
- Se la distribuzione contiene Edge Server, viene aggiunto un altro server. 
    
- Se la distribuzione contiene una chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool. Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool. 

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, Vedi [aggiornamento di Skype for business a Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

    
Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database. Ad esempio, se c'è un database di SQL Server front-end, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo nome e lo definirà come "database SQL front-end mirror".
  
Per altre informazioni su come preparare l'ambiente per una disponibilità elevata, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

