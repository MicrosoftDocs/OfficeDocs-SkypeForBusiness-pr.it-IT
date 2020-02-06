---
title: Monitorare, avviare e arrestare i servizi di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 846d7376e1a3e9bd06ae74c20ee0812c8c78bbeb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817475"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="59fc1-103">Monitorare, avviare e arrestare i servizi di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="59fc1-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59fc1-104">**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59fc1-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="59fc1-105">I servizi di chat persistenti e i servizi di conformità della chat persistente fanno parte della topologia di Skype for Business Server e possono quindi essere monitorati, fermati e avviati usando i seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="59fc1-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="59fc1-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="59fc1-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="59fc1-107">Restituisce informazioni dettagliate sui componenti di Skype for Business Server 2015 che vengono eseguiti come servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="59fc1-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="59fc1-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="59fc1-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="59fc1-109">Avvia il servizio.</span><span class="sxs-lookup"><span data-stu-id="59fc1-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="59fc1-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="59fc1-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="59fc1-111">Arresta il servizio.</span><span class="sxs-lookup"><span data-stu-id="59fc1-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="59fc1-112">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="59fc1-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="59fc1-113">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="59fc1-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="59fc1-114">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="59fc1-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="59fc1-115">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59fc1-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="59fc1-116">Per informazioni dettagliate su come usare i cmdlet, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="59fc1-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

