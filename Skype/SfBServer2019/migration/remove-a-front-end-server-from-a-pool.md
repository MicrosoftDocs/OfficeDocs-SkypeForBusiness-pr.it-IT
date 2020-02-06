---
title: Rimuovere un Front End Server da un pool
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
description: Il server front-end non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813034"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un Front End Server da un pool

Il server front-end non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.
  
Questo argomento illustra il processo di rimozione di un singolo server front-end da un pool Front-end esistente. Se il server front-end è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [rimuovere il pool Front-end o il server Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Non è necessario rimuovere i singoli server front-end prima di rimuovere il pool Front-end. Quando si rimuove il pool, si rimuove ogni server front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server front-end da un pool

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. Passare al nodo di installazione legacy.
    
3. Espandi i **pool Front End di Enterprise Edition**, Espandi il pool Front end con il front end server che vuoi rimuovere, fai clic con il pulsante destro del mouse sul server front-end che vuoi rimuovere e quindi fai clic su **Elimina**.
    

