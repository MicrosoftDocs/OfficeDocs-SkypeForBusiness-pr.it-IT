---
title: Verifica della replica nel dominio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: "Per verificare la replica della preparazione del dominio eseguita nel passaggio 1: Preparare lo schema, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell. Per eseguire il cmdlet di Windows PowerShell, effettuare l'accesso in qualità di membro del gruppo Domain Admins a un computer membro del dominio che è stato preparato. Eseguire le operazioni seguenti:"
ms.openlocfilehash: e02708e7b995c2f83e82080be60caa1e251f6b9438a75d93c7d74f47d812db93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319279"
---
# <a name="verify-replication-in-the-domain"></a>Verificare la replica nel dominio
 
Per verificare la replica della preparazione del dominio eseguita nel passaggio **1:** Preparare lo schema, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell. Per eseguire il cmdlet di Windows PowerShell, effettuare l'accesso in qualità di membro del gruppo Domain Admins a un computer membro del dominio che è stato preparato. Eseguire le operazioni seguenti:
  
1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
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
    

