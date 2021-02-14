---
title: Rimuovere pool Front End o server Standard Edition
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
description: In questo argomento viene illustrato il processo di rimozione di un pool Front End o di un Front End Server Standard Edition. Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool. Quando si rimuove un Front End Server Standard Edition, è necessario rimuovere la definizione dell SQL store dal Generatore di topologie.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752278"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

In questo articolo viene illustrata la procedura di rimozione di un pool Front End o di un Front End Server Standard Edition. Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool. Quando si rimuove un Front End Server Standard Edition, è necessario rimuovere la definizione dell SQL store dal Generatore di topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di Font End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo legacy.
    
3. Espandere **Pool Enterprise Edition Front End,** espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front End che si desidera rimuovere e quindi scegliere **Elimina.**
    
4. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata legacy in base alle esigenze. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server Standard Edition Front End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo delle installazioni legacy.
    
3. Espandere **Standard Edition Front End Server,** fare clic con il pulsante destro del mouse sul Front End Server che si desidera rimuovere e quindi scegliere **Elimina.**
    
4. Espandere **SQL archivi,** fare clic con il pulsante destro del mouse sul database SQL Server associato al Front End Server Standard Edition e quindi scegliere **Elimina.**
    
    > [!IMPORTANT]
    > È necessario rimuovere la definizione dei database SQL Server collocati dal Front End Server Standard Edition. 
  
5. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata in base alle esigenze. 
    

