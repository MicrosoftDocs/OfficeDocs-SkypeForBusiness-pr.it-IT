---
title: Distribuire video Interop server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Riepilogo: distribuire il ruolo del server VIS in Skype for Business Server.'
ms.openlocfilehash: 790030e3ef0b88473f6fc1750c054db5cdd74b4a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235587"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="e140c-103">Distribuire video Interop server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e140c-104">**Riepilogo:** Distribuire il ruolo del server VIS in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e140c-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="e140c-105">Skype for Business Server ora può essere integrato direttamente con i sistemi di teleconferenza Cisco (VTCs), come Cisco C60 o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="e140c-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="e140c-106">Questo richiede l'introduzione di un nuovo ruolo del server denominato video Interop Server (VIS) e la configurazione corretta sia del VIS che dell'equipaggiamento con cui interagisce.</span><span class="sxs-lookup"><span data-stu-id="e140c-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="e140c-107">Un VTC registra con l'infrastruttura Cisco esistente, ad esempio Cisco Unified Communication Manager (CUCM), e viene usato un trunk SIP video tra CUCM e il pool VIS.</span><span class="sxs-lookup"><span data-stu-id="e140c-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e140c-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e140c-108">In this section</span></span>

<span data-ttu-id="e140c-109">La configurazione dell'interoperabilità tra un server VIS o un pool e sistemi VTC richiede l'esecuzione delle cinque procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="e140c-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="e140c-110">Creare un pool VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="e140c-111">Distribuire il ruolo del server VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="e140c-112">Configurare il server di interoperabilità video in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="e140c-113">Configurare CUCM per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="e140c-114">Configurare un VTC per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="e140c-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e140c-115">Related sections</span></span>

[<span data-ttu-id="e140c-116">Pianificare il video Interop server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e140c-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

