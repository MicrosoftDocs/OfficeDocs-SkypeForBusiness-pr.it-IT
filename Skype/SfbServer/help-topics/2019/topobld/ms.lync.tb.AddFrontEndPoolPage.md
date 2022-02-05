---
title: Aggiungere l'FQDN del pool Front End
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Specificare il nome di dominio completo (FQDN) del pool Front End che si sta creando. Non è possibile modificare l''FQDN di un pool Front End dopo avere pubblicato la topologia contenente il pool. Se si desidera rinominare un pool, è necessario eliminare il pool e quindi aggiungerne uno nuovo con il nuovo FQDN.'
---

# <a name="add-front-end-pool-fqdn"></a>Aggiungere il nome di dominio completo (FQDN) del pool Front End
 
Specificare il nome di dominio completo (FQDN) del pool Front End che si sta creando. Non è possibile modificare l'FQDN di un pool Front End dopo avere pubblicato la topologia contenente il pool. Se si desidera rinominare un pool, è necessario eliminare il pool e quindi aggiungerne uno nuovo con il nuovo FQDN.
  
> [!TIP]
> Se si prevede di implementare in futuro un pool Front End, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con il carico bilanciato, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione. Quando si è pronti ad aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo Generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool Front End tramite la Distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool ai servizi o ai dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware. In molti casi possono essere in uso tutti e due i sistemi di bilanciamento del carico. Ricordarsi di aggiungere il nuovo server membro a entrambi. 
  

