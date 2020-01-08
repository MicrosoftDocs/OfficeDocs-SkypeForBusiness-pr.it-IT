---
title: Cmdlet in Skype for business online che usano l'ambito globale e l'ambito dei tag
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40977915"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlet in Skype for business online che usano l'ambito globale e l'ambito dei tag

 


In Skype for business online i criteri possono essere configurati sia nell'ambito *globale* che nell'ambito del *tag* (o nell'ambito *per utente*). Quando si usano i cmdlet **Get-CS** , non è necessario specificare un ambito o un'identità. Se si chiama uno di questi cmdlet senza parametri, verranno restituiti tutti gli elementi rilevanti. Ad esempio, questo comando restituisce informazioni su tutti i criteri di accesso esterno:

    Get-CsExternalAccessPolicy

Se si vogliono limitare i dati restituiti, è necessario includere solo il parametro Identity o il parametro Filter. Ad esempio, per restituire solo il criterio globale, usare questo comando:

    Get-CsExternalAccessPolicy -Identity "global"

Per restituire un criterio per utente con l'identità "RedmondAccessPolicy", usare questo comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Quando si fa riferimento a un criterio per utente, il <STRONG>prefisso</STRONG> di tag è facoltativo. Questa sintassi, che include il prefisso, è valida anche:<BR>Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"



Per restituire tutti i criteri eccetto i criteri globali, ovvero tutti i criteri per utente, usare questo comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

I cmdlet seguenti funzionano sia per l'ambito globale che per l'ambito per utente (tag):

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Nonostante il nome, i dial plan sono, in termini funzionali, i criteri. Viene usato il <EM>dial plan</EM> di termine anziché, ad esempio, i criteri di chiamata, per preservare la terminologia usata con le versioni precedenti di Lync Server.



## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

