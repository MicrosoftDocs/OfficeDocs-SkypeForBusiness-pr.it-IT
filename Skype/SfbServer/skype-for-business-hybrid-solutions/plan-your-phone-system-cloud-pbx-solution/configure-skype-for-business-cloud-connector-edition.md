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
description: Informazioni su come configurare Skype for Business Cloud Connector Edition, una topologia minima locale per consentire l'integrazione dell'infrastruttura vocale locale con i servizi vocali del sistema telefonico (cloud PBX) in Skype for business online.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219516"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1b8f4-103">Configurare e gestire Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b8f4-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="1b8f4-104">Informazioni su come configurare Skype for Business Cloud Connector Edition, una topologia minima locale per consentire l'integrazione dell'infrastruttura vocale locale con i servizi vocali del sistema telefonico (cloud PBX) in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="1b8f4-105">Prima di iniziare, è consigliabile esaminare i prerequisiti in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="1b8f4-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1b8f4-106">Le procedure descritte in questo argomento si applicano solo a Cloud Connector Edition 1.4.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="1b8f4-107">Se non è ancora stato eseguito l'aggiornamento a Cloud Connector Edition 2,1, vedere [upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1b8f4-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="1b8f4-108">È possibile scaricare il file di installazione da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="1b8f4-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1b8f4-109">Procedura per configurare Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b8f4-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="1b8f4-110">Nella tabella seguente sono elencati i passaggi necessari per l'installazione e la configurazione del Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="1b8f4-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="1b8f4-111">**Fase**
</span><span class="sxs-lookup"><span data-stu-id="1b8f4-111">**Step**</span></span>|<span data-ttu-id="1b8f4-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1b8f4-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1b8f4-113">Predisporre l'appliance di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="1b8f4-114">Scaricare il file di installazione, preparare i certificati, configurare Hyper-V e ottenere l'ambiente pronto per la distribuzione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-115">Distribuire un sito singolo in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="1b8f4-116">Creare un sito nella distribuzione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-117">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="1b8f4-118">Aggiungere siti alla distribuzione e conoscere le differenze tra le distribuzioni singole e multisito.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-119">Configurare l'integrazione del connettore Cloud con l'organizzazione Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1b8f4-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="1b8f4-120">Aggiungere record DNS, configurare l'ambiente ibrido, impostare i gateway PSTN e abilitare gli utenti per la segreteria telefonica del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-121">Convalidare la distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b8f4-122">Verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-123">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="1b8f4-124">Aggiornare la distribuzione del connettore cloud esistente alla versione 2,1.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-125">Modificare la configurazione di una distribuzione di Cloud Connector esistente</span><span class="sxs-lookup"><span data-stu-id="1b8f4-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b8f4-126">Modificare le impostazioni in Cloud Connector dopo che è già stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-127">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b8f4-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="1b8f4-128">Informazioni su come distribuire il bypass multimediale in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-129">Informazioni di riferimento sui cmdlet di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="1b8f4-130">Informazioni sui cmdlet di PowerShell utilizzati in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1b8f4-131">Risolvere i problemi relativi alla distribuzione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b8f4-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b8f4-132">Soluzioni ai problemi comuni riscontrati con una distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b8f4-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

