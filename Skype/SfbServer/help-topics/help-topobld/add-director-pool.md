---
title: Aggiungere un pool di Director
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Per eseguire l'operazione Definisci FQDN pool Director, selezionare un Pool di più computer costituito da due o più server Director in un pool con bilanciamento del carico oppure un Pool di computer singolo. È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per connettersi al pool di server Director o al nome di dominio completo del singolo Director. Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.
ms.openlocfilehash: 6b4b3060c499c5d2b1f7aeb2a80e9ff02fae1798
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852200"
---
# <a name="add-director-pool"></a>Aggiungere pool di Director
 
Per eseguire l'operazione **Definisci FQDN pool Director**, selezionare un **Pool di più computer** costituito da due o più server Director in un pool con bilanciamento del carico oppure un **Pool di computer singolo**. È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per connettersi al pool di server Director o al nome di dominio completo del singolo Director. Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.
  
> [!TIP]
> Se si prevede di implementare in futuro un pool di server Director, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione. Quando si è pronti ad aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo Generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di server Director tramite la distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool ai servizi o dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS (Domain Name System) o i dispositivi di bilanciamento del carico hardware. In molti casi possono essere in uso tutti e due i sistemi di bilanciamento del carico. Ricordarsi di aggiungere il nuovo server membro a entrambi. 
  

