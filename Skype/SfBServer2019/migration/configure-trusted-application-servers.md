---
title: Configurare i server applicazioni attendibili
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
description: In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool Skype for Business Server 2019. In un ambiente misto, sia il pool legacy che il pool Skype for Business Server 2019 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy non è supportata.
ms.openlocfilehash: 9965af757a570cfd787bb482a932d2817fd07ab0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584470"
---
# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool Skype for Business Server 2019. In un ambiente misto, sia il pool legacy che il pool Skype for Business Server 2019 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy non è supportata.
  
> [!IMPORTANT]
> Se si esegue la migrazione di un server applicazioni attendibile, è consigliabile aggiornare anche la versione di UCMA in uso. Se si crea un nuovo pool di applicazioni attendibili per Skype for Business Server 2019, è necessario aggiornare UCMA alla versione inclusa in Skype for Business Server 2019 o alla versione più recente disponibile. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selezionare Skype for Business Server 2019 come hop successivo quando si crea un server applicazioni attendibili

1. Apre lo strumento di generazione topologia
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e scegliere Nuovo pool di applicazioni **attendibili**.
    
3. Immettere il **nome di dominio** completo del pool di applicazioni attendibili e specificare se sarà a server singolo o a più server. 
    
4. Fare clic su **Avanti**.
    
5. **Nell'elenco della pagina Selezionare l'hop** successivo selezionare Skype for Business Server pool Front End 2019. 
    
6. Fare clic su **Fine**.
    
7. Selezionare il nodo principale **Skype for Business Server** e scegliere Pubblica dal **menu** **Azione.**
    
    Verificare che **il pool di applicazioni attendibili** sia stato creato correttamente e che sia associato al pool Front End corretto. 
    

