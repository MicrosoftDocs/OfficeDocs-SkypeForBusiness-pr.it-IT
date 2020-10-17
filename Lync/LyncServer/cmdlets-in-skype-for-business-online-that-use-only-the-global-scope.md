---
title: Cmdlet in Skype for business online che utilizzano solo l'ambito globale
description: Cmdlet in Skype for business online che utilizzano solo l'ambito globale.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f59806128ceea825a4cdd966e85852b98079b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545602"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlet in Skype for business online che utilizzano solo l'ambito globale

 


Un certo numero di impostazioni di Skype for business online sono disponibili solo nell' *ambito globale*. Questo significa che esiste una singola raccolta di impostazioni che si applica a tutti gli utenti assegnati a quel tenant. Ogni tenant ha una propria raccolta univoca di impostazioni globali. Quando si utilizzano i cmdlet limitati all'ambito globale, il parametro Identity è facoltativo. Ad esempio, per recuperare le impostazioni di configurazione delle riunioni, è possibile utilizzare questo comando:

    Get-CsMeetingConfiguration -Identity "global"

In alternativa, è possibile omettere il parametro Identity e utilizzare invece questo comando più semplice:

    Get-CsMeetingConfiguration

Poiché è presente una sola raccolta globale di impostazioni di configurazione delle riunioni, i due comandi restituiscono le stesse informazioni esatte. È inoltre possibile omettere il parametro Identity quando si utilizza uno dei cmdlet **set-CS** . Questi due comandi sono identici:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

I due comandi sono identici perché, per impostazione predefinita, Windows PowerShell modificherà la raccolta globale se non si include il parametro Identity.

I seguenti cmdlet operano solo nell'ambito globale:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Si noti che il cmdlet **Remove-CsVoicePolicy** è un elemento anomalo. In primo luogo, questo cmdlet richiede l'inclusione del parametro Identity:

    Remove-CsVoicePolicy -Identity "global"

In secondo luogo, il cmdlet **Remove-CsVoicePolicy** non elimina effettivamente il criterio vocale globale. Skype for business online non consente di eliminare i criteri globali o le impostazioni di configurazione. Il cmdlet consente di reimpostare i valori predefiniti di tutte le proprietà del criterio vocale globale. Ad esempio, per impostazione predefinita, la proprietà AllowCallForwarding è impostata su false. Tuttavia, AllowCallForwarding potrebbe essere stato modificato, con il valore ora impostato su true. Quando si esegue il cmdlet **Remove-CsVoicePolicy** , la proprietà AllowCallForwarding restituirà il valore predefinito: false. La tabella seguente riepiloga questo scenario:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valore di AllowCallForwarding</th>
<th>Scenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Valore predefinito</p></td>
</tr>
<tr class="even">
<td><p>Vero</p></td>
<td><p>Dopo che il criterio globale è stato modificato</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Dopo l'esecuzione del cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

