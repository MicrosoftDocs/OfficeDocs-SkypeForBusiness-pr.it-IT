---
title: Distribuire Video Interop Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Riepilogo: distribuire il ruolo del server VIS in Skype for Business Server.'
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801956"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="19d28-103">Distribuire Video Interop Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="19d28-104">**Riepilogo:** Distribuire il ruolo del server VIS in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19d28-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="19d28-105">Skype for Business Server può ora integrarsi direttamente con i sistemi di teleconferenza Cisco (VTC), ad esempio Cisco C60 o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="19d28-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="19d28-106">Ciò richiede l'introduzione di un nuovo ruolo del server denominato Video Interop Server (VIS) e la corretta configurazione del VIS e delle attrezzature con cui interagisce.</span><span class="sxs-lookup"><span data-stu-id="19d28-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="19d28-107">Un VTC viene registrato con l'infrastruttura Cisco esistente, ad esempio Cisco Unified Communication Manager (CUCM), e viene utilizzato un trunk SIP video tra LAM e il pool VIS.</span><span class="sxs-lookup"><span data-stu-id="19d28-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="19d28-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="19d28-108">In this section</span></span>

<span data-ttu-id="19d28-109">La configurazione dell'interoperabilità tra un server o un pool VIS e sistemi VTC richiede l'esecuzione delle cinque procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="19d28-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="19d28-110">Creare un pool VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="19d28-111">Distribuire il ruolo del server VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="19d28-112">Configurare Video Interop Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="19d28-113">Configurare CUCM per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="19d28-114">Configurare un VTC per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="19d28-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="19d28-115">Related sections</span></span>

[<span data-ttu-id="19d28-116">Pianificare Video Interop Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19d28-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

