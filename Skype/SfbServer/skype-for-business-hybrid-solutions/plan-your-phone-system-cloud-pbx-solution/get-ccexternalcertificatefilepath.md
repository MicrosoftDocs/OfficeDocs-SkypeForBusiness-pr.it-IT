---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition. L'utente prepara il certificato.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799906"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="1918c-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="1918c-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="1918c-105">Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1918c-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="1918c-106">L'utente prepara il certificato.</span><span class="sxs-lookup"><span data-stu-id="1918c-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="1918c-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1918c-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="1918c-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="1918c-108">Examples</span></span>
<span data-ttu-id="1918c-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1918c-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="1918c-110">Example 1</span></span>

<span data-ttu-id="1918c-111">Nell'esempio seguente viene mostrato il percorso del certificato per il server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="1918c-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="1918c-112">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="1918c-112">Example 2</span></span>

<span data-ttu-id="1918c-113">Nell'esempio seguente viene mostrato il set di certificati per il Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="1918c-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="1918c-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="1918c-114">Detailed Description</span></span>
<span data-ttu-id="1918c-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1918c-116">Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1918c-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="1918c-117">Il certificato per il Mediation Server è obbligatorio se verrà utilizzato TLS tra il gateway (s) e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1918c-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="1918c-118">Per modificare il percorso, utilizzare il cmdlet Set-CcExternalCertificateFilePath seguente.</span><span class="sxs-lookup"><span data-stu-id="1918c-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1918c-119">Parametri</span><span class="sxs-lookup"><span data-stu-id="1918c-119">Parameters</span></span>
<span data-ttu-id="1918c-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="1918c-121">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="1918c-121">**Parameter**</span></span>|<span data-ttu-id="1918c-122">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="1918c-122">**Required**</span></span>|<span data-ttu-id="1918c-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1918c-123">**Type**</span></span>|<span data-ttu-id="1918c-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1918c-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1918c-125">Destinazione</span><span class="sxs-lookup"><span data-stu-id="1918c-125">Target</span></span>  <br/> |<span data-ttu-id="1918c-126">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="1918c-126">Optional</span></span>  <br/> | <span data-ttu-id="1918c-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1918c-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="1918c-128">Tipo di percorso file richiesto.</span><span class="sxs-lookup"><span data-stu-id="1918c-128">Type of file path requested.</span></span> <span data-ttu-id="1918c-129">I tipi includono:</span><span class="sxs-lookup"><span data-stu-id="1918c-129">Types include:</span></span>  <br/> <span data-ttu-id="1918c-130">EdgeServer (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1918c-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="1918c-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1918c-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1918c-132">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="1918c-132">Input Types</span></span>
<span data-ttu-id="1918c-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1918c-134">Il cmdlet Get-CcExternalCertificateFilePath non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="1918c-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1918c-135">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="1918c-135">Return Types</span></span>
<span data-ttu-id="1918c-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1918c-137">Il comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="1918c-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1918c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1918c-138">See also</span></span>
<span data-ttu-id="1918c-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1918c-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="1918c-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

