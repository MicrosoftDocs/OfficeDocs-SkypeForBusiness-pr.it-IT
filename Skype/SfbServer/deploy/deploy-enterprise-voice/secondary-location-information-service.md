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
description: Configurare un database di origine percorso secondario (SLS) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830646"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurare un servizio informazioni percorso secondario in Skype for Business Server
 
Configurare un database di origine percorso secondario (SLS) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Skype for Business Server fornisce un'interfaccia del servizio Web che è possibile utilizzare per configurare il servizio informazioni percorso in un database di origine percorso secondario (SLS). L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni percorso. Se sono configurati sia il database delle posizioni che il database delle posizioni secondarie, il servizio informazioni percorso prima esegue una query nel database delle posizioni e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS. Se la posizione esiste nella SLS, il servizio informazioni percorso invierà il percorso al client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Per configurare un database delle posizioni secondarie

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per configurare l'URL per il percorso del database del percorso secondario. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

