---
title: Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755118"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag

 


I cmdlet **Grant-CS** (utilizzati per l'assegnazione di criteri agli utenti) richiedono due identificatori: un'identità utente (il parametro Identity) e l'identità di un criterio per utente (il parametro PolicyName). Ad esempio, per assegnare il criterio vocale, RedmondVoicePolicy, all'utente Ken, è possibile utilizzare il seguente comando:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Quando si assegnano criteri agli utenti, è necessario tenere presente due aspetti. Per prima cosa, è possibile assegnare solo i criteri per utente. Non è possibile assegnare il criterio globale a un utente. Ad esempio, questo comando avrà esito negativo:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Questo comando ha esito negativo perché non è necessario assegnare il criterio globale. Se si desidera gestire un utente utilizzando il criterio globale, è sufficiente assicurarsi di non assegnare un criterio per utente. Se a un utente non è stato assegnato alcun criterio per utente, l'utente verrà gestito automaticamente utilizzando il criterio globale.


> [!NOTE]  
> Che cosa succede se all'utente sono stati assegnati in precedenza un criterio per utente e si desidera annullare l'assegnazione di tale criterio e l'utente deve invece essere gestito dal criterio globale? In tal caso, si utilizzerà la seguente sintassi, che annulla l'assegnazione di un criterio per utente concedendo a un criterio null l'utente:<BR>Grant-CsVoicePolicy – Identity "Ken" – PolicyName $Null



In secondo luogo, tenere presente che i criteri per utente vengono creati nell'ambito dei tag. Tuttavia, è possibile omettere il **prefisso** del tag quando si specifica il nome di un criterio. Questi due comandi sono identici:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Se si desidera restituire le identità per tutti i criteri per utente (o almeno per tutti i criteri per utente di tipo specificato, ad esempio i criteri vocali), utilizzare un comando simile al seguente:

    Get-CsVoicePolicy -Filter "tag:*"

I cmdlet seguenti utilizzano sia l'identità dell'utente che l'ambito dei tag:

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

