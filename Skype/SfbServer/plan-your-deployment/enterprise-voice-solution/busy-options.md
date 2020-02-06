---
title: Pianificare le opzioni di occupato per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informazioni sulla caratteristica opzioni occupato in Skype for Business Server.
ms.openlocfilehash: cf9ee9dbb3785804b1bb63f4118a29d29cf7715c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803246"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Pianificare le opzioni di occupato per Skype for Business Server
 
Informazioni sulla caratteristica opzioni occupato in Skype for Business Server.
  
Opzioni di occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di 2016 di luglio che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica. 
  
Il criterio di opzioni occupato è supportato per il failover e il ripristino di emergenza nei pool Front-End associati e nel Survivable Branch Server (SBS).
  
Questo argomento descrive le caratteristiche delle opzioni di occupato. Per informazioni su come installare e configurare le opzioni di occupato, vedere [installare e configurare le opzioni di occupato per Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opzioni di configurazione

Se le opzioni di occupato sono abilitate per l'organizzazione, tutti gli utenti dell'organizzazione, sia VoIP aziendale che utenti non aziendali, possono usare le caratteristiche seguenti:
  
- Occupato in busy-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.
    
- Segreteria telefonica in occupato, in cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.
    
La caratteristica opzioni occupato offre funzionalità di failover. Se si verifica un problema e gli utenti non riescono a eseguire il failover in un altro server front-end o in un altro pool in Skype for Business Server, le impostazioni delle opzioni occupate verranno mantenute.
  
Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze. 
  
Dopo la configurazione, l'impostazione opzioni occupato è attiva per tutti i client e i dispositivi di chiamata Skype for business dell'utente. In base alle impostazioni delle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non suonerebbe su uno dei dispositivi di chiamata dell'utente, tra cui Macintosh, desktop di Windows, client mobili o telefoni IP, in cui l'utente ha eseguito l'accesso. 
  
Gli utenti vedranno le notifiche per le chiamate perse nei loro client e dispositivi Skype for business e verranno avvisati anche tramite posta elettronica. I chiamanti la cui chiamata è stata rifiutata a causa di impegni occupati vedranno una notifica nel client Skype for business che informa che l'utente che ha tentato di raggiungere è impegnato in un'altra chiamata.
  
È possibile configurare la caratteristica opzioni occupato usando i cmdlet di PowerShell per Skype for business per:
  
- Abilitare o disabilitare i criteri vocali delle opzioni di occupato per l'organizzazione.
    
- Gestire occupato o Voicemail occupato per tutti gli utenti dell'organizzazione.
    
- Amministrare occupato o Voicemail occupato per tutti gli utenti ospitati in un determinato pool Front-end.
    
- Amministrare occupato o Voicemail occupato per un elenco di utenti.
    
- Amministrare occupato o Voicemail occupato per un singolo utente.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilità con le applicazioni vocali

Le opzioni di occupato offrono l'interoperabilità con le applicazioni vocali seguenti in Skype for business:
  
- Gruppi di risposte (RGS)
    
  - Le opzioni di occupato impostate sui numeri di Response Group verranno ignorate dal sistema. saranno consentite più chiamate simultanee. 
    
  - L'esperienza di routing degli assistenti correnti nei gruppi di risposte rimarrà invariata per gli agenti con le impostazioni delle opzioni occupate.
    
  - Le chiamate provenienti da Response Groups agli utenti che sono agenti Response Groups non verranno limitate dalle impostazioni delle opzioni occupate e l'esperienza corrente di RGS verrà mantenuta.
    
  - Le chiamate correlate non-RGS agli agenti saranno onorate dalle impostazioni delle opzioni occupate.
    
- Chiamata in team
    
  - Le chiamate in arrivo per gli utenti configurati per una chiamata al team verranno impostate come priorità per ignorare le attività occupato e la segreteria telefonica nelle impostazioni di occupato.
    
  - L'esperienza di chiamata del team corrente rimarrà invariata con le opzioni di occupato impostate per gli utenti.
    
  - Le chiamate non correlate alla chiamata in team a tali utenti saranno onorate dalle impostazioni delle opzioni occupate.
    
- Delega di boss/admin 
    
  - Le chiamate in arrivo agli utenti configurati per una delega di capo/amministratore, come capo o amministratore, saranno in ordine di priorità per ignorare la disponibilità e la segreteria telefonica nelle impostazioni di occupato.
    
  - L'esperienza di delega corrente per il boss o l'amministratore rimarrà invariata con le opzioni di occupato impostate per gli amministratori o il boss.
    
  - Le chiamate correlate alla delega di non-boss/admin per gli amministratori saranno onorate dalle impostazioni delle opzioni occupate.
    
- Aspetto della linea condivisa 
    
  - Le impostazioni delle opzioni di occupato sugli account utente impostati per l'aspetto della linea condivisa verranno ignorate. 
    
  - L'aspetto della linea condivisa nativa occupato e la segreteria telefonica sulle opzioni di occupato saranno onorati.
    
- Servizio di parcheggio delle chiamate 
    
  - Le chiamate parcheggiate che non sono state recuperate e squillano di nuovo a causa di un timeout sarà consentito squillare anche se l'utente ha parcheggiato la chiamata tramite le opzioni di occupato. 
    
- Conferenza telefonica
    
  - Gli utenti delle chiamate in conferenza vengono considerati occupati e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni occupate.
    
  - Agli utenti delle conferenze non viene impedito di avviare nuove chiamate o conferenze per le opzioni di occupato.
    
  - Gli utenti delle conferenze possono comunque ricevere nuovi inviti alle conferenze, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni occupate.
    
- Squillo simultaneo e inoltro di chiamata
    
    La funzionalità occupato su occupato non è progettata per l'utilizzo con squillo simultaneo e inoltro di chiamata.
    

