---
title: Distribuire Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: "Riepilogo: informazioni su come distribuire un Edge Server o un pool di Edge nell'ambiente di Skype for Business Server."
ms.openlocfilehash: 03cb3f1bc4a938a698c28332b4781d08434bc52f
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493105"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="fb6a1-103">Distribuire Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="fb6a1-104">**Riepilogo:** Informazioni su come distribuire un Edge Server o un pool di Edge nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="fb6a1-105">Perché distribuire un Edge Server o un pool di Edge nell'ambiente di Skype for Business Server?</span><span class="sxs-lookup"><span data-stu-id="fb6a1-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="fb6a1-106">È necessario se sono necessari utenti esterni che non hanno eseguito l'accesso alla rete interna dell'organizzazione per poter interagire con gli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="fb6a1-107">Questi utenti esterni possono essere autenticati e utenti remoti anonimi, partner federati o altri client mobili.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="fb6a1-108">Elenco di controllo della distribuzione per Edge, per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="fb6a1-109">Come indicato in precedenza, molto passa in una distribuzione di Edge Server per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="fb6a1-110">Questo elenco di controllo offre una panoramica delle attività che è necessario eseguire e collegamenti a passaggi più dettagliati.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="fb6a1-111">Speriamo che tu abbia iniziato nel [piano per le distribuzioni di Edge Server nella sezione Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="fb6a1-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="fb6a1-112">In caso contrario, molte delle cose a cui ci riferiamo sono dettagliate.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="fb6a1-113">La sezione distribuzione contiene solo le procedure, quindi se vuoi conoscere il ragionamento che sta alla base di questi passaggi, la pianificazione è il punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="fb6a1-114">Questa documentazione presuppone anche che tu abbia già completato la distribuzione di base di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="fb6a1-115">Questa operazione può essere eseguita affiancata con il bordo, ma è necessario seguire prima questi passaggi e quindi è possibile apportare le modifiche della topologia per il bordo documentato in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fb6a1-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="fb6a1-116">Questi sono i passaggi di alto livello che è necessario seguire e i punti in cui sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="fb6a1-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="fb6a1-117">Requisiti di sistema di Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="fb6a1-118">Requisiti ambientali di Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="fb6a1-119">Creare la topologia di Edge per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="fb6a1-120">Distribuire Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="fb6a1-121">Convalidare la distribuzione di Edge in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb6a1-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

