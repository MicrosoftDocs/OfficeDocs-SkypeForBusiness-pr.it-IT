---
title: Verificare la Federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194288"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la Federazione e l'accesso remoto per gli utenti esterni

Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e dell'accesso esterno

- Utenti di almeno un dominio federato, un utente interno in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.
    
- Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. 
    
- Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.
    
- Un utente ospitato nell'installazione legacy che usa l'accesso degli utenti remoti (registrazione i nPer Lync Server/Skype for business dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.
    
- Un utente ospitato in Skype for Business Server 2019 usando l'accesso degli utenti remoti (accedere a Skype for Business Server 2019 dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.
    

