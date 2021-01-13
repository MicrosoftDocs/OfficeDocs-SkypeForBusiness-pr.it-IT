---
title: Distribuire il controllo di ammissione di chiamata in Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836886"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Distribuire il controllo di ammissione di chiamata in Skype for Business Server
 
Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate. Per ulteriori informazioni, vedere [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Per distribuire il controllo di ammissione di chiamata

1.  Raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se non è già stato fatto, è necessario definire le aree e i siti di rete e associare le subnet ai siti di rete. Per informazioni dettagliate, vedere [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md).
    
3. Creare profili di criteri di larghezza di banda, come descritto in [creare profili di criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md)
    
4. Creare collegamenti area di rete, come descritto in [creare collegamenti area di rete in Skype for Business Server](create-network-region-links.md).
    
5. Creare route tra aree di rete, come descritto in [creare route interregionali di rete in Skype for Business Server](create-network-interregional-routes.md).
    
6. Creare criteri intersito di rete, come descritto in [creare criteri intersito di rete in Skype for Business Server](create-network-intersite-policies.md).
    
7. Abilitare il controllo di ammissione di chiamata, come descritto in [abilitare il controllo di ammissione di chiamata in Skype for Business Server](enable-call-admission-control.md).
    
8. Controllare alcune impostazioni finali, per assicurarsi che tutto sia configurato correttamente. Per informazioni dettagliate, vedere [Call ammissioni Control Deployment: Final Checklist for Skype for Business Server](final-checklist.md).
    

