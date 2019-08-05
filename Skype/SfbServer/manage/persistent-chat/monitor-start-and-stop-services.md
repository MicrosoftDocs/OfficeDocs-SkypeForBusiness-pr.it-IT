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
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36196010"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="fe173-103">Monitorare, avviare e arrestare i servizi di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="fe173-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fe173-104">**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fe173-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fe173-105">I servizi di chat persistenti e i servizi di conformità della chat persistente fanno parte della topologia di Skype for Business Server e possono quindi essere monitorati, fermati e avviati usando i seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fe173-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fe173-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="fe173-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="fe173-107">Restituisce informazioni dettagliate sui componenti di Skype for Business Server 2015 che vengono eseguiti come servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="fe173-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="fe173-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="fe173-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="fe173-109">Avvia il servizio.</span><span class="sxs-lookup"><span data-stu-id="fe173-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="fe173-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="fe173-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="fe173-111">Arresta il servizio.</span><span class="sxs-lookup"><span data-stu-id="fe173-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="fe173-112">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fe173-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fe173-113">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="fe173-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="fe173-114">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="fe173-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="fe173-115">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fe173-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="fe173-116">Per informazioni dettagliate su come usare i cmdlet, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="fe173-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

