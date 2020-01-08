---
title: Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2957fbc63a885a1c2e1f053cffbf7439d2b648d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40978841"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="b0b58-102">Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="b0b58-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="b0b58-103">Per restituire informazioni su tutti i provider di servizi di audioconferenza con cui l'organizzazione ha contratto, è possibile chiamare semplicemente il cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) senza parametri:</span><span class="sxs-lookup"><span data-stu-id="b0b58-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="b0b58-104">Se si vogliono limitare i dati restituiti a un singolo provider (in questo esempio, il provider contoso audio Services), usare il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="b0b58-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="b0b58-105">Esiste un solo cmdlet Skype for business online che accetta un ID del provider di servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="b0b58-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="b0b58-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0b58-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="b0b58-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0b58-107">See Also</span></span>


[<span data-ttu-id="b0b58-108">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="b0b58-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="b0b58-109">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0b58-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

