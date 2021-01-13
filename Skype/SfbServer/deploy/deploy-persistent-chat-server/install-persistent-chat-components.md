---
title: Installare i componenti di chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Riepilogo: leggere questo argomento per informazioni su come utilizzare la distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802086"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="59a4c-103">Installare i componenti di chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59a4c-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59a4c-104">**Riepilogo:** Leggere questo argomento per informazioni su come utilizzare la distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59a4c-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="59a4c-105">Prima di installare i componenti di chat persistente, accertarsi di aver già installato l'hardware e il software prerequisito e aver creato la topologia appropriata per supportare il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="59a4c-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="59a4c-106">Per informazioni dettagliate sulla pianificazione e i requisiti, vedere [requirements for your Skype for Business Environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="59a4c-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="59a4c-107">Per informazioni su come aggiornare e pubblicare la topologia in modo da includere il server Chat persistente, vedere [Add Persistent Chat Server to your Skype for Business server 2015 topologia](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="59a4c-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="59a4c-108">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="59a4c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="59a4c-109">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="59a4c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="59a4c-110">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="59a4c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="59a4c-111">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59a4c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="59a4c-112">Installare e avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="59a4c-112">Install and start services</span></span>

<span data-ttu-id="59a4c-113">Se si utilizza la distribuzione guidata di Skype for Business Server, scegliere Install or Update Skype for Business Server System per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="59a4c-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="59a4c-114">Installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="59a4c-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="59a4c-115">Installare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59a4c-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="59a4c-116">Richiedere, installare o assegnare certificati</span><span class="sxs-lookup"><span data-stu-id="59a4c-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="59a4c-117">Avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="59a4c-117">Start services</span></span>
    
<span data-ttu-id="59a4c-118">Per informazioni dettagliate su come utilizzare la distribuzione guidata per installare i componenti, assegnare i certificati e avviare i servizi, vedere [Install Skype for Business server 2015](../../deploy/install/install.md) e [Install Skype for Business Server 2015 nei server della topologia](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="59a4c-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

