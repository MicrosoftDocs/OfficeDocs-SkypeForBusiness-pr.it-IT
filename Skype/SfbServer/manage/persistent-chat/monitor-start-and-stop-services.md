---
title: Monitorare, avviare e arrestare i servizi chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi di Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814136"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="2f758-103">Monitorare, avviare e arrestare i servizi chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f758-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2f758-104">**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2f758-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2f758-105">I servizi Chat persistente e Conformità chat persistente fanno parte della topologia di Skype for Business Server e possono pertanto essere monitorati, arrestati e avviati utilizzando i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f758-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2f758-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2f758-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2f758-107">Restituisce informazioni dettagliate sui componenti di Skype for Business Server 2015 eseguiti come servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="2f758-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="2f758-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2f758-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2f758-109">Avvia il servizio.</span><span class="sxs-lookup"><span data-stu-id="2f758-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="2f758-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2f758-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2f758-111">Arresta il servizio.</span><span class="sxs-lookup"><span data-stu-id="2f758-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2f758-112">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2f758-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2f758-113">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="2f758-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="2f758-114">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="2f758-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2f758-115">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2f758-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="2f758-116">Per informazioni dettagliate su come utilizzare i cmdlet, vedere [Skype for Business Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="2f758-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

