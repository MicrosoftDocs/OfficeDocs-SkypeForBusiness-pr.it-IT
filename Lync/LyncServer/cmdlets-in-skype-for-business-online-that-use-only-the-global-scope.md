---
title: Cmdlet in Skype for business online che usano solo l'ambito globale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975263"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlet in Skype for business online che usano solo l'ambito globale

 


Alcune impostazioni di Skype for business online sono disponibili solo nell' *ambito globale*. Questo significa che esiste una singola raccolta di impostazioni che si applica a tutti gli utenti assegnati al tenant. Ogni tenant ha una raccolta univoca di impostazioni globali. Quando si usano cmdlet limitati all'ambito globale, il parametro Identity è facoltativo. Ad esempio, per recuperare le impostazioni di configurazione della riunione, è possibile usare questo comando:

    Get-CsMeetingConfiguration -Identity "global"

In alternativa, puoi omettere il parametro Identity e usare questo comando più semplice:

    Get-CsMeetingConfiguration

Poiché esiste una sola raccolta globale di impostazioni di configurazione della riunione, i due comandi restituiscono le stesse informazioni esatte. Il parametro Identity può essere omesso anche quando si usa uno dei cmdlet **set-CS** . Questi due comandi sono identici:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

I due comandi sono identici perché, per impostazione predefinita, Windows PowerShell modificherà la raccolta globale se non Includi il parametro Identity.

I cmdlet seguenti operano solo nell'ambito globale:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

Tieni presente che il cmdlet **Remove-CsVoicePolicy** è una sorta di anomalia. Prima di tutto, questo cmdlet richiede di includere il parametro Identity:

    Remove-CsVoicePolicy -Identity "global"

In secondo luogo, il cmdlet **Remove-CsVoicePolicy** non elimina effettivamente il criterio vocale globale; Skype for business online non consente di eliminare i criteri globali o le impostazioni di configurazione. Ciò che il cmdlet fa è consentire di reimpostare i valori predefiniti di tutte le proprietà del criterio vocale globale. Per impostazione predefinita, ad esempio, la proprietà AllowCallForwarding è impostata su false. Tuttavia, AllowCallForwarding potrebbe essere stato modificato, con il valore ora impostato su true. Quando si esegue il cmdlet **Remove-CsVoicePolicy** , la proprietà AllowCallForwarding tornerà al valore predefinito: false. La tabella seguente riepiloga questo scenario:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valore AllowCallForwarding</th>
<th>Scenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Valore predefinito</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Dopo la modifica dei criteri globali</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Dopo l'esecuzione del cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

