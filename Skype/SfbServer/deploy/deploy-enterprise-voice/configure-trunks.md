---
title: Configurare Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Riepilogo: informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233852"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="f6c4c-103">Configurare Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6c4c-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="f6c4c-104">**Riepilogo:** Informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f6c4c-105">Come parte della distribuzione VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="f6c4c-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="f6c4c-106">Connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="f6c4c-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="f6c4c-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f6c4c-107">PSTN gateway</span></span>
    
- <span data-ttu-id="f6c4c-108">PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="f6c4c-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="f6c4c-109">Per altre informazioni, Vedi [pianificare la connettività PSTN in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="f6c4c-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="f6c4c-110">La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="f6c4c-111">Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="f6c4c-112">Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).</span><span class="sxs-lookup"><span data-stu-id="f6c4c-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="f6c4c-113">Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario prima di tutto definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="f6c4c-114">Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="f6c4c-115">Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="f6c4c-116">In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="f6c4c-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="f6c4c-117">Quando viene definito un trunk, deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="f6c4c-118">Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="f6c4c-119">Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Skype for Business Server, dove Trunks può essere associato alle route.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="f6c4c-120">Il nome del trunk semplice viene usato come nome del gateway da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="f6c4c-121">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="f6c4c-122">In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="f6c4c-123">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f6c4c-123">Specify the default gateway for the Mediation Server.</span></span> 
  

