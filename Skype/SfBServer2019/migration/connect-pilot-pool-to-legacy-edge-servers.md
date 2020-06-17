---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, è necessario configurare Skype for Business Server 2019 per l'utilizzo di questa route.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753926"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, è necessario configurare Skype for Business Server 2019 per l'utilizzo di questa route. 
  
Per abilitare il sito di Skype for Business Server 2019 per l'utilizzo del server Director e Edge della distribuzione legacy, utilizzare Generatore di topologie per associare il pool perimetrale legacy.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di server perimetrali legacy tramite Generatore di topologie

1. Apre lo strumento di generazione topologia 
    
2. Seleziona il tuo sito, che è direttamente sotto il nodo **di Skype for Business Server** . 
    
3. Scegliere **Modifica proprietà** dal menu **Azioni**.
    
4. Nel riquadro sinistro selezionare **Route di federazione**.
    
5. In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il server Director legacy o legacy Edge se non è elencato alcun Director.
  
6. Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **. 
    
7. In Generatore di topologie, nel nodo Skype for Business Server 2019, passare a **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.
    
8. In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**. 
    
9. Selezionare il server perimetrale legacy nell'elenco. 
  
10. Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **. 
    
11. In **Generatore di topologie**selezionare il nodo di primo livello, **Skype for Business Server**.
    
12. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
13. Al termine della Pubblicazione guidata **** fare clic su  **Fine **.
    

