---
title: Pianificare le opzioni di disponibilità per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.
ms.openlocfilehash: b233260327688830a338989c14ef0eb24ade781e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854230"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Pianificare le opzioni di disponibilità per Skype for Business Server
 
Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.
  
Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica. 
  
Il criterio Opzioni occupato è supportato per il failover e il ripristino di emergenza nei pool Front End abbinati e nei Survivable Branch Server (SBS).
  
In questo argomento vengono descritte le funzionalità di Opzioni occupato. Per informazioni su come installare e configurare le opzioni occupato, vedere [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opzioni di configurazione

Se per l'organizzazione sono abilitate le opzioni occupato, tutti gli utenti dell'organizzazione, sia VoIP aziendale che non VoIP aziendale, possono utilizzare le funzionalità seguenti:
  
- Occupato su occupato - In cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.
    
- Segreteria telefonica su Occupato - In cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.
    
La funzionalità Opzioni occupato offre funzionalità di failover. Se si verifica un problema e gli utenti esereranno il failover a un altro Front End Server o a un altro pool in Skype for Business Server, le impostazioni relative alle opzioni occupato verranno mantenute.
  
Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o a quelli con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze. 
  
Dopo la configurazione, l'impostazione Opzioni occupato è attiva per tutti i dispositivi e i client Skype for Business chiamata dell'utente. In base alle impostazioni di Opzioni occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non squillerebbe su nessuno dei dispositivi di chiamata dell'utente, inclusi Macintosh, Windows Desktop, client mobili o telefoni IP, a cui l'utente ha eseguito l'accesso. 
  
Gli utenti visualizzano le notifiche di chiamata senza risposta nei Skype for Business e nei dispositivi e riceveranno una notifica anche tramite posta elettronica. I chiamanti la cui chiamata è stata rifiutata a causa di Occupato su occupato visualizzano una notifica nel client Skype for Business che indica che l'utente che ha tentato di raggiungere è occupato in un'altra chiamata.
  
È possibile configurare la funzionalità Opzioni occupato utilizzando i cmdlet di PowerShell Skype for Business per:
  
- Abilitare o disabilitare il criterio vocale Opzioni occupato per il Enterprise.
    
- Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti del Enterprise.
    
- Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti ospitati in un particolare pool Front End.
    
- Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per un elenco di utenti.
    
- Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per un singolo utente.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilità con le applicazioni vocali

Opzioni occupato garantisce l'interoperabilità con le applicazioni vocali seguenti in Skype for Business:
  
- Response Group (RGS)
    
  - Le opzioni di occupato impostate sui numeri di Response Group verranno ignorate dal sistema. saranno consentite più chiamate simultanee. 
    
  - L'esperienza di routing dell'operatore corrente in Response Group rimarrà invariata per gli agenti con le impostazioni opzioni occupato.
    
  - Le chiamate provenienti da Response Group agli utenti che sono agenti di Response Group non verranno limitate dalle impostazioni delle opzioni occupato e l'esperienza RGS corrente verrà mantenuta.
    
  - Le chiamate non correlate a RGS agli agenti verranno rispettate dalle impostazioni delle opzioni di disponibilità.
    
- Intercettazione team
    
  - Per le chiamate in arrivo agli utenti che sono impostati per una chiamata al team verrà assegnata la priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.
    
  - L'esperienza di chiamata al team corrente rimarrà invariata con opzioni occupato impostate per gli utenti.
    
  - Le chiamate non correlate alle chiamate del team a tali utenti saranno rispettate dalle impostazioni opzioni occupato.
    
- Delega dell'amministratore/capo 
    
  - Le chiamate in arrivo per gli utenti che sono impostati per una delega del capo/amministratore come capo o come amministratore avranno la priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.
    
  - L'esperienza corrente di delega del capo/amministratore rimarrà invariata con opzioni occupato impostate per gli amministratori o il responsabile.
    
  - Le chiamate correlate alla delega non del capo/amministratore agli amministratori verranno rispettate dalle impostazioni opzioni occupato.
    
- Modalità di linea condivisa 
    
  - Le impostazioni di Opzioni occupato per gli account utente impostati per l'aspetto linea condivisa verranno ignorate. 
    
  - Verranno invece rispettate le opzioni Native Busy on Busy di Shared Line Appearance e Voicemail on Busy.
    
- Servizio parcheggio di chiamata 
    
  - Le chiamate parcheggiate che non sono state recuperate e che stanno squillando a causa del timeout potranno squillare anche se all'utente che ha parcheggiato la chiamata tramite le opzioni occupato. 
    
- Conferenza telefonica
    
  - Gli utenti nelle conferenze telefoniche sono considerati occupato e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni di Opzioni occupato.
    
  - Agli utenti delle conferenze non viene impedito di avviare nuove chiamate o conferenze tramite Opzioni occupato.
    
  - Gli utenti delle conferenze sono ancora in grado di ricevere nuovi inviti alle conferenze, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni di disponibilità.
    
- Squillo simultaneo e inoltro di chiamata
    
    La funzionalità Occupato su occupato non è progettata per funzionare con l'anello simultaneo e l'inoltro di chiamata.
    

