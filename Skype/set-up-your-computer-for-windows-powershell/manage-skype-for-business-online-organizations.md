---
title: Gestire Skype per le organizzazioni aziendali Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: Utilizzare il cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration e Windows PowerShell per ottenere informazioni sui Skype per tenant Business Online.
ms.openlocfilehash: cab693fa153eae99ac605981112a30ec09f49920
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="118fa-103">Gestire Skype per le organizzazioni aziendali Online</span><span class="sxs-lookup"><span data-stu-id="118fa-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="118fa-104">È possibile trovare informazioni la Skype per tenant Business Online utilizzando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="118fa-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="118fa-105">Gestire Skype per tenant Business Online</span><span class="sxs-lookup"><span data-stu-id="118fa-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="118fa-106">Per restituire informazioni sui Skype per tenant Business Online, chiamare il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza alcun parametro aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="118fa-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="118fa-107">Per restituire solo il tenant nome e l'ID, utilizzare questo comando.</span><span class="sxs-lookup"><span data-stu-id="118fa-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="118fa-108">Il valore del parametro _ID tenant_ è necessario quando si esegue cmdlet quali [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="118fa-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="118fa-109">Per informazioni sugli indica se le informazioni sulle licenze per il tenant specificato sono disponibile in Skype per interfaccia di amministrazione di Business in linea, utilizzare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="118fa-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="118fa-110">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="118fa-110">Related topics</span></span>
[<span data-ttu-id="118fa-111">Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="118fa-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
