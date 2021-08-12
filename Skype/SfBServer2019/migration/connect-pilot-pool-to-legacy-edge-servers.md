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
description: Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'utilizzo di questa route.
ms.openlocfilehash: 8e76dfc9ee99e2c4e82f40d3aba4aa8a43972c98e0569416ce293b2cfc012d96
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296013"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'utilizzo di questa route. 
  
Per abilitare il sito Skype for Business Server 2019 per l'utilizzo del server Director e del server perimetrale della distribuzione legacy, utilizzare Generatore di topologie per associare il pool di server perimetrali legacy.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di server perimetrali legacy tramite Generatore di topologie

1. Apre lo strumento di generazione topologia 
    
2. Selezionare il sito, che si trova direttamente sotto **il Skype for Business Server** nodo. 
    
3. Scegliere **Modifica proprietà** dal menu **Azioni**.
    
4. Nel riquadro sinistro selezionare **Route di federazione**.
    
5. In **Assegnazione route federazione sito** selezionare Abilita **federazione SIP** e quindi selezionare il server Director legacy o il server perimetrale legacy se non è elencato alcun server Director.
  
6. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
7. In Generatore di topologie, nel nodo Skype for Business Server 2019 passare al **server edizione Standard** o ai pool edizione Enterprise **Front End,** fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica** proprietà .
    
8. In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**. 
    
9. Selezionare il server perimetrale legacy nell'elenco. 
  
10. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
11. In **Generatore di topologie** selezionare il nodo di primo livello, **Skype for Business Server**.
    
12. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
13. Al termine della Pubblicazione guidata fare clic su  **Fine**.
    

