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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Cmdlet in Skype for business online che utilizzano un'identità utente

 


In Skype for business online, esistono diversi modi per fare riferimento a una singola identità utente:

  - Utilizzare il nome visualizzato del servizio di dominio Active Directory dell'utente. Ad esempio:
    
        -Identity "Ken Myer"

  - Utilizzare l'indirizzo SIP dell'utente. Ad esempio:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Utilizzare l'UPN dell'utente. Ad esempio:
    
        -Identity " kenmyer@litwareinc.com"

  - Utilizzare il nome distinto dei servizi di dominio Active Directory dell'utente. Ad esempio:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

I cmdlet seguenti accettano un'identità utente:

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

Tenere presente che non è necessario specificare l'identità di un utente quando si chiama uno dei cmdlet **Get-CS** . In questo caso, i cmdlet restituiscono tutte le istanze dell'elemento specificato. Ad esempio, questo comando restituisce informazioni su tutti gli utenti abilitati per Skype for business online:

    Get-CsOnlineUser

Il parametro Identity è obbligatorio solo se si desidera restituire le informazioni relative a un utente specifico:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

