---
title: Distribuire il controllo di ammissione alle chiamate in Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Il controllo di ammissione di chiamata (CAC) è una soluzione che determina se una sessione in tempo reale può essere stabilita in base alla larghezza di banda disponibile per evitare una scarsa qualità audio/video per gli utenti nelle reti congestionate.
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767669"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Distribuire il controllo di ammissione alle chiamate in Skype for Business Server
 
Il controllo di ammissione di chiamata (CAC) è una soluzione che determina se una sessione in tempo reale può essere stabilita in base alla larghezza di banda disponibile per evitare una scarsa qualità audio/video per gli utenti nelle reti congestionate. Per altre informazioni, Vedi [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Per distribuire il controllo di ammissione alle chiamate

1.  Raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se non è già stato fatto, è necessario definire le aree geografiche e i siti di rete e associare subnet ai siti di rete. Per informazioni dettagliate, vedere [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md).
    
3. Creare profili di criteri di larghezza di banda, come dettagliato in [creare profili di criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md)
    
4. Creare collegamenti a un'area geografica di rete, come descritto in [creare collegamenti all'area di rete in Skype for Business Server](create-network-region-links.md).
    
5. Creare rotte interregionali di rete, come descritto in dettaglio in [creare route interregionali di rete in Skype for Business Server](create-network-interregional-routes.md).
    
6. Creare criteri di intersito di rete, come descritto in dettaglio per [creare criteri intersito di rete in Skype for Business Server](create-network-intersite-policies.md).
    
7. Abilitare il controllo di ammissione alle chiamate, come descritto in [Abilita controllo ammissione chiamata in Skype for Business Server](enable-call-admission-control.md).
    
8. Verificare alcune impostazioni finali per verificare che tutto sia configurato correttamente. Per informazioni dettagliate, vedere [distribuzione dei controlli di ammissione alle chiamate: elenco di controllo finale per Skype for Business Server](final-checklist.md).
    

