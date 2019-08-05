---
title: Installare i componenti di Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Riepilogo: leggere questo argomento per informazioni su come usare la distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.'
ms.openlocfilehash: 2b19599ff3523a1b96a2349d62c948ed3fe72d7b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195942"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="bd5ac-103">Installare i componenti di Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="bd5ac-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bd5ac-104">**Riepilogo:** Leggere questo argomento per informazioni su come usare la distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="bd5ac-105">Prima di installare i componenti della chat persistente, accertarsi di avere già installato hardware e software prerequisito e aver creato la topologia appropriata per supportare il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="bd5ac-106">Per informazioni dettagliate sulla pianificazione e i requisiti, vedere [requisiti per l'ambiente Skype for business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e [pianificare il server di chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd5ac-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="bd5ac-107">Per informazioni su come aggiornare e pubblicare la topologia per includere il server di chat persistente, vedere [aggiungere il server di chat persistente alla topologia di Skype for Business server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd5ac-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="bd5ac-108">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bd5ac-109">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="bd5ac-110">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="bd5ac-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="bd5ac-111">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="bd5ac-112">Installare e avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="bd5ac-112">Install and start services</span></span>

<span data-ttu-id="bd5ac-113">Usando la distribuzione guidata di Skype for Business Server, scegliere Install o Update Skype for Business Server System per eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bd5ac-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="bd5ac-114">Installare un archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="bd5ac-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="bd5ac-115">Installare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bd5ac-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="bd5ac-116">Richiedere, installare o assegnare certificati</span><span class="sxs-lookup"><span data-stu-id="bd5ac-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="bd5ac-117">Avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="bd5ac-117">Start services</span></span>
    
<span data-ttu-id="bd5ac-118">Per informazioni dettagliate su come usare la distribuzione guidata per installare i componenti, assegnare certificati e avviare i servizi, vedere [installare Skype for Business server 2015](../../deploy/install/install.md) e [installare Skype for Business Server 2015 nei server](../../deploy/install/install-skype-for-business-server.md)della topologia.</span><span class="sxs-lookup"><span data-stu-id="bd5ac-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

