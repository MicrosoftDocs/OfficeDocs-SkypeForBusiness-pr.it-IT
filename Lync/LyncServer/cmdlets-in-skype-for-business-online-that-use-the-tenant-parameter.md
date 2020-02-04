---
title: Cmdlet in Skype for business online che usano il parametro tenant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728016"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlet in Skype for business online che usano il parametro tenant

 


Quando si modificano le impostazioni del provider pubblico, è sempre necessario fornire un'identità del tenant. Questo vale anche se hai solo un singolo tenant. Questo comando, ad esempio, imposta Windows Live come l'unico provider pubblico a cui gli utenti possono comunicare:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Fortunatamente, non è necessario digitare l'ID tenant, ad esempio bf19b7db-6960-41e5-A139-2aa373474354, ogni volta che si esegue uno di questi cmdlet. Puoi invece recuperare l'ID tenant eseguendo il cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , archiviando l'ID tenant in una variabile e usando quindi tale variabile quando chiami uno degli altri cmdlet. Ad esempio:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

In alternativa, è possibile eseguire questa operazione in un singolo comando recuperando l'ID tenant e quindi eseguendo il piping di tale valore al cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Non è necessario specificare l'ID tenant quando si chiama il cmdlet **Get-CsTenant** . Questo comando restituisce informazioni sul tenant:

    Get-CsTenant

I cmdlet seguenti accettano un'identità tenant. In questi casi, tuttavia, il parametro è facoltativo e non deve essere immesso quando si chiama il cmdlet. Windows PowerShell consentirà di immettere effettivamente l'identità del tenant in base al tenant di Skype for business online a cui si è attualmente connessi:

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

Ad esempio, il cmdlet **Get-CsTenantFederationConfiguration** può essere chiamato usando questo comando:

    Get-CsTenantFederationConfiguration

Sebbene non sia obbligatorio, puoi includere il parametro tenant quando chiami Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

