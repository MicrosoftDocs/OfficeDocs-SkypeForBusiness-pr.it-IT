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
description: In questo argomento vengono illustrate le procedure per la rimozione di un pool Front end o di un front end server Standard Edition. Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752278"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

In questo articolo vengono illustrate le procedure per la rimozione di un pool Front end o di un server Standard Edition front end. Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di Font End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo Legacy.
    
3. Espandere Pool **Enterprise Edition front end**, espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front end che si desidera rimuovere e quindi scegliere **Elimina**.
    
4. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata legacy in base alle esigenze. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server Standard Edition Front End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo installazioni legacy.
    
3. Espandere **Standard Edition Front End Server**, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.
    
4. Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al front end server Standard Edition e quindi scegliere **Elimina**.
    
    > [!IMPORTANT]
    > È necessario rimuovere la definizione dei database di SQL Server collocati dal front end server Standard Edition. 
  
5. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata in base alle esigenze. 
    

