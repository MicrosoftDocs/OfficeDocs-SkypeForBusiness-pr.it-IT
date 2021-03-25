---
title: Gestire le organizzazioni skype for business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Usare Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for Business Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113182"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="bb27e-103">Gestire le organizzazioni skype for business online</span><span class="sxs-lookup"><span data-stu-id="bb27e-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="bb27e-104">L'ultima [versione di anteprima pubblica di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un unico modulo per la gestione di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="bb27e-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="bb27e-105">È possibile trovare informazioni sul tenant di Skype for Business Online usando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="bb27e-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="bb27e-106">Gestire i tenant di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb27e-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="bb27e-107">Per restituire informazioni sul tenant di Skype for Business Online, chiamare il cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="bb27e-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="bb27e-108">Per restituire solo il nome e l'ID del tenant, usare questo comando.</span><span class="sxs-lookup"><span data-stu-id="bb27e-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="bb27e-109">Il valore del _parametro TenantID_ è obbligatorio quando si eseguono cmdlet come [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) e [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="bb27e-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="bb27e-110">Per informazioni sulla disponibilità delle informazioni sulle licenze per il tenant specificato nell'interfaccia di amministrazione di Skype for Business Online, usare il cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="bb27e-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bb27e-111">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bb27e-111">Related topics</span></span>
[<span data-ttu-id="bb27e-112">Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb27e-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
