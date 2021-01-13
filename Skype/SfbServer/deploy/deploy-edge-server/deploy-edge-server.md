---
title: Distribuire server perimetrali in Skype for Business Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: "Riepilogo: informazioni su come distribuire un server perimetrale o un pool di server perimetrali nell'ambiente di Skype for business."
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804386"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="74567-103">Distribuire server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="74567-104">**Riepilogo:** Informazioni su come distribuire un server perimetrale o un pool di server perimetrali nell'ambiente di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="74567-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="74567-105">Perché distribuire un server perimetrale o un pool di server perimetrali nell'ambiente di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="74567-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="74567-106">È necessario se sono necessari utenti esterni che non sono connessi alla rete interna dell'organizzazione per poter interagire con gli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="74567-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="74567-107">Gli utenti esterni possono essere autenticati e utenti remoti anonimi, partner federati o altri client mobili.</span><span class="sxs-lookup"><span data-stu-id="74567-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="74567-108">Elenco di controllo di distribuzione per il server perimetrale, per Skype for business</span><span class="sxs-lookup"><span data-stu-id="74567-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="74567-109">Come indicato in alto, molte attività vengono distribuite in una distribuzione di server perimetrali per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74567-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="74567-110">Questo elenco di controllo offre una panoramica delle attività che è necessario eseguire e collegamenti a passaggi più dettagliati.</span><span class="sxs-lookup"><span data-stu-id="74567-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="74567-111">Si spera di aver iniziato nella sezione [pianificazione per le distribuzioni di server perimetrali in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="74567-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="74567-112">In caso contrario, molte delle cose a cui ci si riferisce sono dettagliate.</span><span class="sxs-lookup"><span data-stu-id="74567-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="74567-113">La sezione Deployment contiene solo le procedure, quindi se si desidera conoscere il ragionamento alla base di questi passaggi, la pianificazione è il punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="74567-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="74567-114">Questa documentazione presuppone inoltre che sia stata già completata la distribuzione di base di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74567-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="74567-115">È possibile eseguire la distribuzione affiancata al server perimetrale, ma è necessario eseguire prima tali passaggi e quindi è possibile apportare le modifiche alla topologia per il server perimetrale documentato.</span><span class="sxs-lookup"><span data-stu-id="74567-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="74567-116">Questi sono i passaggi di alto livello che è necessario seguire e i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="74567-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="74567-117">Requisiti di sistema per i server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="74567-118">Requisiti ambientali dei server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="74567-119">Creare la topologia perimetrale per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="74567-120">Distribuire server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="74567-121">Convalidare la distribuzione di Edge in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74567-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

