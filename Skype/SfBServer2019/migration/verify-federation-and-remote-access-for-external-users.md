---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
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
description: Dopo la transizione della route di federazione al server perimetrale di Skype for Business Server 2019, è consigliabile eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751668"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la federazione e l'accesso remoto per gli utenti esterni

Dopo la transizione della route di federazione al server perimetrale di Skype for Business Server 2019, è consigliabile eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e l'accesso esterno

- Utenti provenienti da almeno un dominio federato, un utente interno su Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.
    
- Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. 
    
- Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.
    
- Un utente ospitato nell'installazione legacy utilizzando l'accesso degli utenti remoti (logging i nPer Lync Server/Skype for business dall'esterno della rete Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.
    
- Un utente ospitato in Skype for Business Server 2019 utilizzando l'accesso degli utenti remoti (accedere a Skype for Business Server 2019 dall'esterno della rete Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.
    

