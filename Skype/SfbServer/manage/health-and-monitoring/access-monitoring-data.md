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
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="97c8d-103">Accedere ai dati di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="97c8d-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="97c8d-104">**Riepilogo:** Informazioni sui dati di monitoraggio usati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="97c8d-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="97c8d-105">I dati di monitoraggio vengono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dei dettagli delle chiamate e QoEMetrics per la qualità dei dati dell'esperienza.</span><span class="sxs-lookup"><span data-stu-id="97c8d-105">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data.</span></span> <span data-ttu-id="97c8d-106">Non c'è niente di speciale in questi due database; Ciò significa che è possibile accedere ai dati archiviati in tali database con uno degli strumenti usati in genere per l'accesso e l'analisi dei dati di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97c8d-106">There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="97c8d-107">Uno strumento da tenere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è il monitoraggio dei report di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="97c8d-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="97c8d-108">I report di monitoraggio sono un set di report standard pubblicati da Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="97c8d-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="97c8d-109">Questi report, accessibili tramite un Web browser, consentono l'utilizzo, le informazioni di diagnostica delle chiamate e le informazioni sulla qualità dei contenuti multimediali, tutte basate sui record di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) archiviati nei database CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="97c8d-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="97c8d-110">Il monitoraggio dei report è disponibile con Skype for Business Server e può essere installato dalla distribuzione guidata di Skype for Business Server dopo l'installazione di Skype for Business Server e il monitoraggio è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="97c8d-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="97c8d-111">Come notato, il monitoraggio dei report richiede l'uso di SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="97c8d-111">As noted, Monitoring Reports requires the use of SQL Server Reporting Service.</span></span> <span data-ttu-id="97c8d-112">SQL Server Reporting Service può essere installato contemporaneamente all'installazione di SQL Server o può essere installato in qualsiasi momento dopo l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97c8d-112">SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="97c8d-113">Per altre informazioni, vedere l'argomento [installare report di monitoraggio in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span><span class="sxs-lookup"><span data-stu-id="97c8d-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

