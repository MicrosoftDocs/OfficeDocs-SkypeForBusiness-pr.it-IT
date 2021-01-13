---
title: Distribuire il controllo di ammissione di chiamata in Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836886"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="43e24-103">Distribuire il controllo di ammissione di chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43e24-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="43e24-104">Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="43e24-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="43e24-105">Per ulteriori informazioni, vedere [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="43e24-106">Per distribuire il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="43e24-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="43e24-107">Raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="43e24-108">Se non è già stato fatto, è necessario definire le aree e i siti di rete e associare le subnet ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="43e24-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="43e24-109">Per informazioni dettagliate, vedere [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="43e24-110">Creare profili di criteri di larghezza di banda, come descritto in [creare profili di criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="43e24-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="43e24-111">Creare collegamenti area di rete, come descritto in [creare collegamenti area di rete in Skype for Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="43e24-112">Creare route tra aree di rete, come descritto in [creare route interregionali di rete in Skype for Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="43e24-113">Creare criteri intersito di rete, come descritto in [creare criteri intersito di rete in Skype for Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="43e24-114">Abilitare il controllo di ammissione di chiamata, come descritto in [abilitare il controllo di ammissione di chiamata in Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="43e24-115">Controllare alcune impostazioni finali, per assicurarsi che tutto sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="43e24-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="43e24-116">Per informazioni dettagliate, vedere [Call ammissioni Control Deployment: Final Checklist for Skype for Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="43e24-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

