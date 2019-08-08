---
title: Distribuire il controllo di ammissione alle chiamate in Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Il controllo di ammissione di chiamata (CAC) è una soluzione che determina se una sessione in tempo reale può essere stabilita in base alla larghezza di banda disponibile per evitare una scarsa qualità audio/video per gli utenti nelle reti congestionate.
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233520"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="1b91f-103">Distribuire il controllo di ammissione alle chiamate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1b91f-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="1b91f-104">Il controllo di ammissione di chiamata (CAC) è una soluzione che determina se una sessione in tempo reale può essere stabilita in base alla larghezza di banda disponibile per evitare una scarsa qualità audio/video per gli utenti nelle reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="1b91f-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="1b91f-105">Per altre informazioni, Vedi [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="1b91f-106">Per distribuire il controllo di ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="1b91f-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="1b91f-107">Raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="1b91f-108">Se non è già stato fatto, è necessario definire le aree geografiche e i siti di rete e associare subnet ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="1b91f-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="1b91f-109">Per informazioni dettagliate, vedere [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="1b91f-110">Creare profili di criteri di larghezza di banda, come dettagliato in [creare profili di criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1b91f-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="1b91f-111">Creare collegamenti a un'area geografica di rete, come descritto in [creare collegamenti all'area di rete in Skype for Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="1b91f-112">Creare rotte interregionali di rete, come descritto in dettaglio in [creare route interregionali di rete in Skype for Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="1b91f-113">Creare criteri di intersito di rete, come descritto in dettaglio per [creare criteri intersito di rete in Skype for Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="1b91f-114">Abilitare il controllo di ammissione alle chiamate, come descritto in [Abilita controllo ammissione chiamata in Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="1b91f-115">Verificare alcune impostazioni finali per verificare che tutto sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1b91f-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="1b91f-116">Per informazioni dettagliate, vedere [distribuzione dei controlli di ammissione alle chiamate: elenco di controllo finale per Skype for Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="1b91f-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

