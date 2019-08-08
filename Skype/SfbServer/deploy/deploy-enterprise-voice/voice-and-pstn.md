---
title: Configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Riepilogo: informazioni su come configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for Business Server.'
ms.openlocfilehash: 3cdc621e163aa8cff4ba2456c3a94ddf30bfcbaf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240209"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="4391d-103">Configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="4391d-104">**Riepilogo:** Informazioni su come configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4391d-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="4391d-105">I criteri vocali, i record di utilizzo PSTN e le route vocali sono correlati integralmente.</span><span class="sxs-lookup"><span data-stu-id="4391d-105">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="4391d-106">Si configurano i criteri vocali selezionando un set di funzionalità di chiamata e quindi assegnando al criterio un set di record di utilizzo PSTN, che specificano i diritti autorizzati per gli utenti o i gruppi a cui è assegnato il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="4391d-106">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="4391d-107">Alle route vocali vengono assegnati anche record di utilizzo PSTN, che servono per abbinare le route con gli utenti autorizzati ad usarli.</span><span class="sxs-lookup"><span data-stu-id="4391d-107">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="4391d-108">Gli utenti possono quindi inserire solo chiamate che usano le route per cui hanno un record di utilizzo PSTN corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4391d-108">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="4391d-109">Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nell'iniziare la configurazione di un criterio vocale che include i record di utilizzo PSTN appropriati e quindi associare le route appropriate a ogni record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="4391d-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4391d-110">È anche possibile creare criteri vocali con l'ambito *degli* utenti e assegnarli a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="4391d-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="4391d-111">Per la procedura dettagliata per eseguire ognuna di queste attività, vedere le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="4391d-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4391d-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4391d-112">In this section</span></span>

- [<span data-ttu-id="4391d-113">Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="4391d-114">Configurare l'escape della segreteria telefonica in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="4391d-115">Visualizzare i record di utilizzo PSTN in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="4391d-116">Creare o modificare una route vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="4391d-117">Esportare o importare un file di configurazione della route vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="4391d-118">Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="4391d-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

