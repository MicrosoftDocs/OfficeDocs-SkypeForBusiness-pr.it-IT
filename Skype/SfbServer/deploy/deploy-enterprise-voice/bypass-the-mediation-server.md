---
title: Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: ada5ce953086fe2182314bbe4904964683cb868c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764904"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server
 
Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale. 
  
 Se si utilizza la procedura descritta in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone una buona connettività tra gli endpoint Skype for Business e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.
  
Se non si dispone di una buona connettività tra gli endpoint di Skype for Business e tutti i peer al Mediation Server le cui rispettive connessioni trunk sono state abilitate per il bypass multimediale, è necessario configurare le impostazioni globali di bypass multimediale per utilizzare le informazioni sul sito e sull'area geografica quando si utilizza il bypass multimediale. Ciò consente di specificare in modo più preciso quando il contenuto multimediale deve ignorare il Mediation Server. A tale scopo, seguire la procedura descritta in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) e Associate a subnet with a network [site.](deploy-network.md#BKMK_AssociateSubnets)
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Per abilitare il bypass multimediale globalmente in modo che il Mediation Server venga ignorato sempre

1. Aprire Skype for Business Server Pannello di controllo.
    
2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **Globale** nell'elenco.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.
    
5. Fare clic su **Ignora sempre**.
    
6. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

[Pianificare il bypass multimediale in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)

