---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito. Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813704"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito. Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route. 
  
Per consentire al sito di Skype for Business Server 2019 di usare il Director e il server perimetrale della distribuzione legacy, usare generatore di topologie per associare il pool di Edge legacy.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di Edge legacy tramite Generatore di topologia

1. Aprire Generatore di topologie. 
    
2. Selezionare il sito, che si trova direttamente sotto il nodo **di Skype for Business Server** . 
    
3. Nel menu **azioni** fare clic su **modifica proprietà**.
    
4. Nel riquadro sinistro selezionare **Route federativo**.
    
5. In **assegnazione della route federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il Director legacy o il server perimetrale legacy se non è elencato alcun amministratore.
  
6. Fare clic su **OK** per chiudere la pagina **modifica proprietà** . 
    
7. In Generatore di topologia, nel nodo di Skype for Business Server 2019, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.
    
8. In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**. 
    
9. Nell'elenco selezionare il server perimetrale legacy. 
  
10. Fare clic su **OK** per chiudere la pagina **modifica proprietà** . 
    
11. In **Generatore di topologie**selezionare il nodo principale, **Skype for Business Server**.
    
12. Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.
    
13. Al termine della **pubblicazione guidata** , fare clic su **fine**.
    

