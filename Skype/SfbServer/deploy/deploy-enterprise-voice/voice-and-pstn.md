---
title: Configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Riepilogo: informazioni su come configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business Server.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830446"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="e596e-103">Configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="e596e-104">**Riepilogo:** Informazioni su come configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e596e-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="e596e-p101">I criteri vocali, i record di utilizzo PSTN e le route vocali sono strettamente correlati. È infatti possibile configurare i criteri vocali selezionando un insieme di funzionalità di chiamata e quindi assegnando al criterio un insieme di record di utilizzo PSTN, che specificano quali diritti sono autorizzati per gli utenti o i gruppi a cui viene assegnato il criterio. Anche alle route vocali vengono assegnati record di utilizzo PSTN, allo scopo di trovare una corrispondenza tra le route e gli utenti che sono autorizzati a utilizzarle. In altri termini, gli utenti possono effettuare esclusivamente chiamate che utilizzino le route per cui dispongono di un record di utilizzo PSTN corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e596e-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="e596e-109">Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nel configurare innanzitutto un criterio vocale contenente i record di utilizzo PSTN appropriati e quindi nell'associare le route appropriate a ogni record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="e596e-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e596e-110">È inoltre possibile creare criteri vocali con  *ambito utente*  e assegnarli a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="e596e-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="e596e-111">Per i passaggi dettagliati per l'esecuzione di ognuna di queste attività, vedere le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e596e-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e596e-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e596e-112">In this section</span></span>

- [<span data-ttu-id="e596e-113">Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="e596e-114">Configurare l'escape del sistema di caselle vocali in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="e596e-115">Visualizzare i record di utilizzo PSTN in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="e596e-116">Creare o modificare una route vocale in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="e596e-117">Esportare o importare un file di configurazione della route vocale in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="e596e-118">Pubblicare modifiche in sospeso nella configurazione del routing vocale in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e596e-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

