---
title: Avviare servizi (Invoke)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: Il riquadro Riepilogo nel riquadro comandi in esecuzione consente di visualizzare lo stato delle attività emesse per avviare i servizi per il server dei ruoli di Skype for Business Server che si sta distribuendo.
ms.openlocfilehash: 3f1f19de0e591b23181c9e711991a2b9d99f9b4a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705281"
---
# <a name="start-services-invoke"></a><span data-ttu-id="92bc7-103">Avviare servizi (Invoke)</span><span class="sxs-lookup"><span data-stu-id="92bc7-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="92bc7-104">Il riquadro Riepilogo nel riquadro **comandi in esecuzione** consente di visualizzare lo stato delle attività emesse per avviare i servizi per il server dei ruoli di Skype for Business Server che si sta distribuendo.</span><span class="sxs-lookup"><span data-stu-id="92bc7-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="92bc7-105">Il riepilogo nel riquadro attività non rappresenta un'indicazione in tempo reale dell'avvio dei servizi.</span><span class="sxs-lookup"><span data-stu-id="92bc7-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="92bc7-106">Alcuni dei servizi di Skype for Business Server possono richiedere un tempo prolungato per iniziare il processo di avvio iniziale.</span><span class="sxs-lookup"><span data-stu-id="92bc7-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="92bc7-107">Le attività inviano il comando di avvio, ma non determinano se il servizio viene poi avviato.</span><span class="sxs-lookup"><span data-stu-id="92bc7-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="92bc7-108">Se si desidera monitorare l'avvio e lo stato del servizio, è consigliabile utilizzare Microsoft Management Console (MMC) nei servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="92bc7-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="92bc7-p102">Sotto il riquadro attività è disponibile un elenco a discesa in cui è incluso il file di registro **Avvio servizi**. Per visualizzare il file di registro, fare clic su **Visualizza registro**. Fare clic su **Fine** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="92bc7-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

