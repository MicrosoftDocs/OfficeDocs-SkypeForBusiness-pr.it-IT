---
title: Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza
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
ms.openlocfilehash: e0ae3167b1cb6c83b46e4f9d4846e8863b43515d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001721"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza

 


Per restituire informazioni su tutti i provider di servizi di audioconferenza a cui l'organizzazione ha contratto, è possibile chiamare il cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) senza parametri:

    Get-CsAudioConferencingProvider

Se si desidera limitare i dati restituiti a un singolo provider (in questo esempio, il provider contoso audio Services), utilizzare il parametro Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

È presente un solo cmdlet Skype for business online che accetta un ID provider di servizi di audioconferenza:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

