---
title: Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9dc5438a0fe246b1e988d60a0e6ce1ac3d3f6d67
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726716"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="d14f1-102">Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="d14f1-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="d14f1-103">Per restituire informazioni su tutti i provider di servizi di audioconferenza con cui l'organizzazione ha contratto, è possibile chiamare semplicemente il cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) senza parametri:</span><span class="sxs-lookup"><span data-stu-id="d14f1-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="d14f1-104">Se si vogliono limitare i dati restituiti a un singolo provider (in questo esempio, il provider contoso audio Services), usare il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="d14f1-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="d14f1-105">Esiste un solo cmdlet Skype for business online che accetta un ID del provider di servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="d14f1-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="d14f1-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d14f1-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="d14f1-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14f1-107">See Also</span></span>


[<span data-ttu-id="d14f1-108">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="d14f1-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="d14f1-109">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d14f1-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

