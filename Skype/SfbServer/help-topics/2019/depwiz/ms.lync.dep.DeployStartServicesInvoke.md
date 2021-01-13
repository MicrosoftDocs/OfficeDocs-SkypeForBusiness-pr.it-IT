---
title: Avviare servizi (Invoke)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: Nel riquadro dei comandi in esecuzione del riquadro di riepilogo viene visualizzato lo stato delle attività emesse per avviare i servizi per il server di ruoli di Skype for Business Server che si sta distribuendo.
ms.openlocfilehash: 34e128fd5c879c80e3e3eb242cd654b19c5f6dd3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808776"
---
# <a name="start-services-invoke"></a><span data-ttu-id="e6f28-103">Avviare servizi (Invoke)</span><span class="sxs-lookup"><span data-stu-id="e6f28-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="e6f28-104">Nel riquadro dei comandi in **esecuzione** del riquadro di riepilogo viene visualizzato lo stato delle attività emesse per avviare i servizi per il server di ruoli di Skype for Business Server che si sta distribuendo.</span><span class="sxs-lookup"><span data-stu-id="e6f28-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="e6f28-105">Il riepilogo nel riquadro attività task non rappresenta un'indicazione in tempo reale dell'avvio dei servizi.</span><span class="sxs-lookup"><span data-stu-id="e6f28-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="e6f28-106">Alcuni dei servizi di Skype for Business Server possono richiedere un tempo prolungato per iniziare il processo di avvio iniziale.</span><span class="sxs-lookup"><span data-stu-id="e6f28-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="e6f28-107">Le attività inviano il comando di avvio, ma non determinano se il servizio viene poi avviato.</span><span class="sxs-lookup"><span data-stu-id="e6f28-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="e6f28-108">Se si desidera monitorare l'avvio e lo stato del servizio, è consigliabile utilizzare Microsoft Management Console (MMC) nei servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="e6f28-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="e6f28-p102">Sotto il riquadro attività è disponibile un elenco a discesa in cui è incluso il file di registro **Avvio servizi**. Per visualizzare il file di registro, fare clic su **Visualizza registro**. Fare clic su **Fine** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="e6f28-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

