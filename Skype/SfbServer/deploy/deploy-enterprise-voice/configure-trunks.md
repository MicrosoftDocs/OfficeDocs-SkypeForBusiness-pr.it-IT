---
title: Configurare i trunk in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Riepilogo: informazioni su come configurare un trunk tra un Mediation Server e peer per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824956"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="ac3f2-103">Configurare i trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ac3f2-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="ac3f2-104">**Riepilogo:** Informazioni su come configurare un trunk tra un Mediation Server e peer per VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ac3f2-105">Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="ac3f2-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="ac3f2-106">Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="ac3f2-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="ac3f2-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="ac3f2-107">PSTN gateway</span></span>
    
- <span data-ttu-id="ac3f2-108">Centralino (PBX)</span><span class="sxs-lookup"><span data-stu-id="ac3f2-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="ac3f2-109">Per ulteriori dettagli, vedere [Pianificare la connettività PSTN in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="ac3f2-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="ac3f2-110">La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="ac3f2-111">Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="ac3f2-112">Utilizzare generatore di topologie per associare gateway a Mediation Server, ovvero trunk.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="ac3f2-113">Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario innanzitutto definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="ac3f2-114">Un trunk è costituito dall'associazione seguente: nome di dominio completo (FQDN) di Mediation Server, porta di attesa del Mediation Server, FQDN del gateway e porta di attesa del gateway.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="ac3f2-115">Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="ac3f2-116">In questo modo si garantisce una resilienza aggiuntiva all'infrastruttura di VoIP aziendale, che risulta particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="ac3f2-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="ac3f2-117">Dopo essere stato definito, il trunk deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="ac3f2-118">Per associare un trunk a una route, è necessario definire un nome semplice per il trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="ac3f2-119">Questo nome semplice viene utilizzato come nome del trunk nel Pannello di controllo di Skype for Business Server, dove i trunk possono essere associati alle route.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="ac3f2-120">Il nome del trunk semplice viene utilizzato come nome del gateway da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="ac3f2-121">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="ac3f2-122">In Generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="ac3f2-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="ac3f2-123">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ac3f2-123">Specify the default gateway for the Mediation Server.</span></span> 
  

