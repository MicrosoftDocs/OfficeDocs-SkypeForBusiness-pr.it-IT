---
title: Aggiungere il nome di dominio completo (FQDN) del pool Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Specificare il nome di dominio completo (FQDN) del pool Front-end che si sta creando. Non è possibile modificare il nome di dominio completo di un pool dopo la pubblicazione della topologia contenente il pool Front-end. Se è necessario rinominare un pool, è necessario eliminare il pool e quindi aggiungere un nuovo pool con il nuovo nome di dominio completo.
ms.openlocfilehash: e9e420956656d7bd0217f122844ea222f6bd2b40
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698231"
---
# <a name="add-front-end-pool-fqdn"></a>Aggiungere il nome di dominio completo (FQDN) del pool Front End
 
Specificare il nome di dominio completo (FQDN) del pool Front-end che si sta creando. Non è possibile modificare il nome di dominio completo di un pool dopo la pubblicazione della topologia contenente il pool Front-end. Se è necessario rinominare un pool, è necessario eliminare il pool e quindi aggiungere un nuovo pool con il nuovo nome di dominio completo.
  
> [!TIP]
> Se si prevede di implementare un pool Front-end in futuro, selezionare **più pool di computer**. Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di un singolo computer e un FQDN del pool per questo computer. Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool Front end tramite la distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool agli appropriati dispositivi di bilanciamento del carico per il pool, il bilanciamento del carico DNS (Domain Name System) o il servizio di bilanciamento del carico hardware. In molti casi, è necessario disporre entrambi i sistemi di bilanciamento del carico. Assicurarsi di aggiungere il nuovo server membro a entrambi. 
  

