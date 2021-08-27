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
ms.localizationpriority: medium
description: In questo argomento viene illustrato il processo di rimozione di un pool Front End o di edizione Standard Front End Server. Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool. Quando si rimuove un edizione Standard Front End Server, è necessario rimuovere la definizione SQL Store da Generatore di topologie.
ms.openlocfilehash: 04ff2120fcbbe0c914a0a105669083eeb13a8347
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589250"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

In questo articolo viene illustrata la procedura di rimozione di un pool Front End o di edizione Standard Front End Server. Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool. Quando si rimuove un edizione Standard Front End Server, è necessario rimuovere la definizione SQL Store da Generatore di topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di Font End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo legacy.
    
3. Espandere **edizione Enterprise pool Front End,** espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front End che si desidera rimuovere e quindi scegliere **Elimina.**
    
4. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata legacy in base alle esigenze. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server Standard Edition Front End Server

1. Apre lo strumento di generazione topologia
    
2. Passare al nodo installazioni legacy.
    
3. Espandere **edizione Standard Front End Server,** fare clic con il pulsante destro del mouse sul Front End Server che si desidera rimuovere e quindi scegliere **Elimina**.
    
4. Espandere **SQL archivi,** fare clic con il pulsante destro del mouse sul database SQL Server associato al Front End Server edizione Standard e quindi scegliere **Elimina**.
    
    > [!IMPORTANT]
    > È necessario rimuovere la definizione dei database SQL Server collocati edizione Standard Front End Server. 
  
5. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata in base alle esigenze. 
    

