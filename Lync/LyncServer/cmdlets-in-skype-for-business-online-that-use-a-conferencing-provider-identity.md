---
title: Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza
description: Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ab4fb410878ca73314b73737948d9961462c87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545732"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="98dde-103">Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="98dde-103">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="98dde-104">Per restituire informazioni su tutti i provider di servizi di audioconferenza a cui l'organizzazione ha contratto, è possibile chiamare il cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) senza parametri:</span><span class="sxs-lookup"><span data-stu-id="98dde-104">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="98dde-105">Se si desidera limitare i dati restituiti a un singolo provider (in questo esempio, il provider contoso audio Services), utilizzare il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="98dde-105">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="98dde-106">È presente un solo cmdlet Skype for business online che accetta un ID provider di servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="98dde-106">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="98dde-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98dde-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="98dde-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98dde-108">See Also</span></span>


[<span data-ttu-id="98dde-109">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="98dde-109">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="98dde-110">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98dde-110">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

