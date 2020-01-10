---
title: Configurare un'applicazione SNMP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurare un'applicazione SNMP per l'uso con E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 5941a7fee85b486577df4c79848274528ddab952
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001376"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurare un'applicazione SNMP in Skype for Business Server
 
Configurare un'applicazione SNMP per l'uso con E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server include un'interfaccia di servizio Web standard che puoi usare per connettere il servizio informazioni sulla posizione alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono agli indirizzi MAC con le informazioni sulla porta e sullo switch. 
  
Se è installata un'applicazione SNMP e il servizio informazioni sulla posizione non riesce a trovare una corrispondenza nel database della posizione, il servizio informazioni sulla posizione esegue automaticamente una query nell'applicazione usando l'indirizzo MAC fornito dal client. Il servizio informazioni sulla posizione usa quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per interrogare di nuovo il database della posizione.
  
> [!NOTE]
> Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Per configurare l'URL dell'applicazione SNMP

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

