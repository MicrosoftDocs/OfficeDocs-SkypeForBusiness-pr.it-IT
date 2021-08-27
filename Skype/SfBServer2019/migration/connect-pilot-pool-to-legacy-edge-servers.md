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
ms.localizationpriority: medium
description: Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'utilizzo di questa route.
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607463"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'utilizzo di questa route. 
  
Per abilitare il sito Skype for Business Server 2019 per l'utilizzo del server Director e del server perimetrale della distribuzione legacy, utilizzare Generatore di topologie per associare il pool di server perimetrali legacy.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di server perimetrali legacy tramite Generatore di topologie

1. Apre lo strumento di generazione topologia 
    
2. Selezionare il sito, che si trova direttamente sotto **il nodo Skype for Business Server** sito. 
    
3. Scegliere **Modifica proprietà** dal menu **Azioni**.
    
4. Nel riquadro sinistro selezionare **Route di federazione**.
    
5. In **Assegnazione route federazione sito** selezionare Abilita federazione **SIP** e quindi selezionare il server Director legacy o il server perimetrale legacy se non è elencato alcun server Director.
  
6. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
7. In Generatore di topologie, nel nodo Skype for Business Server 2019 passare al **server edizione Standard** o ai pool **front-end edizione Enterprise**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere Modifica **proprietà**.
    
8. In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**. 
    
9. Selezionare il server perimetrale legacy nell'elenco. 
  
10. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
11. In **Generatore di topologie** selezionare il nodo più in alto, **Skype for Business Server**.
    
12. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
13. Al termine della Pubblicazione guidata fare clic su  **Fine**.
    

