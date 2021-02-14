---
title: Gestire le organizzazioni di Skype for Business online
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
description: Usare Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for Business online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085692"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="b4f3b-103">Gestire le organizzazioni di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b4f3b-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="b4f3b-104">L'ultima [versione di Anteprima pubblica di Teams powerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="b4f3b-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="b4f3b-105">Puoi trovare informazioni sul tuo tenant Skype for Business online utilizzando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b4f3b-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="b4f3b-106">Gestire i tenant di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b4f3b-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="b4f3b-107">Per ottenere informazioni sul tuo tenant Skype for Business online, chiama il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b4f3b-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="b4f3b-108">Per restituire solo il nome e l'ID del tenant, usare questo comando.</span><span class="sxs-lookup"><span data-stu-id="b4f3b-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="b4f3b-109">Il valore del parametro _TenantID_ è obbligatorio quando si eseguono cmdlet come [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4f3b-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="b4f3b-110">Per informazioni sulla disponibilità delle informazioni sulle licenze per il tenant specificato nell'interfaccia di amministrazione di Skype for Business Online, usare il cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)</span><span class="sxs-lookup"><span data-stu-id="b4f3b-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b4f3b-111">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b4f3b-111">Related topics</span></span>
[<span data-ttu-id="b4f3b-112">Configurare il computer per la gestione di Skype for Business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f3b-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
