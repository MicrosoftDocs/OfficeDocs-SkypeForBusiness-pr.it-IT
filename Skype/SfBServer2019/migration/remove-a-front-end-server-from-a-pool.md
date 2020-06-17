---
title: Rimuovere un Front End Server da un pool
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
description: Il front end server non può esistere come computer autonomo. Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752318"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un Front End Server da un pool

Il front end server non può esistere come computer autonomo. Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.
  
In questo argomento vengono illustrate le procedure per la rimozione di un singolo front end server da un pool Front end esistente. Se il front end server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [Remove front end pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md). Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front end. Quando si rimuove il pool, è necessario rimuovere ogni Front End Server.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server Front End Server da un pool

1. Nel server front end di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo di installazione legacy.
    
3. Espandere **pool Enterprise Edition front end**, espandere il pool Front end con il front end server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.
    

