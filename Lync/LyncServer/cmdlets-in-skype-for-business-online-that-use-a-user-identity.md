---
title: Cmdlet in Skype for business online che usano un'identità utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40978635"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="e5946-102">Cmdlet in Skype for business online che usano un'identità utente</span><span class="sxs-lookup"><span data-stu-id="e5946-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="e5946-103">In Skype for business online esiste una serie di modi diversi per fare riferimento a una singola identità utente:</span><span class="sxs-lookup"><span data-stu-id="e5946-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="e5946-104">Usare il nome visualizzato dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5946-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="e5946-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5946-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="e5946-106">Usare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5946-106">Use the user’s SIP address.</span></span> <span data-ttu-id="e5946-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5946-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e5946-108">Usare l'UPN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5946-108">Use the user’s UPN.</span></span> <span data-ttu-id="e5946-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5946-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="e5946-110">Usare il nome distinto dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5946-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="e5946-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5946-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="e5946-112">I cmdlet seguenti accettano un'identità utente:</span><span class="sxs-lookup"><span data-stu-id="e5946-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="e5946-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e5946-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="e5946-125">Tieni presente che non devi specificare l'identità di un utente quando chiami uno dei cmdlet **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="e5946-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="e5946-126">In questo caso, i cmdlet restituiscono tutte le istanze dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="e5946-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="e5946-127">Ad esempio, questo comando restituisce informazioni su tutti gli utenti abilitati per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="e5946-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="e5946-128">Il parametro Identity è obbligatorio solo se si vogliono restituire informazioni per un utente specifico:</span><span class="sxs-lookup"><span data-stu-id="e5946-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="e5946-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5946-129">See Also</span></span>


[<span data-ttu-id="e5946-130">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="e5946-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e5946-131">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e5946-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

