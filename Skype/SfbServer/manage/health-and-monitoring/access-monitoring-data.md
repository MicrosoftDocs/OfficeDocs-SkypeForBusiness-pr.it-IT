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
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="141fa-103">Accedere ai dati di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="141fa-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="141fa-104">**Riepilogo:** Informazioni sui dati di monitoraggio utilizzati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="141fa-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="141fa-p101">I dati di monitoraggio sono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dettagli chiamata, e QoEMetrics per i dati QoE. Questi sono normali database, ed è possibile accedere ai dati in essi contenuti tramite tutti gli strumenti solitamente utilizzati per accedere e analizzare i dati di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="141fa-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="141fa-107">Uno strumento da prendere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è i rapporti di monitoraggio di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="141fa-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="141fa-108">I rapporti di monitoraggio sono un insieme di report standard pubblicati da Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="141fa-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="141fa-109">Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="141fa-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="141fa-110">I rapporti di monitoraggio vengono forniti con Skype for Business Server e possono essere installati dalla Distribuzione guidata di Skype for Business Server dopo l'installazione e la configurazione del monitoraggio di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="141fa-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="141fa-p103">Monitoring Reports richiede l'utilizzo di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente a SQL Server o dopo l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="141fa-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="141fa-113">Per ulteriori informazioni, vedere l'argomento [Installare i rapporti di monitoraggio in Skype for Business Server.](../../deploy/deploy-monitoring/install-monitoring-reports.md)</span><span class="sxs-lookup"><span data-stu-id="141fa-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

