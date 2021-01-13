---
title: Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804216"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server
 
Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale. 
  
 Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che si disponga di una buona connettività tra gli endpoint di Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.
  
Se non si dispone di una buona connettività tra gli endpoint di Skype for business e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per l'utilizzo delle informazioni sul sito e sulla regione quando si utilizza il bypass multimediale. Ciò consente di specificare in modo più preciso quando il contenuto multimediale deve ignorare il Mediation Server. A tale scopo, eseguire la procedura descritta in [Configure Media Bypass Global Settings in Skype for Business Server per utilizzare le informazioni sui siti e le aree](use-site-and-region-information.md) geografiche e [associare invece una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Per abilitare il bypass multimediale globalmente in modo che il Mediation Server venga ignorato sempre

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare doppio clic sulla configurazione **Globale** nell'elenco.
    
4. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.
    
5. Fare clic su **Ignora sempre**.
    
6. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

[Pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)

