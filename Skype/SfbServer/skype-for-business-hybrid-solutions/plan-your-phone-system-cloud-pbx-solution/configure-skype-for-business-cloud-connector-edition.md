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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Informazioni su come configurare Skype for Business Cloud Connector Edition, una minima topologia locale per consentire l'integrazione dell'infrastruttura vocale locale con il sistema telefonico in Office 365 (cloud PBX) Voice Services in Skype for business online.
ms.openlocfilehash: 49c0ce1a67b579a566e2dd22b9b345c1d6a4afdd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190865"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="a215c-103">Configurare e gestire Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a215c-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="a215c-104">Informazioni su come configurare Skype for Business Cloud Connector Edition, una minima topologia locale per consentire l'integrazione dell'infrastruttura vocale locale con il sistema telefonico in Office 365 (cloud PBX) Voice Services in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="a215c-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="a215c-105">Prima di iniziare, è necessario rivedere i prerequisiti in [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="a215c-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a215c-106">La procedura descritta in questo argomento si applica solo a Cloud Connector Edition 1.4.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a215c-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="a215c-107">Se non è stato ancora aggiornato a Cloud Connector Edition 2,1, vedere [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a215c-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="a215c-108">È possibile scaricare il file di installazione [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)da.</span><span class="sxs-lookup"><span data-stu-id="a215c-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="a215c-109">Procedura per configurare Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a215c-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="a215c-110">La tabella seguente elenca i passaggi necessari per installare e configurare Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="a215c-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="a215c-111">**Passaggio**</span><span class="sxs-lookup"><span data-stu-id="a215c-111">**Step**</span></span>|<span data-ttu-id="a215c-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a215c-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a215c-113">Preparare l'accessorio Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="a215c-114">Scaricare il file di installazione, preparare i certificati, configurare Hyper-V e ottenere l'ambiente pronto per la distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a215c-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="a215c-115">Distribuire un singolo sito nel connettore Cloud</span><span class="sxs-lookup"><span data-stu-id="a215c-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="a215c-116">Creare un sito nella distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a215c-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="a215c-117">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="a215c-118">Aggiungere siti alla distribuzione e informazioni sulle differenze tra distribuzioni singole e multisito.</span><span class="sxs-lookup"><span data-stu-id="a215c-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="a215c-119">Configurare l'integrazione del connettore Cloud con il tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="a215c-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="a215c-120">Aggiungere record DNS, configurare Hybrid, impostare gateway PSTN e abilitare gli utenti per il sistema telefonico in Office 365 segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="a215c-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="a215c-121">Convalidare la distribuzione del Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a215c-122">Verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="a215c-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="a215c-123">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="a215c-124">Aggiornare la distribuzione del Cloud Connector esistente alla versione 2,1.</span><span class="sxs-lookup"><span data-stu-id="a215c-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="a215c-125">Modificare la configurazione di una distribuzione di Cloud Connector esistente</span><span class="sxs-lookup"><span data-stu-id="a215c-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a215c-126">Modificare le impostazioni nel connettore cloud dopo che è già stata distribuita.</span><span class="sxs-lookup"><span data-stu-id="a215c-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="a215c-127">Distribuire il bypass multimediale in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a215c-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="a215c-128">Informazioni su come distribuire il bypass multimediale in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a215c-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="a215c-129">Informazioni di riferimento sui cmdlet di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="a215c-130">Informazioni sui cmdlet di PowerShell usati in Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a215c-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="a215c-131">Risolvere i problemi di distribuzione del Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a215c-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="a215c-132">Soluzioni ai problemi comuni incontrati con una distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a215c-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

