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
ms.openlocfilehash: 962948c02e8890fce05db513e4839b4e179d23ebfad83e98003a88122e538d9a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281359"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un Front End Server da un pool

Il Front End Server non può esistere come computer autonomo. Deve essere definito come pool Front End, anche se nel pool è presente un solo computer.
  
In questo argomento viene illustrato il processo di rimozione di un singolo Front End Server da un pool Front End esistente. Se il Front End Server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [Remove Front End pool or edizione Standard server](remove-front-end-pool-or-standard-edition-server.md). Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front End. Quando si rimuove il pool, si rimuove ogni Front End Server.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server Front End Server da un pool

1. Nel Front End Server Skype for Business Server 2019 aprire Generatore di topologie.
    
2. Passare al nodo di installazione legacy.
    
3. Espandere **edizione Enterprise Pool Front End,** espandere il pool Front End con il Front End Server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul Front End Server che si desidera rimuovere e quindi scegliere **Elimina**.
    

