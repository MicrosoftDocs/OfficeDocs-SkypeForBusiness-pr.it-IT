---
title: Migrazione di server di archiviazione e Monitoring Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front End. Se tuttavia le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è consigliabile aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione.
ms.openlocfilehash: b1f497019d2043a7ea43c1134af615ae4db6183cd3d16593bfab6e835fa4db32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303550"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione di server di archiviazione e Monitoring Server

Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front End. Se tuttavia le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è consigliabile aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione. 
  
Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:
  
- I dati di archiviazione e i dati di monitoraggio non vengono spostati nella Skype for Business Server 2019. I dati di cui si è fatto il backup prima di rimuovere le autorizzazioni dell'ambiente legacy saranno la cronologia delle attività nell'ambiente legacy.
    
- La versione legacy del server di archiviazione e del Monitoring Server può essere associata solo a un pool Front End legacy. In Skype for Business Server 2019, Archiviazione e monitoraggio non sono più ruoli del server, ma servizi integrati nel pool front-end Skype for Business Server 2019.
    
- Durante la coesistenza delle distribuzioni legacy e Skype for Business Server 2019, la versione legacy di Server di archiviazione e Monitoring Server raccoglie i dati per gli utenti ospitati in pool legacy. L'archiviazione e il monitoraggio Skype for Business Server 2019 raccolgono i dati per gli utenti ospitati Skype for Business Server pool 2019.
    
    > [!NOTE]
    > Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Skype for Business Server 2019, la versione legacy del server di archiviazione continua a raccogliere i dati per gli utenti ospitati nei pool legacy e l'archiviazione in Skype for Business Server 2019 raccoglie i dati per gli utenti ospitati nei pool di Skype for Business Server 2019. 
  
- Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti in combinazione con l'archiviazione e il monitoraggio in Skype for Business Server 2019, consultare il fornitore su quando e come è necessario integrare la soluzione di terze parti con Skype for Business Server 2019.
    

