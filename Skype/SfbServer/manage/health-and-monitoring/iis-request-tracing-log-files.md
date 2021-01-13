---
title: Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015
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
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili (MCX) in Skype for Business Server 2015 supporto per i client legacy.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823506"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="2d76f-103">Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d76f-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d76f-104">**Riepilogo:** Informazioni sul servizio per dispositivi mobili (MCX) in Skype for Business Server 2015 supporto per i client legacy.</span><span class="sxs-lookup"><span data-stu-id="2d76f-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="2d76f-105">Questo argomento si applica alle distribuzioni che supportano solo client Lync 2010 Lync mobile ed è progettato per il servizio per dispositivi mobili (MCX).</span><span class="sxs-lookup"><span data-stu-id="2d76f-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="2d76f-106">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2d76f-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2d76f-107">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="2d76f-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2d76f-108">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="2d76f-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="2d76f-109">Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio per dispositivi mobili di Skype for Business Server (MCX), i file di registro generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno.</span><span class="sxs-lookup"><span data-stu-id="2d76f-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="2d76f-110">La registrazione della traccia IIS è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2d76f-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="2d76f-111">È necessario monitorare i Front End Server per assicurarsi che non si esaurisca lo spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="2d76f-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="2d76f-112">Per impostazione predefinita, in IIS i file di registro vengono archiviati in %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="2d76f-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="2d76f-113">Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="2d76f-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="2d76f-114">Per informazioni dettagliate sul comando **HttpLogging** , vedere [la Guida di riferimento al comando](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="2d76f-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

