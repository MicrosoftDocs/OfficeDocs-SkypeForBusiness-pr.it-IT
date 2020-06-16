---
title: Cmdlet in Skype for business online che non utilizzano un ambito o un'identità
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ade4dee78fff151530e0d76279fdbfaeade720b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755316"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlet in Skype for business online che non utilizzano un ambito o un'identità

 


I cmdlet utilizzati per la modifica degli elenchi consentiti e degli elenchi bloccati (elenchi che determinano le organizzazioni esterne a cui gli utenti sono autorizzati a comunicare) non utilizzano un ambito o un'identità. Infatti, il cmdlet **New-CsEdgeAllowAllKnownDomains** non dispone di alcun parametro. I cmdlet che non utilizzano un ambito o un'identità sono i seguenti:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

Si noti che, con il cmdlet **New-CsEdgeAllowList** e il cmdlet **New-CsEdgeDomainPattern** , è necessario includere il parametro Domain. Ad esempio:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

