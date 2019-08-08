---
title: Configurare i server delle applicazioni attendibili
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In un ambiente misto, se crei un nuovo server applicazioni attendibile, devi impostare il pool hop successivo come un pool di Skype for Business Server 2019. In un ambiente misto viene visualizzato sia il pool legacy che il pool di Skype for Business Server 2019 nell'elenco a discesa. La selezione del pool legacy non è supportata.
ms.openlocfilehash: b715cd7f3f067c5e54dbc085350fcc7f96b5c4be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239543"
---
# <a name="configure-trusted-application-servers"></a>Configurare i server delle applicazioni attendibili

In un ambiente misto, se crei un nuovo server applicazioni attendibile, devi impostare il pool hop successivo come un pool di Skype for Business Server 2019. In un ambiente misto viene visualizzato sia il pool legacy che il pool di Skype for Business Server 2019 nell'elenco a discesa. La selezione del pool legacy non è supportata.
  
> [!IMPORTANT]
> Se si esegue la migrazione di un server applicazioni attendibile, è anche necessario aggiornare la versione di UCMA in uso. Se crei un nuovo pool di applicazioni attendibili per Skype for Business Server 2019, dovresti aggiornare UCMA alla versione inclusa in Skype for Business Server 2019 o l'ultima versione disponibile. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selezionare Skype for Business Server 2019 come hop successivo quando si crea un server applicazioni attendibile

1. Aprire Generatore di topologie.
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.
    
3. Immettere il **nome di dominio completo del pool** di applicazioni attendibili e selezionare se sarà a server singolo o a più server. 
    
4. Fare clic su **Avanti**.
    
5. Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Skype for Business Server 2019. 
    
6. Fare clic su **fine**.
    
7. Selezionare il nodo superiore di **Skype for Business Server**e scegliere **pubblica**dal menu **azione** .
    
    Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente ed associato al pool Front-end corretto. 
    

