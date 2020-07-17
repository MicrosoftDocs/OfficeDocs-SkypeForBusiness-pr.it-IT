---
title: Cmdlet in Skype for business online che utilizzano un'identità utente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755108"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="5a08b-102">Cmdlet in Skype for business online che utilizzano un'identità utente</span><span class="sxs-lookup"><span data-stu-id="5a08b-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="5a08b-103">In Skype for business online, esistono diversi modi per fare riferimento a una singola identità utente:</span><span class="sxs-lookup"><span data-stu-id="5a08b-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="5a08b-104">Utilizzare il nome visualizzato del servizio di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a08b-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="5a08b-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a08b-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="5a08b-106">Utilizzare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a08b-106">Use the user’s SIP address.</span></span> <span data-ttu-id="5a08b-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a08b-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5a08b-108">Utilizzare l'UPN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a08b-108">Use the user’s UPN.</span></span> <span data-ttu-id="5a08b-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a08b-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="5a08b-110">Utilizzare il nome distinto dei servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a08b-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="5a08b-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a08b-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="5a08b-112">I cmdlet seguenti accettano un'identità utente:</span><span class="sxs-lookup"><span data-stu-id="5a08b-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="5a08b-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a08b-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="5a08b-125">Tenere presente che non è necessario specificare l'identità di un utente quando si chiama uno dei cmdlet **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="5a08b-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="5a08b-126">In questo caso, i cmdlet restituiscono tutte le istanze dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="5a08b-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="5a08b-127">Ad esempio, questo comando restituisce informazioni su tutti gli utenti abilitati per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="5a08b-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="5a08b-128">Il parametro Identity è obbligatorio solo se si desidera restituire le informazioni relative a un utente specifico:</span><span class="sxs-lookup"><span data-stu-id="5a08b-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="5a08b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a08b-129">See Also</span></span>


[<span data-ttu-id="5a08b-130">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="5a08b-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="5a08b-131">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a08b-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

