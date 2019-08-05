---
title: Rimuovere il pool Front-end o il server Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Questo argomento illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition. Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195228"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere il pool Front-end o il server Standard Edition

Questo articolo illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition. Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.
  
## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di server front-end

1. Aprire Generatore di topologie.
    
2. Passare al nodo Legacy.
    
3. Espandere pool di **front-end Enterprise Edition**, espandere il pool Front-End, fare clic con il pulsante destro del mouse sul pool Front-end che si desidera rimuovere e quindi scegliere **Elimina**.
    
4. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata legacy in base alle esigenze. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server front-end Standard Edition

1. Aprire Generatore di topologie.
    
2. Passare al nodo installazioni legacy.
    
3. Espandere i **server front-end Standard Edition**, fare clic con il pulsante destro del mouse sul server front-end che si desidera rimuovere e quindi scegliere **Elimina**.
    
4. Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al server front-end Standard Edition e quindi scegliere **Elimina**.
    
    > [!IMPORTANT]
    > È necessario rimuovere la definizione dei database di SQL Server collocati dal server front-end Standard Edition. 
  
5. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata in base alle esigenze. 
    

