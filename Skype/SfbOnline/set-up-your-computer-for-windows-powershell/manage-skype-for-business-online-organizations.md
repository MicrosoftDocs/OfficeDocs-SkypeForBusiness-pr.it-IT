---
title: Gestire le organizzazioni di Skype for business online
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
description: Usa Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for business online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085692"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="a8170-103">Gestire le organizzazioni di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a8170-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="a8170-104">La [versione di anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) più recente è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell per Teams.</span><span class="sxs-lookup"><span data-stu-id="a8170-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="a8170-105">Puoi trovare informazioni sul tenant di Skype for business online usando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a8170-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="a8170-106">Gestire i tenant di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a8170-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="a8170-107">Per restituire informazioni sul tenant di Skype for business online, chiama il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a8170-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="a8170-108">Per restituire solo il nome e l'ID del tenant, usare questo comando.</span><span class="sxs-lookup"><span data-stu-id="a8170-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="a8170-109">Il valore del parametro _ID tenant_ è obbligatorio quando si utilizzano cmdlet, ad esempio [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="a8170-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="a8170-110">Per informazioni sul fatto che le informazioni sulla licenza per il tenant specificato siano disponibili nell'interfaccia di amministrazione di Skype for business online, usare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="a8170-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a8170-111">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a8170-111">Related topics</span></span>
[<span data-ttu-id="a8170-112">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8170-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
