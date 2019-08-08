---
title: Connettere il pool pilota agli Edge Server legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito. Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239554"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota agli Edge Server legacy

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
    
11. In **Generatore**di topologie selezionare il nodo principale, **Skype for Business Server**.
    
12. Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.
    
13. Al termine della **pubblicazione guidata** , fare clic su **fine**.
    

