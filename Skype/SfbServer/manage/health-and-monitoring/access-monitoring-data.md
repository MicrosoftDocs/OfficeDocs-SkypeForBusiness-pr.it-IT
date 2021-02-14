---
title: Accedere ai dati di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Riepilogo: informazioni sui dati di monitoraggio utilizzati in Skype for Business Server.'
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826546"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accedere ai dati di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni sui dati di monitoraggio utilizzati in Skype for Business Server.
  
I dati di monitoraggio sono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dettagli chiamata, e QoEMetrics per i dati QoE. Questi sono normali database, ed è possibile accedere ai dati in essi contenuti tramite tutti gli strumenti solitamente utilizzati per accedere e analizzare i dati di SQL Server.
  
Uno strumento da prendere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è i rapporti di monitoraggio di Skype for Business Server. I rapporti di monitoraggio sono un insieme di report standard pubblicati da Microsoft SQL Server Reporting Service. Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE. I rapporti di monitoraggio vengono forniti con Skype for Business Server e possono essere installati dalla Distribuzione guidata di Skype for Business Server dopo l'installazione e la configurazione del monitoraggio di Skype for Business Server.
  
Monitoring Reports richiede l'utilizzo di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente a SQL Server o dopo l'installazione di SQL Server.
  
Per ulteriori informazioni, vedere l'argomento [Installare i rapporti di monitoraggio in Skype for Business Server.](../../deploy/deploy-monitoring/install-monitoring-reports.md)
  

