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
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812496"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="acbab-103">Distribuire VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="acbab-104">**Riepilogo:** Informazioni su come distribuire VoIP aziendale per Skype for Business Server in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="acbab-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="acbab-105">Utilizzare questo argomento per distribuire VoIP aziendale in un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="acbab-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="acbab-106">Per distribuire VoIP aziendale in un sito di succursale, passare [a Distribuzione di siti di succursale.](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)</span><span class="sxs-lookup"><span data-stu-id="acbab-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="acbab-107">In questa sezione sono incluse le procedure per le distribuzioni in cui un Mediation Server è collocato in ogni Front End Server o server Standard Edition, come consigliato, nonché per le distribuzioni con un pool Mediation Server autonomo. È possibile ignorare il contenuto seguente se è stato utilizzato Generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni Front End Server o server Standard Edition, perché la Distribuzione guidata ha già installato automaticamente i file per Mediation Server durante l'installazione dei file per il pool Front End Server o il server Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="acbab-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="acbab-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="acbab-108">In this section</span></span>

- [<span data-ttu-id="acbab-109">Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="acbab-110">Distribuire un Mediation Server in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="acbab-111">Definire un gateway in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="acbab-112">Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="acbab-113">Installare i file per Mediation Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="acbab-114">Configurare i trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="acbab-115">Creare o modificare una regola di conversione per la presentazione dell'ID chiamante in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="acbab-116">Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="acbab-117">Creare o modificare una regola di normalizzazione in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="acbab-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="acbab-118">Creare o modificare un dial plan in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="acbab-119">Configurare criteri vocali, record di utilizzo PSTN e route vocali in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="acbab-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="acbab-120">Abilitare gli utenti per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="acbab-121">Distribuire funzionalità VoIP aziendale avanzate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="acbab-122">Distribuire le funzionalità di gestione delle chiamate in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="acbab-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="acbab-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acbab-123">See also</span></span>

[<span data-ttu-id="acbab-124">Pianificare la VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acbab-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

