---
title: Accedere ai dati di monitoraggio Skype for Business Server
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
ms.openlocfilehash: 56b27a372eaef71ee02569a418721e9d2e4b28859a99c20489713a859439217a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336646"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accedere ai dati di monitoraggio Skype for Business Server
 
**Riepilogo:** Informazioni sui dati di monitoraggio usati in Skype for Business Server.
  
I dati di monitoraggio sono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dettagli chiamata, e QoEMetrics per i dati QoE. Questi sono normali database, ed è possibile accedere ai dati in essi contenuti tramite tutti gli strumenti solitamente utilizzati per accedere e analizzare i dati di SQL Server.
  
Uno strumento da prendere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è Skype for Business Server report di monitoraggio. I report di monitoraggio sono un insieme di report standard pubblicati da Microsoft SQL Server Reporting Service. Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE. I report di monitoraggio vengono Skype for Business Server e possono essere installati dalla distribuzione guidata di Skype for Business Server dopo l'installazione Skype for Business Server e la configurazione del monitoraggio.
  
Monitoring Reports richiede l'utilizzo di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente a SQL Server o dopo l'installazione di SQL Server.
  
Per ulteriori informazioni, vedere l'argomento [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

