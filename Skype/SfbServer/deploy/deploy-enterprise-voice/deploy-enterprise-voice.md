---
title: Distribuire VoIP aziendale in Skype for Business Server
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
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Riepilogo: informazioni su come distribuire VoIP aziendale per Skype for Business Server in un sito centrale.'
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104972"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="91a68-103">Distribuire VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="91a68-104">**Riepilogo:** Informazioni su come distribuire VoIP aziendale per Skype for Business Server in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="91a68-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="91a68-105">Utilizzare questo argomento per distribuire VoIP aziendale in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="91a68-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="91a68-106">Per distribuire VoIP aziendale in un sito di succursale, passare a [Distribuzione di siti di succursale](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span><span class="sxs-lookup"><span data-stu-id="91a68-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="91a68-107">In questa sezione sono incluse le procedure per le distribuzioni in cui un Mediation Server è collocato in ogni Front End Server o server Standard Edition, come consigliato, nonché per le distribuzioni con un pool Mediation Server autonomo. È possibile ignorare il contenuto seguente se è stato utilizzato Generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni Front End Server o server Standard Edition, poiché la Distribuzione guidata ha già installato automaticamente i file per Mediation Server durante l'installazione dei file per il pool Front End Server o il server Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="91a68-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="91a68-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="91a68-108">In this section</span></span>

- [<span data-ttu-id="91a68-109">Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="91a68-110">Distribuire un Mediation Server in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="91a68-111">Definire un gateway in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="91a68-112">Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="91a68-113">Installare i file per Mediation Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="91a68-114">Configurare i trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="91a68-115">Creare o modificare una regola di conversione per la presentazione dell'ID chiamante in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="91a68-116">Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="91a68-117">Creare o modificare una regola di normalizzazione in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="91a68-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="91a68-118">Creare o modificare un dial plan in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="91a68-119">Configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="91a68-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="91a68-120">Abilitare gli utenti per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="91a68-121">Distribuire funzionalità VoIP aziendale avanzate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="91a68-122">Distribuire le funzionalità di gestione delle chiamate in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="91a68-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="91a68-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91a68-123">See also</span></span>

[<span data-ttu-id="91a68-124">Pianificare la VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91a68-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)