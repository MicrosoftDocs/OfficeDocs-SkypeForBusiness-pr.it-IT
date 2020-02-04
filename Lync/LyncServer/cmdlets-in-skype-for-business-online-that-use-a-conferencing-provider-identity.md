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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza

 


Per restituire informazioni su tutti i provider di servizi di audioconferenza con cui l'organizzazione ha contratto, è possibile chiamare semplicemente il cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) senza parametri:

    Get-CsAudioConferencingProvider

Se si vogliono limitare i dati restituiti a un singolo provider (in questo esempio, il provider contoso audio Services), usare il parametro Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Esiste un solo cmdlet Skype for business online che accetta un ID del provider di servizi di audioconferenza:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

