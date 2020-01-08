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

