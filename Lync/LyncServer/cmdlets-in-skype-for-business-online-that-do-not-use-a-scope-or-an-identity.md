---
title: Cmdlet in Skype for business online che non usano un ambito o un'identità
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975981"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlet in Skype for business online che non usano un ambito o un'identità

 


I cmdlet usati per la modifica degli elenchi consentiti e degli elenchi bloccati (elenchi che determinano le organizzazioni esterne con cui gli utenti possono comunicare) non usano né un ambito né un'identità. Infatti, il cmdlet **New-CsEdgeAllowAllKnownDomains** non ha alcun tipo di parametro. I cmdlet che non usano né un ambito né un'identità sono i seguenti:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

Tieni presente che, sia con il cmdlet **New-CsEdgeAllowList** che con il cmdlet **New-CsEdgeDomainPattern** , devi includere il parametro Domain. Ad esempio:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

