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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Il cmdlet Set-CcExternalCertificateFilePath specifica il percorso in cui è archiviato il certificato per il server di mediazione o il server perimetrale.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190643"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="97fbc-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="97fbc-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="97fbc-104">Il cmdlet Set-CcExternalCertificateFilePath specifica il percorso in cui è archiviato il certificato per il server di mediazione o il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="97fbc-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="97fbc-105">Questo certificato è necessario durante la distribuzione o quando si aggiungono nuovi elettrodomestici di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="97fbc-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="97fbc-106">Il comando consente inoltre di importare un nuovo certificato per il Mediation Server dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="97fbc-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="97fbc-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="97fbc-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="97fbc-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="97fbc-108">Examples</span></span>
<span data-ttu-id="97fbc-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="97fbc-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="97fbc-110">Example 1</span></span>

<span data-ttu-id="97fbc-111">L'esempio seguente imposta il percorso del certificato per il server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="97fbc-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="97fbc-112">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="97fbc-112">Example 2</span></span>

<span data-ttu-id="97fbc-113">L'esempio seguente imposta il percorso del certificato per il Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="97fbc-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="97fbc-114">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="97fbc-114">Example 3</span></span>

<span data-ttu-id="97fbc-115">Nell'esempio successivo viene aggiornato il certificato per il Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="97fbc-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="97fbc-116">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="97fbc-116">Detailed Description</span></span>
<span data-ttu-id="97fbc-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-117"></span></span>

<span data-ttu-id="97fbc-118">Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, il certificato di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="97fbc-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="97fbc-119">Il certificato per il Mediation Server è obbligatorio se TLS verrà usato tra i gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="97fbc-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="97fbc-120">Quando si distribuisce un'appliance di Cloud Connector e si vuole distribuire TLS, è possibile specificare solo il percorso del certificato che verrà distribuito nel Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="97fbc-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="97fbc-121">Tuttavia, se si vuole aggiornare il certificato di mediazione in un'appliance già distribuita, è necessario specificare il percorso e il parametro-Import.</span><span class="sxs-lookup"><span data-stu-id="97fbc-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="97fbc-122">Per visualizzare il percorso, usare il cmdlet Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="97fbc-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="97fbc-123">Parametri</span><span class="sxs-lookup"><span data-stu-id="97fbc-123">Parameters</span></span>
<span data-ttu-id="97fbc-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-124"></span></span>

|<span data-ttu-id="97fbc-125">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="97fbc-125">**Parameter**</span></span>|<span data-ttu-id="97fbc-126">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="97fbc-126">**Required**</span></span>|<span data-ttu-id="97fbc-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="97fbc-127">**Type**</span></span>|<span data-ttu-id="97fbc-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97fbc-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="97fbc-129">Destinazione</span><span class="sxs-lookup"><span data-stu-id="97fbc-129">Target</span></span> <br/> | <span data-ttu-id="97fbc-130">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="97fbc-130">Required</span></span> <br/> |<span data-ttu-id="97fbc-131">System.String</span><span class="sxs-lookup"><span data-stu-id="97fbc-131">System.String</span></span>  <br/> |<span data-ttu-id="97fbc-132">Tipo di percorso di file richiesto.</span><span class="sxs-lookup"><span data-stu-id="97fbc-132">Type of file path requested.</span></span> <span data-ttu-id="97fbc-133">I tipi includono:</span><span class="sxs-lookup"><span data-stu-id="97fbc-133">Types include:</span></span>  <br/> <span data-ttu-id="97fbc-134">EdgeServer (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="97fbc-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="97fbc-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="97fbc-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="97fbc-136">Importazione</span><span class="sxs-lookup"><span data-stu-id="97fbc-136">Import</span></span>  <br/> |<span data-ttu-id="97fbc-137">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="97fbc-137">Optional</span></span>  <br/> |<span data-ttu-id="97fbc-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="97fbc-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="97fbc-139">Indica che il certificato deve essere importato nel Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="97fbc-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="97fbc-140">Questo parametro non è necessario se si distribuisce un dispositivo per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="97fbc-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="97fbc-141">Il parametro è obbligatorio se si vuole modificare il certificato esistente in una versione già distribuita.</span><span class="sxs-lookup"><span data-stu-id="97fbc-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="97fbc-142">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="97fbc-142">Input Types</span></span>
<span data-ttu-id="97fbc-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-143"></span></span>

<span data-ttu-id="97fbc-144">Il cmdlet Set-CcExternalCertificateFilePath non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="97fbc-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="97fbc-145">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="97fbc-145">Return Types</span></span>
<span data-ttu-id="97fbc-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-146"></span></span>

<span data-ttu-id="97fbc-147">Nessuno</span><span class="sxs-lookup"><span data-stu-id="97fbc-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97fbc-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97fbc-148">See also</span></span>
<span data-ttu-id="97fbc-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97fbc-149"></span></span>

[<span data-ttu-id="97fbc-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="97fbc-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

