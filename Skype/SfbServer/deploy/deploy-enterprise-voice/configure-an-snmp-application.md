---
title: Configurare un'applicazione SNMP in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurare un'applicazione SNMP per l'utilizzo con E9-1-1 in Skype for Business Server VoIP aziendale.
---

# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurare un'applicazione SNMP in Skype for Business Server
 
Configurare un'applicazione SNMP per l'utilizzo con E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server include un'interfaccia del servizio Web standard che è possibile utilizzare per connettere il servizio Informazioni percorso alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono agli indirizzi MAC con le informazioni sulla porta e sullo switch. 
  
Se è installata un'applicazione SNMP e il servizio informazioni percorso non riesce a trovare una corrispondenza nel database delle località, il servizio Informazioni percorso esegue automaticamente una query sull'applicazione utilizzando l'indirizzo MAC fornito dal client. Il servizio Informazioni percorso utilizza quindi le informazioni sulla porta e sullo switch restituite dall'applicazione SNMP per eseguire nuovamente una query sul database delle località.
  
> [!NOTE]
> Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Per configurare l'URL dell'applicazione SNMP

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)