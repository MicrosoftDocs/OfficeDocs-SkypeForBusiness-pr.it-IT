---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Il Set-CcExternalCertificateFilePath cmdlet consente di specificare il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824200"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="25640-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="25640-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="25640-104">Il Set-CcExternalCertificateFilePath cmdlet consente di specificare il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="25640-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="25640-105">Questo certificato è necessario durante la distribuzione o quando si aggiungono nuove appliance di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="25640-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="25640-106">Il comando consente inoltre di importare un nuovo certificato per il Mediation Server dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25640-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="25640-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="25640-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="25640-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="25640-108">Examples</span></span>
<span data-ttu-id="25640-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="25640-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="25640-110">Example 1</span></span>

<span data-ttu-id="25640-111">Nell'esempio seguente viene impostato il percorso del certificato per il server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="25640-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="25640-112">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="25640-112">Example 2</span></span>

<span data-ttu-id="25640-113">Nell'esempio seguente viene impostato il percorso del certificato per il Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="25640-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="25640-114">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="25640-114">Example 3</span></span>

<span data-ttu-id="25640-115">Nell'esempio seguente viene aggiornato il certificato per il Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="25640-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="25640-116">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="25640-116">Detailed Description</span></span>
<span data-ttu-id="25640-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="25640-118">Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, per il certificato mediation server.</span><span class="sxs-lookup"><span data-stu-id="25640-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="25640-119">Il certificato per il Mediation Server è obbligatorio se verrà utilizzato TLS tra il gateway (s) e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="25640-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="25640-120">Quando si distribuisce un'applicazione Cloud Connector e si desidera distribuire TLS, è possibile specificare solo il percorso del certificato che verrà distribuito nel Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="25640-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="25640-121">Tuttavia, se si desidera aggiornare il certificato mediation in un'applicazione già distribuita, è necessario specificare il percorso e il parametro -Import.</span><span class="sxs-lookup"><span data-stu-id="25640-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="25640-122">Per visualizzare il percorso, utilizzare il cmdlet Get-CCExternalCertificateFilePath seguente.</span><span class="sxs-lookup"><span data-stu-id="25640-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="25640-123">Parametri</span><span class="sxs-lookup"><span data-stu-id="25640-123">Parameters</span></span>
<span data-ttu-id="25640-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="25640-125">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="25640-125">**Parameter**</span></span>|<span data-ttu-id="25640-126">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="25640-126">**Required**</span></span>|<span data-ttu-id="25640-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="25640-127">**Type**</span></span>|<span data-ttu-id="25640-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="25640-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="25640-129">Destinazione</span><span class="sxs-lookup"><span data-stu-id="25640-129">Target</span></span> <br/> | <span data-ttu-id="25640-130">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="25640-130">Required</span></span> <br/> |<span data-ttu-id="25640-131">System.String</span><span class="sxs-lookup"><span data-stu-id="25640-131">System.String</span></span>  <br/> |<span data-ttu-id="25640-132">Tipo di percorso file richiesto.</span><span class="sxs-lookup"><span data-stu-id="25640-132">Type of file path requested.</span></span> <span data-ttu-id="25640-133">I tipi includono:</span><span class="sxs-lookup"><span data-stu-id="25640-133">Types include:</span></span>  <br/> <span data-ttu-id="25640-134">EdgeServer (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="25640-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="25640-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="25640-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="25640-136">Importazione</span><span class="sxs-lookup"><span data-stu-id="25640-136">Import</span></span>  <br/> |<span data-ttu-id="25640-137">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="25640-137">Optional</span></span>  <br/> |<span data-ttu-id="25640-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="25640-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="25640-139">Indica che il certificato deve essere importato nel Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="25640-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="25640-140">Questo parametro non è necessario se si distribuisce un'applicazione per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="25640-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="25640-141">Il parametro è obbligatorio se si desidera modificare il certificato esistente in una versione già distribuita.</span><span class="sxs-lookup"><span data-stu-id="25640-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="25640-142">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="25640-142">Input Types</span></span>
<span data-ttu-id="25640-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="25640-144">Il cmdlet Set-CcExternalCertificateFilePath non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="25640-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="25640-145">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="25640-145">Return Types</span></span>
<span data-ttu-id="25640-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="25640-147">None</span><span class="sxs-lookup"><span data-stu-id="25640-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25640-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25640-148">See also</span></span>
<span data-ttu-id="25640-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25640-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="25640-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="25640-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

