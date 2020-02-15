---
title: Cmdlet in Skype for business online che utilizzano un'identità utente
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
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001261"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="a8fdb-102">Cmdlet in Skype for business online che utilizzano un'identità utente</span><span class="sxs-lookup"><span data-stu-id="a8fdb-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="a8fdb-103">In Skype for business online, esistono diversi modi per fare riferimento a una singola identità utente:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="a8fdb-104">Utilizzare il nome visualizzato del servizio di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="a8fdb-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="a8fdb-106">Utilizzare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-106">Use the user’s SIP address.</span></span> <span data-ttu-id="a8fdb-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a8fdb-108">Utilizzare l'UPN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-108">Use the user’s UPN.</span></span> <span data-ttu-id="a8fdb-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="a8fdb-110">Utilizzare il nome distinto dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="a8fdb-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="a8fdb-112">I cmdlet seguenti accettano un'identità utente:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="a8fdb-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a8fdb-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="a8fdb-125">Tenere presente che non è necessario specificare l'identità di un utente quando si chiama uno dei cmdlet **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="a8fdb-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="a8fdb-126">In questo caso, i cmdlet restituiscono tutte le istanze dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="a8fdb-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="a8fdb-127">Ad esempio, questo comando restituisce informazioni su tutti gli utenti abilitati per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="a8fdb-128">Il parametro Identity è obbligatorio solo se si desidera restituire le informazioni relative a un utente specifico:</span><span class="sxs-lookup"><span data-stu-id="a8fdb-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="a8fdb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8fdb-129">See Also</span></span>


[<span data-ttu-id="a8fdb-130">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a8fdb-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a8fdb-131">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a8fdb-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

