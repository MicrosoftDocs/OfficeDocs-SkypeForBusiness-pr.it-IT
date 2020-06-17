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
description: Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front end. Tuttavia, se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752668"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione di server di archiviazione e Monitoring Server

Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front end. Tuttavia, se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione. 
  
Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:
  
- I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Skype for Business Server 2019. I dati di cui è stato eseguito il backup prima della rimozione dell'ambiente legacy saranno la cronologia delle attività nell'ambiente legacy.
    
- La versione legacy del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front end legacy. In Skype for Business Server 2019, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Skype for Business Server 2019.
    
- Durante il periodo di coesistenza tra le distribuzioni legacy e Skype for Business Server 2019, la versione legacy del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool legacy. Archiviazione e monitoraggio in Skype for Business Server 2019 raccogliere dati per gli utenti ospitati nei pool Skype for Business Server 2019.
    
    > [!NOTE]
    > Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Skype for Business Server 2019, la versione legacy del server di archiviazione continua a raccogliere dati per gli utenti ospitati in pool legacy e l'archiviazione in Skype for Business Server 2019 raccoglie i dati per gli utenti ospitati nei pool di Skype for Business Server 2019. 
  
- Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme all'archiviazione e al monitoraggio in Skype for Business Server 2019, consultare il fornitore su quando e come integrare la soluzione di terze parti con Skype for Business Server 2019.
    

