---
title: Migrazione dei server di archiviazione e monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se il server di archiviazione e il server di monitoraggio sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo la migrazione dei pool Front-end. Se le funzionalità di archiviazione e monitoraggio sono critiche per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool di piloti di Skype for Business Server 2019 prima della migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195011"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione dei server di archiviazione e monitoraggio

Se il server di archiviazione e il server di monitoraggio sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo la migrazione dei pool Front-end. Se le funzionalità di archiviazione e monitoraggio sono critiche per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool di piloti di Skype for Business Server 2019 prima della migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione. 
  
Per le funzionalità di archiviazione e monitoraggio durante il processo di migrazione, tieni presenti le considerazioni seguenti:
  
- L'archiviazione dei dati e il monitoraggio dei dati non vengono spostati nella distribuzione di Skype for Business Server 2019. I dati di cui eseguire il backup prima della disattivazione dell'ambiente legacy saranno la cronologia delle attività nell'ambiente legacy.
    
- La versione legacy del server di archiviazione e del server di monitoraggio può essere associata solo a un pool di front end legacy. In Skype for Business Server 2019 l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi integrati nel pool di front end Skype for Business Server 2019.
    
- Durante il periodo in cui le distribuzioni legacy e Skype for Business Server 2019 coesistono, la versione legacy di Archiving Server e Monitoring Server raccolgono dati per gli utenti ospitati in pool legacy. Archiviazione e monitoraggio in Skype for Business Server 2019 raccogliere dati per gli utenti residenti nei pool Skype for Business Server 2019.
    
    > [!NOTE]
    > Durante la fase di migrazione quando si usa ancora il server perimetrale legacy con il nuovo pool di piloti di Skype for Business Server 2019, la versione legacy del server di archiviazione continua a raccogliere dati per gli utenti ospitati in pool legacy ed archiviati in Skype for business Server 2019 raccoglie i dati per gli utenti ospitati nei pool Skype for Business Server 2019. 
  
- Se si usa una soluzione di archiviazione e monitoraggio di terze parti in combinazione con l'archiviazione e il monitoraggio in Skype for Business Server 2019, consultare il fornitore in merito a quando e come integrare la soluzione di terze parti con Skype for Business Server 2019.
    

