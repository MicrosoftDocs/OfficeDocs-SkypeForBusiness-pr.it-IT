---
title: Cmdlet in Skype for business online che usano il parametro tenant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728016"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="22a0a-102">Cmdlet in Skype for business online che usano il parametro tenant</span><span class="sxs-lookup"><span data-stu-id="22a0a-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="22a0a-103">Quando si modificano le impostazioni del provider pubblico, è sempre necessario fornire un'identità del tenant. Questo vale anche se hai solo un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="22a0a-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="22a0a-104">Questo comando, ad esempio, imposta Windows Live come l'unico provider pubblico a cui gli utenti possono comunicare:</span><span class="sxs-lookup"><span data-stu-id="22a0a-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="22a0a-105">Fortunatamente, non è necessario digitare l'ID tenant, ad esempio bf19b7db-6960-41e5-A139-2aa373474354, ogni volta che si esegue uno di questi cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22a0a-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="22a0a-106">Puoi invece recuperare l'ID tenant eseguendo il cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , archiviando l'ID tenant in una variabile e usando quindi tale variabile quando chiami uno degli altri cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22a0a-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="22a0a-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="22a0a-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="22a0a-108">In alternativa, è possibile eseguire questa operazione in un singolo comando recuperando l'ID tenant e quindi eseguendo il piping di tale valore al cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="22a0a-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="22a0a-109">Non è necessario specificare l'ID tenant quando si chiama il cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="22a0a-110">Questo comando restituisce informazioni sul tenant:</span><span class="sxs-lookup"><span data-stu-id="22a0a-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="22a0a-111">I cmdlet seguenti accettano un'identità tenant.</span><span class="sxs-lookup"><span data-stu-id="22a0a-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="22a0a-112">In questi casi, tuttavia, il parametro è facoltativo e non deve essere immesso quando si chiama il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22a0a-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="22a0a-113">Windows PowerShell consentirà di immettere effettivamente l'identità del tenant in base al tenant di Skype for business online a cui si è attualmente connessi:</span><span class="sxs-lookup"><span data-stu-id="22a0a-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="22a0a-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="22a0a-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="22a0a-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="22a0a-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="22a0a-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="22a0a-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="22a0a-120">Ad esempio, il cmdlet **Get-CsTenantFederationConfiguration** può essere chiamato usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="22a0a-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="22a0a-121">Sebbene non sia obbligatorio, puoi includere il parametro tenant quando chiami Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="22a0a-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="22a0a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a0a-122">See Also</span></span>


[<span data-ttu-id="22a0a-123">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="22a0a-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="22a0a-124">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="22a0a-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

