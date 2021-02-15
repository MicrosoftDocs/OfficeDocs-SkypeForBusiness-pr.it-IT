---
title: Configurare un servizio informazioni percorso secondario in Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurare un database SLS (Secondary Location Source) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830646"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurare un servizio informazioni percorso secondario in Skype for Business Server
 
Configurare un database SLS (Secondary Location Source) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server offre un'interfaccia del servizio Web che è possibile utilizzare per puntare il servizio informazioni percorso a un database SLS (Secondary Location Source). L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al file WSDL del servizio informazioni percorso. Se sono configurati sia un database delle località che un database delle località secondario, il servizio informazioni percorso esegue innanzitutto una query sul database delle località e, se non viene trovata alcuna corrispondenza, invia la richiesta di posizione dal client al database SLS. Se il percorso esiste nel servizio SLS, il servizio informazioni percorso invia la posizione al client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Per configurare un database delle località secondario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet seguente per configurare l'URL per il percorso del database delle località secondario. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

