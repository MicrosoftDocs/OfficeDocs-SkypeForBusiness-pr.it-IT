---
title: Supporto di più trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX. Utilizzare generatore di topologie per associare gateway a Mediation Server, ovvero trunk.
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826226"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="d24a4-105">Supporto di più trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d24a4-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="d24a4-106">La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d24a4-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="d24a4-107">Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d24a4-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="d24a4-108">Utilizzare generatore di topologie per associare gateway a Mediation Server, ovvero trunk.</span><span class="sxs-lookup"><span data-stu-id="d24a4-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="d24a4-109">Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario innanzitutto definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d24a4-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="d24a4-110">Un trunk è costituito dall'associazione seguente: nome di dominio completo (FQDN) di Mediation Server, porta di attesa del Mediation Server, FQDN del gateway e porta di attesa del gateway.</span><span class="sxs-lookup"><span data-stu-id="d24a4-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="d24a4-111">Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d24a4-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="d24a4-112">In questo modo si garantisce una resilienza aggiuntiva all'infrastruttura di VoIP aziendale, che risulta particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="d24a4-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="d24a4-113">Dopo essere stato definito, il trunk deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="d24a4-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="d24a4-114">Per associare un trunk a una route, è necessario definire un nome semplice per il trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d24a4-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="d24a4-115">Questo nome semplice viene utilizzato come nome del trunk nel Pannello di controllo di Skype for Business Server, dove i trunk possono essere associati alle route.</span><span class="sxs-lookup"><span data-stu-id="d24a4-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="d24a4-116">Il nome del trunk semplice viene utilizzato come nome del gateway da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d24a4-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="d24a4-117">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d24a4-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="d24a4-118">In Generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="d24a4-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="d24a4-119">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d24a4-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="d24a4-120">Nel diagramma seguente vengono illustrati i più trunk definiti per ogni Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="d24a4-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Assegnazioni di più trunk](../../media/multiple-trunk-assignments.jpg)
