---
title: Configurare e gestire Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Informazioni su come configurare Skype for Business Cloud Connector Edition, una topologia locale minima per consentire l'integrazione dell'infrastruttura vocale locale con i servizi vocali del sistema telefonico (Cloud PBX) in Skype for Business online.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094874"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="a6f7a-103">Configurare e gestire Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a6f7a-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="a6f7a-104">Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="a6f7a-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="a6f7a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="a6f7a-106">Informazioni su come configurare Skype for Business Cloud Connector Edition, una topologia locale minima per consentire l'integrazione dell'infrastruttura vocale locale con i servizi vocali del sistema telefonico (Cloud PBX) in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="a6f7a-107">Prima di iniziare, è consigliabile esaminare i prerequisiti in [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="a6f7a-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a6f7a-108">I passaggi descritti in questo argomento si applicano solo a Cloud Connector Edition 1.4.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="a6f7a-109">Se non è stato ancora eseguito l'aggiornamento a Cloud Connector Edition 2.1, vedere [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a6f7a-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="a6f7a-110">È possibile scaricare il file di installazione da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="a6f7a-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="a6f7a-111">Passaggi per configurare Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a6f7a-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="a6f7a-112">Nella tabella seguente sono elencati i passaggi necessari per installare e configurare Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="a6f7a-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="a6f7a-113">**Passaggio**</span><span class="sxs-lookup"><span data-stu-id="a6f7a-113">**Step**</span></span>|<span data-ttu-id="a6f7a-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a6f7a-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a6f7a-115">Predisporre l'appliance di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="a6f7a-116">Scaricare il file di installazione, preparare i certificati, configurare Hyper-V e preparare l'ambiente per la distribuzione del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-117">Distribuire un sito singolo in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="a6f7a-118">Creare un sito nella distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-119">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="a6f7a-120">Aggiungere siti alla distribuzione e informazioni sulle differenze tra distribuzioni singole e multisocie.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-121">Configurare l'integrazione del connettore cloud con l'organizzazione di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="a6f7a-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="a6f7a-122">Aggiungere record DNS, configurare ibridi, configurare gateway PSTN e abilitare gli utenti per la segreteria telefonica del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-123">Convalidare la distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a6f7a-124">Verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-125">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="a6f7a-126">Aggiornare la distribuzione esistente di Cloud Connector alla versione 2.1.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-127">Modificare la configurazione di una distribuzione di Cloud Connector esistente</span><span class="sxs-lookup"><span data-stu-id="a6f7a-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a6f7a-128">Modificare le impostazioni in Cloud Connector dopo che è già stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-129">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a6f7a-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="a6f7a-130">Informazioni su come distribuire il bypass multimediale in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-131">Informazioni di riferimento sui cmdlet di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="a6f7a-132">Informazioni sui cmdlet di PowerShell utilizzati in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="a6f7a-133">Risolvere i problemi relativi alla distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a6f7a-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a6f7a-134">Soluzioni ai problemi comuni riscontrati con una distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
