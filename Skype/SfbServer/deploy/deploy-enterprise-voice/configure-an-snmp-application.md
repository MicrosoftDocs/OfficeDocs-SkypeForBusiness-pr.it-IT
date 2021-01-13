---
title: Configurare un'applicazione SNMP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurare un'applicazione SNMP per l'utilizzo con il servizio E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804156"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurare un'applicazione SNMP in Skype for Business Server
 
Configurare un'applicazione SNMP per l'utilizzo con il servizio E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server include un'interfaccia di servizio Web standard che è possibile utilizzare per connettere il servizio informazioni percorso alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono a indirizzi MAC con informazioni sulla porta e sull'opzione. 
  
Se un'applicazione SNMP è installata e il servizio informazioni percorso non riesce a trovare una corrispondenza nel database delle posizioni, il servizio informazioni percorso esegue automaticamente una query nell'applicazione utilizzando l'indirizzo MAC fornito dal client. Il servizio informazioni percorso utilizza quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per eseguire di nuovo una query sul database delle posizioni.
  
> [!NOTE]
> Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Per configurare l'URL dell'applicazione SNMP

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

