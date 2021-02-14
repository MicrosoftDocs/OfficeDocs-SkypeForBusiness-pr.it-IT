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
description: Il Front End Server non può esistere come computer autonomo. Deve essere definito come pool Front End, anche se nel pool è presente un solo computer.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752318"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un Front End Server da un pool

Il Front End Server non può esistere come computer autonomo. Deve essere definito come pool Front End, anche se nel pool è presente un solo computer.
  
In questo argomento viene illustrato il processo di rimozione di un singolo Front End Server da un pool Front End esistente. Se il Front End Server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere Rimuovere il pool Front End o [il server Standard Edition.](remove-front-end-pool-or-standard-edition-server.md) Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front End. Quando si rimuove il pool, si rimuove ogni Front End Server.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server Front End Server da un pool

1. Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo di installazione legacy.
    
3. Espandere **Pool Enterprise Edition Front End,** espandere il pool Front End con il Front End Server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul Front End Server che si desidera rimuovere e quindi scegliere **Elimina.**
    

