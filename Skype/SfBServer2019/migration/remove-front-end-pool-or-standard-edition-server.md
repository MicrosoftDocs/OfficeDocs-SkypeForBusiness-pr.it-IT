---
title: Rimuovere pool Front End o server Standard Edition
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
description: Questo argomento illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition. Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813004"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

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
    

