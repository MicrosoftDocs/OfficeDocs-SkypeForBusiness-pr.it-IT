---
title: Configurare il bypass multimediale in Skype for Business Server per aggirare sempre il Mediation Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Abilitare il bypass multimediale per aggirare sempre il Mediation Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768269"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurare il bypass multimediale in Skype for Business Server per aggirare sempre il Mediation Server
 
Abilitare il bypass multimediale per aggirare sempre il Mediation Server in Skype for Business Server VoIP aziendale. 
  
 Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che si disponga di una buona connettività tra endpoint Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale nella connessione trunk.
  
Se non si dispone di una buona connettività tra endpoint Skype for business e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per l'uso delle informazioni sul sito e sulle aree geografiche Quando si usa il bypass multimediale. In questo modo è possibile determinare un maggiore controllo quando l'elemento multimediale ignora il Mediation Server. Per eseguire questa operazione, usare la procedura descritta in [configurare le impostazioni globali di bypass multimediale in Skype for Business Server per usare le informazioni sul sito e le aree](use-site-and-region-information.md) geografiche e [associare invece una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Per abilitare il bypass multimediale a livello globale per ignorare sempre il Mediation Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **globale** nell'elenco.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .
    
5. Fare clic su **Ignora sempre**.
    
6. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

[Pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)

