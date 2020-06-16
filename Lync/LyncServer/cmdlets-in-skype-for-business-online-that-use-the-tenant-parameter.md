---
title: Cmdlet in Skype for business online che utilizzano il parametro tenant
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755042"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="fc303-102">Cmdlet in Skype for business online che utilizzano il parametro tenant</span><span class="sxs-lookup"><span data-stu-id="fc303-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="fc303-103">Quando si modificano le impostazioni del provider pubblico, è sempre necessario fornire un'identità tenant. Questo è vero anche se si dispone solo di un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="fc303-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="fc303-104">Ad esempio, questo comando imposta Windows Live come l'unico provider pubblico a cui gli utenti possono comunicare:</span><span class="sxs-lookup"><span data-stu-id="fc303-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="fc303-105">Fortunatamente, non è necessario digitare l'ID tenant (ad esempio, bf19b7db-6960-41e5-A139-2aa373474354) ogni volta che si esegue uno di questi cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc303-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="fc303-106">In alternativa, è possibile recuperare l'ID tenant eseguendo il cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , archiviando l'ID tenant in una variabile e quindi utilizzando tale variabile quando si chiama uno degli altri cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc303-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="fc303-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fc303-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="fc303-108">In alternativa, è possibile eseguire questa operazione in un singolo comando recuperando l'ID tenant e quindi eseguendo il piping del valore sul cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="fc303-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="fc303-109">Non è necessario specificare l'ID tenant quando si chiama il cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="fc303-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="fc303-110">Questo comando restituisce informazioni sul tenant:</span><span class="sxs-lookup"><span data-stu-id="fc303-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="fc303-111">I cmdlet seguenti accettano un'identità tenant.</span><span class="sxs-lookup"><span data-stu-id="fc303-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="fc303-112">Tuttavia, in questi casi, il parametro è facoltativo e non è necessario immetterlo quando si chiama il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc303-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="fc303-113">Invece, Windows PowerShell entrerà in modo efficace nell'identità del tenant per l'utente in base al tenant di Skype for business online a cui è attualmente connesso:</span><span class="sxs-lookup"><span data-stu-id="fc303-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="fc303-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fc303-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fc303-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fc303-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fc303-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fc303-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="fc303-120">Ad esempio, è possibile chiamare il cmdlet **Get-CsTenantFederationConfiguration** utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fc303-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="fc303-121">Sebbene non sia necessario, è possibile includere il parametro tenant quando si chiama Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="fc303-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="fc303-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc303-122">See Also</span></span>


[<span data-ttu-id="fc303-123">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="fc303-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="fc303-124">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fc303-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

