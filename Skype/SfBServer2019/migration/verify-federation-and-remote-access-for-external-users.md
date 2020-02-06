---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.
ms.openlocfilehash: 7f27fa853c8af2ba5e97835ad1e0dd893c9128e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812684"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la federazione e l'accesso remoto per gli utenti esterni

Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e dell'accesso esterno

- Utenti di almeno un dominio federato, un utente interno in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.
    
- Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. 
    
- Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.
    
- Un utente ospitato nell'installazione legacy che usa l'accesso degli utenti remoti (registrazione i nPer Lync Server/Skype for business dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.
    
- Un utente ospitato in Skype for Business Server 2019 usando l'accesso degli utenti remoti (accedere a Skype for Business Server 2019 dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.
    

