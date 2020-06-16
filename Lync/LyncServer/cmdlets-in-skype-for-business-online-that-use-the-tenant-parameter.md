---
title: Cmdlet in Skype for business online che utilizzano il parametro tenant
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755042"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlet in Skype for business online che utilizzano il parametro tenant

 


Quando si modificano le impostazioni del provider pubblico, è sempre necessario fornire un'identità tenant. Questo è vero anche se si dispone solo di un singolo tenant. Ad esempio, questo comando imposta Windows Live come l'unico provider pubblico a cui gli utenti possono comunicare:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Fortunatamente, non è necessario digitare l'ID tenant (ad esempio, bf19b7db-6960-41e5-A139-2aa373474354) ogni volta che si esegue uno di questi cmdlet. In alternativa, è possibile recuperare l'ID tenant eseguendo il cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , archiviando l'ID tenant in una variabile e quindi utilizzando tale variabile quando si chiama uno degli altri cmdlet. Ad esempio:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

In alternativa, è possibile eseguire questa operazione in un singolo comando recuperando l'ID tenant e quindi eseguendo il piping del valore sul cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Non è necessario specificare l'ID tenant quando si chiama il cmdlet **Get-CsTenant** . Questo comando restituisce informazioni sul tenant:

    Get-CsTenant

I cmdlet seguenti accettano un'identità tenant. Tuttavia, in questi casi, il parametro è facoltativo e non è necessario immetterlo quando si chiama il cmdlet. Invece, Windows PowerShell entrerà in modo efficace nell'identità del tenant per l'utente in base al tenant di Skype for business online a cui è attualmente connesso:

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Ad esempio, è possibile chiamare il cmdlet **Get-CsTenantFederationConfiguration** utilizzando il comando seguente:

    Get-CsTenantFederationConfiguration

Sebbene non sia necessario, è possibile includere il parametro tenant quando si chiama Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Vedere anche


[Identità, ambiti e tenant in Skype for business online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

