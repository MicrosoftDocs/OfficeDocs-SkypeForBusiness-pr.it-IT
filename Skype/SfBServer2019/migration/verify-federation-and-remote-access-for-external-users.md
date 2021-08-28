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
ms.localizationpriority: medium
description: Dopo aver eseguito la transizione della route di federazione al server perimetrale Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la federazione funzioni come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
ms.openlocfilehash: ef6e41242462f218ab96db94dd8a2b5df1b388bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592960"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la federazione e l'accesso remoto per gli utenti esterni

Dopo aver eseguito la transizione della route di federazione al server perimetrale Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la federazione funzioni come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Verificare la connettività degli utenti esterni e l'accesso esterno

- Gli utenti di almeno un dominio federato, un utente interno Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.
    
- Utenti di ogni provider di servizi di messaggistica istantanea pubblica supportati dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente Skype for Business Server 2019 e un utente nell'installazione legacy. 
    
- Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.
    
- Un utente ospitato nell'installazione legacy utilizzando l'accesso utente remoto (registrazione i nto Lync Server/Skype for Business dall'esterno della rete Intranet ma senza VPN) con un utente Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.
    
- Un utente ospitato in Skype for Business Server 2019 che utilizza l'accesso utente remoto (accesso a Skype for Business Server 2019 dall'esterno della rete Intranet ma senza VPN) con un utente Skype for Business Server 2019 e un utente nell'installazione legacy. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.
    

