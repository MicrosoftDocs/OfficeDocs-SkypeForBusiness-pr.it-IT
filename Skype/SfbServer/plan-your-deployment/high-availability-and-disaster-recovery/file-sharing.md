---
title: Disponibilità elevata per la condivisione di file in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informazioni su come garantire la disponibilità elevata delle condivisioni file in Skype for Business Server, usando DFS.
ms.openlocfilehash: e0af97da0bfc5a6ddb07284943640511e0dc06ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859873"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Disponibilità elevata per la condivisione di file in Skype for Business Server
 
Informazioni su come garantire la disponibilità elevata delle condivisioni file in Skype for Business Server, usando DFS.
  
Per garantire la disponibilità elevata per la condivisione di file nella distribuzione Skype for Business Server, è possibile utilizzare DFS (Distributed File System). DFS supporta il failover da un file server a un altro all'interno dello stesso data center. Per una distribuzione su larga scala, è consigliabile utilizzare file server dedicati accoppiati mediante DFS. Per ulteriori informazioni su DFS in Windows Server 2012, vedere [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) . Per informazioni su DFS in Windows Server 2008, vedere [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .
  
A seconda delle dimensioni della rete e del grado di resilienza desiderato, è possibile utilizzare una coppia di server per ospitare tutte le condivisioni file in un sito oppure utilizzare una coppia per ogni pool Front End.
  
DFS è un meccanismo che esegue la replica nel miglior modo possibile in base alle condizioni esistenti, senza alcun impegno pubblicato relativamente al raggiungimento degli obiettivi in termini di tempo di ripristino (RTO, Recovery Time Objective) o di punto di ripristino (RPO, Recovery Point Objective). Un failover tra server DFS deve essere completato rapidamente, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando si verifica il failover.
  
Se si utilizza DFS e l'archivio dati nella condivisione file è fondamentale, è consigliabile eseguire frequentemente il backup delle condivisioni file, ad esempio ogni 4-8 ore. Quando una condivisione file non è più attiva e la replica non è aggiornata, è possibile utilizzare il backup per ripristinare il contenuto del server con problemi nell'altro server accoppiato al server attualmente non disponibile.
