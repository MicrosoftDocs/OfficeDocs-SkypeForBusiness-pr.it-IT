---
title: Pianificare le opzioni di disponibilità per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813696"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Pianificare le opzioni di disponibilità per Skype for Business Server
 
Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.
  
Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica. 
  
Il criterio Opzioni occupato è supportato per il failover e il ripristino di emergenza in pool Front End e Survivable Branch Server (SBS) accoppiati.
  
In questo argomento vengono descritte le funzionalità delle opzioni non disponibili. Per informazioni su come installare e configurare le opzioni occupato, vedere Installare e configurare le opzioni di occupato [per Skype for Business Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>Opzioni di configurazione

Se le opzioni occupato sono abilitate per l'organizzazione, tutti gli utenti dell'organizzazione, sia VoIP aziendale che non VoIP aziendale utenti, possono utilizzare le funzionalità seguenti:
  
- Occupato: in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.
    
- Segreteria telefonica su occupato- In cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.
    
La funzionalità Opzioni occupato offre funzionalità di failover. Se si verifica un problema e si verifica il failover degli utenti in un altro Front End Server o in un altro pool in Skype for Business Server, le impostazioni delle opzioni di disponibilità verranno mantenute.
  
Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o agli utenti con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze. 
  
Dopo la configurazione, l'impostazione Opzioni occupato è attiva per tutti i dispositivi e i client di chiamata Skype for Business dell'utente. In base alle impostazioni relative alle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non squilla su nessuno dei dispositivi di chiamata dell'utente, inclusi Macintosh, Windows Desktop, client mobili o telefoni IP, a cui l'utente ha effettuato l'accesso. 
  
Gli utenti potranno visualizzare le notifiche di chiamata senza risposta sui propri client e dispositivi Skype for Business e riceveranno una notifica anche tramite posta elettronica. I chiamanti la cui chiamata è stata rifiutata a causa di Occupato riceveranno una notifica nel client Skype for Business che informa che l'utente che ha tentato di raggiungere è occupato in un'altra chiamata.
  
È possibile configurare la funzionalità Opzioni occupato utilizzando i cmdlet di PowerShell di Skype for Business per:
  
- Abilitare o disabilitare i criteri vocali opzioni occupato per l'organizzazione.
    
- Amministrare occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti dell'organizzazione.
    
- Amministrare occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti ospitati in un particolare pool Front End.
    
- Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per un elenco di utenti.
    
- Amministrare occupato su occupato o segreteria telefonica su occupato per un singolo utente.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilità con le applicazioni vocali

Opzioni occupato garantisce l'interoperabilità con le seguenti applicazioni vocali in Skype for Business:
  
- Response Group (RGS)
    
  - Le opzioni di occupato impostate sui numeri di Response Group verranno ignorate dal sistema. saranno consentite più chiamate simultanee. 
    
  - L'esperienza di routing dell'Operatore corrente in Response Group rimarrà invariata per gli agenti con le impostazioni delle opzioni di disponibilità.
    
  - Le chiamate provenienti da Response Group agli utenti che sono agenti di Response Group non verranno limitate dalle impostazioni delle opzioni occupato e l'esperienza RGS corrente verrà mantenuta.
    
  - Le chiamate non correlate a RGS agli agenti verranno rispettate dalle relative impostazioni relative alle opzioni di disponibilità.
    
- Intercettazione team
    
  - Le chiamate in arrivo agli utenti impostati per una chiamata al team verranno classificate in ordine di priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.
    
  - L'esperienza corrente della chiamata al team rimarrà invariata con le opzioni occupato impostate per gli utenti.
    
  - Le chiamate non del team correlate a tali utenti verranno rispettate dalle impostazioni delle opzioni occupato.
    
- Delega capo/amministratore 
    
  - Le chiamate in arrivo verso gli utenti che sono impostati per una delega di capo/amministratore come capo o come amministratore avranno la priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.
    
  - L'esperienza corrente di delega del capo/amministratore rimarrà invariata con le opzioni occupato impostate per gli amministratori o il capo.
    
  - Le chiamate agli amministratori correlate alla delega non del capo/amministratore verranno rispettate dalle impostazioni delle opzioni occupato.
    
- Modalità di linea condivisa 
    
  - Le impostazioni relative alle opzioni non disponibili per gli account utente impostati per l'aspetto della linea condivisa verranno ignorate. 
    
  - Verranno invece rispettate le opzioni Native Busy on Busy e Voicemail on Busy di Shared Line Appearance.
    
- Servizio parcheggio di chiamata 
    
  - Le chiamate parcheggiate che non sono state recuperate e che squillano a causa del timeout potranno squillare anche se all'utente che ha parcheggiato la chiamata dalle opzioni occupato. 
    
- Conferenza telefonica
    
  - Gli utenti nelle conferenze telefoniche sono considerati non disponibili e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni di occupato.
    
  - Agli utenti delle conferenze non viene impedito di avviare nuove chiamate o conferenze tramite Opzioni occupato.
    
  - Gli utenti delle conferenze sono ancora in grado di ricevere nuovi inviti alle conferenze, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni di occupato.
    
- Squillo simultaneo e inoltro di chiamata
    
    La funzionalità Occupato non è progettata per funzionare con lo squillo simultaneo e l'inoltro di chiamata.
    

