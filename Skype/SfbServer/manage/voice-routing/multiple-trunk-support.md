---
title: Supporto per più trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816946"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="e5764-105">Supporto per più trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e5764-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="e5764-106">La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e5764-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="e5764-107">Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e5764-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="e5764-108">Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).</span><span class="sxs-lookup"><span data-stu-id="e5764-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="e5764-109">Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario prima di tutto definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e5764-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="e5764-110">Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.</span><span class="sxs-lookup"><span data-stu-id="e5764-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="e5764-111">Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e5764-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="e5764-112">In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="e5764-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="e5764-113">Quando viene definito un trunk, deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="e5764-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="e5764-114">Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="e5764-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="e5764-115">Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Skype for Business Server, dove Trunks può essere associato alle route.</span><span class="sxs-lookup"><span data-stu-id="e5764-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="e5764-116">Il nome del trunk semplice viene usato come nome del gateway da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e5764-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="e5764-117">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e5764-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="e5764-118">In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e5764-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="e5764-119">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e5764-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="e5764-120">Il diagramma seguente illustra i trunk più definiti per ogni Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="e5764-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Più assegnazioni trunk](../../media/multiple-trunk-assignments.jpg)
