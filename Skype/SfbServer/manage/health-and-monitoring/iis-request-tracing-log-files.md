---
title: Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Riepilogo: informazioni sul servizio mobilità (MCX) nel supporto di Skype for Business Server 2015 per i client legacy.'
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992181"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="d7069-103">Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d7069-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d7069-104">**Riepilogo:** Informazioni sul servizio mobilità (MCX) nel supporto di Skype for Business Server 2015 per i client legacy.</span><span class="sxs-lookup"><span data-stu-id="d7069-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="d7069-105">Questo argomento si applica alle distribuzioni che supportano solo client Lync 2010 Lync mobile ed è destinato al servizio mobilità (MCX).</span><span class="sxs-lookup"><span data-stu-id="d7069-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="d7069-106">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d7069-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d7069-107">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="d7069-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d7069-108">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="d7069-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="d7069-109">Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio mobilità di Skype for Business Server (MCX), i file di log generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno.</span><span class="sxs-lookup"><span data-stu-id="d7069-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="d7069-110">La registrazione della traccia di IIS è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d7069-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="d7069-111">È consigliabile monitorare i server front-end per assicurarsi che non finiscano nello spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="d7069-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="d7069-112">Per impostazione predefinita, IIS archivia i file di log in%SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="d7069-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="d7069-113">Per disattivare la traccia delle richieste di IIS per un intero server, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d7069-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="d7069-114">Per informazioni dettagliate sul comando **HttpLogging** , Vedi [la pagina di riferimento del comando](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="d7069-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

