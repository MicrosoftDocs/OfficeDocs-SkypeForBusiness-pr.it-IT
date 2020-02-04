---
title: Cmdlet in Skype for business online che usano l'identità dell'utente e l'ambito dei tag
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727566"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlet in Skype for business online che usano l'identità dell'utente e l'ambito dei tag

 


I cmdlet **Grant-CS** (usati per l'assegnazione di criteri agli utenti) richiedono due identificatori: un'identità utente (il parametro Identity) e l'identità di un criterio per utente (il parametro PolicyName). Ad esempio, per assegnare il criterio vocale, RedmondVoicePolicy, all'utente Ken per l'uso, è possibile usare il comando seguente:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Quando si assegnano criteri agli utenti, è necessario tenere presente due aspetti. In primo luogo, possono essere assegnati solo i criteri per utente. Non è possibile assegnare il criterio globale a un utente. Ad esempio, questo comando avrà esito negativo:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Questo comando non riesce perché non è necessario assegnare il criterio globale. Se si vuole gestire un utente usando il criterio globale, assicurarsi che l'utente non assegni un criterio per utente. Se non è stato assegnato alcun criterio per utente a un utente, l'utente verrà gestito automaticamente tramite il criterio globale.


> [!NOTE]  
> Che cosa succede se all'utente è stato assegnato in precedenza un criterio per utente e si vuole annullare l'assegnazione dei criteri e avere l'utente gestito dal criterio globale? In questo caso, utilizzerai prima di tutto la sintassi seguente, che annulla l'assegnazione di un criterio per utente concedendo un criterio null per l'utente:<BR>Grant-CsVoicePolicy-Identity "Ken"-PolicyName $Null



In secondo luogo, tieni presente che i criteri per utente vengono creati nell'ambito del tag. Tuttavia, è possibile omettere il **prefisso** del contrassegno quando si specifica un nome di criterio. Questi due comandi sono identici:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Se si vuole restituire le identità per tutti i criteri per utente (o almeno per tutti i criteri per utente di tipo specificato, ad esempio i criteri vocali), usare un comando simile al seguente:

    Get-CsVoicePolicy -Filter "tag:*"

I cmdlet seguenti sfruttano sia l'identità dell'utente che l'ambito dei tag:

  - [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

