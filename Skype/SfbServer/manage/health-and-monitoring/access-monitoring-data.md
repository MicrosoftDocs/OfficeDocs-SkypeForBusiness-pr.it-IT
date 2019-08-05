---
title: Accedere ai dati di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Riepilogo: informazioni sui dati di monitoraggio usati in Skype for Business Server.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195531"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accedere ai dati di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni sui dati di monitoraggio usati in Skype for Business Server.
  
I dati di monitoraggio vengono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dei dettagli delle chiamate e QoEMetrics per la qualità dei dati dell'esperienza. Non c'è niente di speciale in questi due database; Ciò significa che è possibile accedere ai dati archiviati in tali database con uno degli strumenti usati in genere per l'accesso e l'analisi dei dati di SQL Server.
  
Uno strumento da tenere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è il monitoraggio dei report di Skype for Business Server. I report di monitoraggio sono un set di report standard pubblicati da Microsoft SQL Server Reporting Service. Questi report, accessibili tramite un Web browser, consentono l'utilizzo, le informazioni di diagnostica delle chiamate e le informazioni sulla qualità dei contenuti multimediali, tutte basate sui record di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) archiviati nei database CDR e QoE. Il monitoraggio dei report è disponibile con Skype for Business Server e può essere installato dalla distribuzione guidata di Skype for Business Server dopo l'installazione di Skype for Business Server e il monitoraggio è stato configurato.
  
Come notato, il monitoraggio dei report richiede l'uso di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente all'installazione di SQL Server o può essere installato in qualsiasi momento dopo l'installazione di SQL Server.
  
Per altre informazioni, vedere l'argomento [installare report di monitoraggio in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

