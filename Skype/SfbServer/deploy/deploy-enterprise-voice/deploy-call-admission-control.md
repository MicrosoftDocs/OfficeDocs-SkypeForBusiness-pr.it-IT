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
ms.openlocfilehash: eaba53e7c4c908024b3427970c103a3bcc8885036ca3e1dbc657e6c0d78e5d8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307817"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Distribuire il controllo di ammissione di chiamata in Skype for Business Server
 
Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate. Per ulteriori informazioni, vedere [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Per distribuire Controllo di ammissione di chiamata

1.  Raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in [Esempio: Raccolta](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server .
    
2. Se non è già stato fatto, è necessario definire aree e siti di rete e associare subnet ai siti di rete. Per informazioni dettagliate, vedere [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).
    
3. Creare profili di criteri di larghezza di banda, come descritto in [Creare profili di criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md)
    
4. Creare collegamenti di area di rete, come descritto in [Creare collegamenti di area di rete in Skype for Business Server](create-network-region-links.md).
    
5. Creare route tra aree di rete, come descritto in Creare route [interregionali](create-network-interregional-routes.md)di rete in Skype for Business Server .
    
6. Creare criteri tra siti di rete, come descritto in Creare criteri [tra siti di](create-network-intersite-policies.md)rete in Skype for Business Server .
    
7. Abilitare il controllo di ammissione di chiamata, come descritto in [Abilitare il controllo di](enable-call-admission-control.md)ammissione di chiamata in Skype for Business Server .
    
8. Controlla alcune impostazioni finali per assicurarti che tutto sia configurato correttamente. Per informazioni dettagliate, vedere [Distribuzione del controllo di ammissione di chiamata: elenco di controllo finale per Skype for Business Server](final-checklist.md).
    

