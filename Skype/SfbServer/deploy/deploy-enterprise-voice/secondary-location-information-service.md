---
title: Configurare un servizio informazioni percorso secondario in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurare un database SLS (Secondary Location Source) per E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 7c41debb07ab8d1aece05b24f515f159f5be0dae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860803"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurare un servizio informazioni percorso secondario in Skype for Business Server
 
Configurare un database SLS (Secondary Location Source) per E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server fornisce un'interfaccia del servizio Web che è possibile utilizzare per puntare il servizio informazioni percorso a un database SLS (Secondary Location Source). L'interfaccia del servizio Web che si connette al database SLS deve essere conforme a WSDL del servizio informazioni percorso. Se sono configurati sia un database delle località che un database delle località secondario, il servizio informazioni percorso esegue innanzitutto una query sul database delle località e, se non viene trovata alcuna corrispondenza, invia la richiesta di posizione dal client al database SLS. Se il percorso esiste nel servizio SLS, il servizio informazioni sulla posizione invia la posizione al client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Per configurare un database delle località secondario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet seguente per configurare l'URL per il percorso del database delle località secondario. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)