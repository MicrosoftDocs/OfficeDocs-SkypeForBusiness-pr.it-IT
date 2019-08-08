---
title: Rimuovere un server front-end da un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Il server front-end non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244530"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un server front-end da un pool

Il server front-end non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.
  
Questo argomento illustra il processo di rimozione di un singolo server front-end da un pool Front-end esistente. Se il server front-end è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [rimuovere il pool Front-end o il server Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Non è necessario rimuovere i singoli server front-end prima di rimuovere il pool Front-end. Quando si rimuove il pool, si rimuove ogni server front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server front-end da un pool

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. Passare al nodo di installazione legacy.
    
3. Espandi i **pool Front End di Enterprise Edition**, Espandi il pool Front end con il front end server che vuoi rimuovere, fai clic con il pulsante destro del mouse sul server front-end che vuoi rimuovere e quindi fai clic su **Elimina**.
    

