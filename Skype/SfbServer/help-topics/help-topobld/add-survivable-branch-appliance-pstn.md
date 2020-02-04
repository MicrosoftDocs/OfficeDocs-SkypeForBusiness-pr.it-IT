---
title: Aggiungere l'indirizzo PSTN di Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue:'
ms.openlocfilehash: d5ba39a79f7810a64776efcd7b7c47488fe93d2b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697951"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="f7945-103">Aggiungere l'indirizzo PSTN di Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f7945-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="f7945-104">Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7945-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="f7945-105">Un nome di dominio completo (FQDN) o un indirizzo IP per il peer del gateway a cui è associato il Survivable Branch Appliance o Survivable Branch Server per il routing delle chiamate PSTN in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="f7945-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7945-106">Se si definisce un Survivable Branch Appliance, si tratta del gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="f7945-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="f7945-p101">La porta di attesa da utilizzare per i messaggi SIP (Session Initiation Protocol). Per impostazione predefinita, le porte sono la 5066 per TCP (Transmission Control Protocol) e la 5067 per TLS (Transport Layer Security) in un gateway, un centralino (PBX) o un Session Border Controller (SBC). In un Survivable Branch Appliance presso un sito di succursale le porte predefinite sono la 5081 per TCP e la 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="f7945-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="f7945-110">Per motivi di sicurezza, è consigliabile utilizzare TLS.</span><span class="sxs-lookup"><span data-stu-id="f7945-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="f7945-111">Se si definisce un Survivable Branch Appliance, vedere la documentazione del fornitore di Survivable Branch Appliance per verificare che il Survivable Branch Appliance supporti il protocollo TLS.</span><span class="sxs-lookup"><span data-stu-id="f7945-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7945-112">Per motivi di sicurezza, è consigliabile distribuire un gateway che supporti TLS.</span><span class="sxs-lookup"><span data-stu-id="f7945-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7945-113">Se si vuole aggiungere un gateway PSTN, sarà possibile configurarlo in un secondo momento, ma la funzionalità sarà limitata finché il gateway PSTN non verrà definito e configurato.</span><span class="sxs-lookup"><span data-stu-id="f7945-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

