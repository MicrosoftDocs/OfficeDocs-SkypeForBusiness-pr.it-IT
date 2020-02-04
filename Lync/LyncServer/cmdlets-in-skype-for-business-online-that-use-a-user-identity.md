---
title: Cmdlet in Skype for business online che usano un'identità utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c29eb2aadefcb6a9f3ca9b5c11a49f7e41167a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728126"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="91d29-102">Cmdlet in Skype for business online che usano un'identità utente</span><span class="sxs-lookup"><span data-stu-id="91d29-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="91d29-103">In Skype for business online esiste una serie di modi diversi per fare riferimento a una singola identità utente:</span><span class="sxs-lookup"><span data-stu-id="91d29-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="91d29-104">Usare il nome visualizzato dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="91d29-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="91d29-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d29-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="91d29-106">Usare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="91d29-106">Use the user’s SIP address.</span></span> <span data-ttu-id="91d29-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d29-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="91d29-108">Usare l'UPN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="91d29-108">Use the user’s UPN.</span></span> <span data-ttu-id="91d29-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d29-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="91d29-110">Usare il nome distinto dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="91d29-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="91d29-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d29-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="91d29-112">I cmdlet seguenti accettano un'identità utente:</span><span class="sxs-lookup"><span data-stu-id="91d29-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="91d29-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="91d29-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="91d29-125">Tieni presente che non devi specificare l'identità di un utente quando chiami uno dei cmdlet **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="91d29-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="91d29-126">In questo caso, i cmdlet restituiscono tutte le istanze dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="91d29-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="91d29-127">Ad esempio, questo comando restituisce informazioni su tutti gli utenti abilitati per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="91d29-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="91d29-128">Il parametro Identity è obbligatorio solo se si vogliono restituire informazioni per un utente specifico:</span><span class="sxs-lookup"><span data-stu-id="91d29-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="91d29-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91d29-129">See Also</span></span>


[<span data-ttu-id="91d29-130">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="91d29-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="91d29-131">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="91d29-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

