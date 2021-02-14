---
title: Installare i componenti di Chat persistente in Skype for Business Server
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
description: 'Riepilogo: leggere questo argomento per informazioni su come usare la Distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802086"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="a7a11-103">Installare i componenti di Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7a11-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7a11-104">**Riepilogo:** Leggere questo argomento per informazioni su come usare la Distribuzione guidata di Skype for Business Server per installare i componenti e i servizi di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7a11-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="a7a11-105">Prima di installare i componenti di Persistent Chat, verificare di aver già installato componenti hardware e software prerequisiti e di aver creato la topologia appropriata per supportare il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a7a11-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="a7a11-106">Per informazioni dettagliate sulla pianificazione e sui requisiti, vedere Requisiti per [l'ambiente Skype for Business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e Pianificare il [server Chat persistente in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="a7a11-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="a7a11-107">Per informazioni su come aggiornare e pubblicare la topologia per includere il server Chat persistente, vedere Aggiungere il server Chat persistente alla topologia di [Skype for Business Server 2015.](add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="a7a11-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="a7a11-108">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a7a11-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a7a11-109">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="a7a11-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="a7a11-110">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="a7a11-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a7a11-111">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7a11-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="a7a11-112">Installare e avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="a7a11-112">Install and start services</span></span>

<span data-ttu-id="a7a11-113">Usando la Distribuzione guidata di Skype for Business Server, scegliere Installa o aggiorna il sistema Skype for Business Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7a11-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="a7a11-114">Installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="a7a11-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="a7a11-115">Installare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7a11-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="a7a11-116">Richiedere, installare o assegnare certificati</span><span class="sxs-lookup"><span data-stu-id="a7a11-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="a7a11-117">Avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="a7a11-117">Start services</span></span>
    
<span data-ttu-id="a7a11-118">Per informazioni dettagliate su come usare la Distribuzione guidata per installare componenti, assegnare certificati e avviare i servizi, vedere Installare [Skype for Business Server 2015](../../deploy/install/install.md) e Installare Skype for Business Server [2015](../../deploy/install/install-skype-for-business-server.md)nei server della topologia.</span><span class="sxs-lookup"><span data-stu-id="a7a11-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

