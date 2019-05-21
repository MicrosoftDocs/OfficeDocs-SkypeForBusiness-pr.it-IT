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
f1keywords: None
ms.custom:
- PowerShell
description: Usa Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for business online.
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284691"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="2c27a-103">Gestire le organizzazioni di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="2c27a-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="2c27a-104">Puoi trovare informazioni sul tenant di Skype for business online usando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2c27a-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="2c27a-105">Gestire i tenant di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="2c27a-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="2c27a-106">Per restituire informazioni sul tenant di Skype for business online, chiama il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2c27a-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="2c27a-107">Per restituire solo il nome e l'ID del tenant, usare questo comando.</span><span class="sxs-lookup"><span data-stu-id="2c27a-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="2c27a-108">Il valore del parametro _ID tenant_ è obbligatorio quando si utilizzano cmdlet, ad esempio [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c27a-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="2c27a-109">Per informazioni sul fatto che le informazioni sulla licenza per il tenant specificato siano disponibili nell'interfaccia di amministrazione di Skype for business online, usare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="2c27a-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2c27a-110">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2c27a-110">Related topics</span></span>
[<span data-ttu-id="2c27a-111">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c27a-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
