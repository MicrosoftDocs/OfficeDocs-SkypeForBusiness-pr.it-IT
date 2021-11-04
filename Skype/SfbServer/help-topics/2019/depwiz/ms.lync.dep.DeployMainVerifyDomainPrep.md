---
title: Verifica della replica nel dominio
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: "Per verificare la replica della preparazione del dominio eseguita nel Passaggio 1: Preparare lo schema, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell. Per eseguire il cmdlet di Windows PowerShell, effettuare l'accesso in qualità di membro del gruppo Domain Admins a un computer membro del dominio che è stato preparato. Eseguire le operazioni seguenti:"
ms.openlocfilehash: f4528bad6aa0c1ab03b3b4d2273b27fa517d44e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738532"
---
# <a name="verify-replication-in-the-domain"></a>Verificare la replica nel dominio
 
Per verificare la replica della preparazione del dominio eseguita nel passaggio **1: Preparare** lo schema, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell. Per eseguire il cmdlet di Windows PowerShell, effettuare l'accesso in qualità di membro del gruppo Domain Admins a un computer membro del dominio che è stato preparato. Eseguire le operazioni seguenti:
  
1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi fare clic su Skype for Business Server **Management Shell.**
    
2. In Windows PowerShell digitare quanto segue:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Ad esempio:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Il parametro GlobalSettingsDomainController consente di indicare dove vengono archiviate le impostazioni globali. Se le impostazioni sono archiviate nel contenitore System (tipico delle distribuzioni di aggiornamento in cui non è stata eseguita la migrazione dell'impostazione globale nel contenitore Configuration), si definisce un controller di dominio nella radice della foresta di Servizi di dominio Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore Configuration e facciano riferimento a qualsiasi controller di dominio in Active Directory. 
  
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale. Questo cmdlet restituirà il valore **LC_DOMAIN_SETTINGS_STATE_READY** se la preparazione del dominio ha avuto esito positivo.
    

