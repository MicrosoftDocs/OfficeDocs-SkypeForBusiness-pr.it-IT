---
title: Configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurare un database di origine della posizione secondaria (SLS) per E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240400"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server
 
Configurare un database di origine della posizione secondaria (SLS) per E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server offre un'interfaccia di servizio Web che può essere usata per puntare il servizio informazioni sulla posizione in un database di origine della posizione secondaria (SLS). L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni sulla posizione. Se sono configurati sia il database della posizione che il database della posizione secondaria, il servizio informazioni sulla posizione esegue prima di tutto il database della posizione e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS. Se la posizione esiste nella SLS, il servizio informazioni sulla posizione restituirà la posizione al client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Per configurare un database di posizione secondario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per configurare l'URL per la posizione del database della posizione secondaria. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

