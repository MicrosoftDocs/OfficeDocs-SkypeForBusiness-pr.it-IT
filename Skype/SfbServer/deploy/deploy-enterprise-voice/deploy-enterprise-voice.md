---
title: Distribuire VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Riepilogo: informazioni su come distribuire Enterprise Voice per Skype for Business Server in un sito centrale.'
ms.openlocfilehash: c5995570d8d3cf775b2837bb6ddfc170860d57dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191951"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="c8d33-103">Distribuire VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="c8d33-104">**Riepilogo:** Informazioni su come distribuire Enterprise Voice per Skype for Business Server in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8d33-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="c8d33-105">Usare questo argomento per distribuire Enterprise Voice in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8d33-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="c8d33-106">Per distribuire VoIP aziendale in un sito di succursale, passare alla sezione [distribuzione dei siti](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)di succursale.</span><span class="sxs-lookup"><span data-stu-id="c8d33-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="c8d33-107">Questa sezione include procedure per le distribuzioni in cui un Mediation Server è collocato in ogni server front-end o Standard Edition, come raccomandato e anche per le distribuzioni con un pool di Mediation Server autonomo. È possibile ignorare il contenuto seguente se è stato usato generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni server front-end o Standard Edition, perché la distribuzione guidata ha già installato automaticamente i file per Mediation Server quando i file sono stati installati per il pool di front end server o per il server Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="c8d33-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="c8d33-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c8d33-108">In this section</span></span>

- [<span data-ttu-id="c8d33-109">Prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="c8d33-110">Distribuire un Mediation Server in Generatore di topologia in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="c8d33-111">Definire un gateway in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="c8d33-112">Definire trunk aggiuntivi in Generatore di topologia in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="c8d33-113">Installare i file per Mediation Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="c8d33-114">Configurare Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="c8d33-115">Creare o modificare una regola di traduzione per la presentazione dell'ID chiamante in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="c8d33-116">Creare o modificare una regola di traduzione per la presentazione di ID chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="c8d33-117">Creare o modificare una regola di normalizzazione in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c8d33-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="c8d33-118">Creare o modificare un dial plan in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="c8d33-119">Configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c8d33-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="c8d33-120">Consentire agli utenti di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="c8d33-121">Distribuire le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="c8d33-122">Distribuire le funzionalità di gestione delle chiamate in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c8d33-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="c8d33-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d33-123">See also</span></span>

[<span data-ttu-id="c8d33-124">Pianificare VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8d33-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

