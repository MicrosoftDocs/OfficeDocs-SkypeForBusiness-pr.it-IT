---
title: Cmdlet in Skype for business online che usano solo l'ambito globale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728106"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="47610-102">Cmdlet in Skype for business online che usano solo l'ambito globale</span><span class="sxs-lookup"><span data-stu-id="47610-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="47610-103">Alcune impostazioni di Skype for business online sono disponibili solo nell' *ambito globale*.</span><span class="sxs-lookup"><span data-stu-id="47610-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="47610-104">Questo significa che esiste una singola raccolta di impostazioni che si applica a tutti gli utenti assegnati al tenant.</span><span class="sxs-lookup"><span data-stu-id="47610-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="47610-105">Ogni tenant ha una raccolta univoca di impostazioni globali. Quando si usano cmdlet limitati all'ambito globale, il parametro Identity è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="47610-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="47610-106">Ad esempio, per recuperare le impostazioni di configurazione della riunione, è possibile usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="47610-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="47610-107">In alternativa, puoi omettere il parametro Identity e usare questo comando più semplice:</span><span class="sxs-lookup"><span data-stu-id="47610-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="47610-108">Poiché esiste una sola raccolta globale di impostazioni di configurazione della riunione, i due comandi restituiscono le stesse informazioni esatte.</span><span class="sxs-lookup"><span data-stu-id="47610-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="47610-109">Il parametro Identity può essere omesso anche quando si usa uno dei cmdlet **set-CS** .</span><span class="sxs-lookup"><span data-stu-id="47610-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="47610-110">Questi due comandi sono identici:</span><span class="sxs-lookup"><span data-stu-id="47610-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="47610-111">I due comandi sono identici perché, per impostazione predefinita, Windows PowerShell modificherà la raccolta globale se non Includi il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="47610-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="47610-112">I cmdlet seguenti operano solo nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="47610-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="47610-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="47610-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="47610-123">Tieni presente che il cmdlet **Remove-CsVoicePolicy** è una sorta di anomalia.</span><span class="sxs-lookup"><span data-stu-id="47610-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="47610-124">Prima di tutto, questo cmdlet richiede di includere il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="47610-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="47610-125">In secondo luogo, il cmdlet **Remove-CsVoicePolicy** non elimina effettivamente il criterio vocale globale; Skype for business online non consente di eliminare i criteri globali o le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="47610-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="47610-126">Ciò che il cmdlet fa è consentire di reimpostare i valori predefiniti di tutte le proprietà del criterio vocale globale.</span><span class="sxs-lookup"><span data-stu-id="47610-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="47610-127">Per impostazione predefinita, ad esempio, la proprietà AllowCallForwarding è impostata su false.</span><span class="sxs-lookup"><span data-stu-id="47610-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="47610-128">Tuttavia, AllowCallForwarding potrebbe essere stato modificato, con il valore ora impostato su true.</span><span class="sxs-lookup"><span data-stu-id="47610-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="47610-129">Quando si esegue il cmdlet **Remove-CsVoicePolicy** , la proprietà AllowCallForwarding tornerà al valore predefinito: false.</span><span class="sxs-lookup"><span data-stu-id="47610-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="47610-130">La tabella seguente riepiloga questo scenario:</span><span class="sxs-lookup"><span data-stu-id="47610-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47610-131">Valore AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="47610-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="47610-132">Scenario</span><span class="sxs-lookup"><span data-stu-id="47610-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47610-133">False</span><span class="sxs-lookup"><span data-stu-id="47610-133">False</span></span></p></td>
<td><p><span data-ttu-id="47610-134">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="47610-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47610-135">True</span><span class="sxs-lookup"><span data-stu-id="47610-135">True</span></span></p></td>
<td><p><span data-ttu-id="47610-136">Dopo la modifica dei criteri globali</span><span class="sxs-lookup"><span data-stu-id="47610-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47610-137">False</span><span class="sxs-lookup"><span data-stu-id="47610-137">False</span></span></p></td>
<td><p><span data-ttu-id="47610-138">Dopo l'esecuzione del cmdlet <strong>Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="47610-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="47610-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47610-139">See Also</span></span>


[<span data-ttu-id="47610-140">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="47610-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="47610-141">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="47610-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

