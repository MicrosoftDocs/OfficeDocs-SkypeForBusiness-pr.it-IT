---
title: Aggiungere un pool di Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Per eseguire l'operazione Definisci FQDN pool Director, selezionare un Pool di più computer costituito da due o più server Director in un pool con bilanciamento del carico oppure un Pool di computer singolo. È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per la connessione al pool di server Director o all'FQDN del singolo Director. Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807756"
---
# <a name="add-director-pool"></a>Aggiungere pool di Director
 
Per eseguire l'operazione **Definisci FQDN pool Director**, selezionare un **Pool di più computer** costituito da due o più server Director in un pool con bilanciamento del carico oppure un **Pool di computer singolo**. È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per la connessione al pool di server Director o all'FQDN del singolo Director. Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.
  
> [!TIP]
> Se si prevede di implementare in futuro un pool di server Director, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione. Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di Director tramite la distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool ai servizi o dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS (Domain Name System) o i dispositivi di bilanciamento del carico hardware. In molti casi possono essere in uso tutti e due i sistemi di bilanciamento del carico. Ricordarsi di aggiungere il nuovo server membro a entrambi. 
  

