---
title: Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755076"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag

 


In Skype for business online, i criteri possono essere configurati nell'ambito *globale* o nell'ambito dei *tag* (o nell'ambito *per utente*). Quando si utilizzano i cmdlet **Get-CS** , non è necessario specificare un ambito o un'identità. Se si chiama uno di questi cmdlet senza alcun parametro, verranno restituiti tutti gli elementi rilevanti. Ad esempio, questo comando restituisce informazioni su tutti i criteri di accesso esterno:

    Get-CsExternalAccessPolicy

Se si desidera limitare i dati restituiti, è necessario includere solo il parametro Identity o il parametro Filter. Ad esempio, per restituire solo il criterio globale, utilizzare il seguente comando:

    Get-CsExternalAccessPolicy -Identity "global"

Per restituire un criterio per utente con identità "RedmondAccessPolicy", utilizzare questo comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Quando si fa riferimento a un criterio per utente, il <STRONG>prefisso</STRONG> di tag è facoltativo. Questa sintassi, che include il prefisso, è valida anche:<BR>Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"



Per restituire tutti i criteri, ad eccezione dei criteri globali, ovvero tutti i criteri per utente, utilizzare questo comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

I cmdlet seguenti agiscono sull'ambito globale e sull'ambito per utente (tag):

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Nonostante il nome, i dial plan sono, funzionalmente, i criteri. Viene utilizzato il <EM>dial plan</EM> di termini anziché, ad esempio, i criteri di composizione per mantenere la terminologia utilizzata con le versioni precedenti di Lync Server.



## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

