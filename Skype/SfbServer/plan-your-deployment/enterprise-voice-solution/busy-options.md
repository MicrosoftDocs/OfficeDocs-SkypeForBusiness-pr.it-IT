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
description: Per ulteriori informazioni, vedere la funzionalità opzioni occupato in Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813696"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Pianificare le opzioni di disponibilità per Skype for Business Server
 
Per ulteriori informazioni, vedere la funzionalità opzioni occupato in Skype for Business Server.
  
Busy options è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare il modo in cui le chiamate in arrivo vengono gestite quando un utente è già in una chiamata o in una conferenza oppure ha una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica. 
  
Il criterio delle opzioni di occupato è supportato per il failover e il ripristino di emergenza in pool Front End associati e Survivable Branch Server (SBS).
  
In questo argomento vengono descritte le caratteristiche delle opzioni di occupato. Per informazioni su come installare e configurare le opzioni di occupato, vedere [Install and Configure busy options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opzioni di configurazione

Se per l'organizzazione sono abilitate le opzioni di disponibilità, tutti gli utenti dell'organizzazione, sia VoIP aziendale che utenti non di VoIP aziendale, possono utilizzare le seguenti funzionalità:
  
- Occupato su occupato-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.
    
- Segreteria telefonica su occupato-in cui le nuove chiamate in entrata verranno inoltrate alla segreteria telefonica se l'utente è occupato.
    
La funzionalità opzioni occupate offre funzionalità di failover. Se si verifica un problema e gli utenti eseguono il failover su un altro front end server o su un altro pool in Skype for Business Server, verranno mantenute le impostazioni delle opzioni occupate.
  
Indipendentemente dal modo in cui sono configurate le opzioni di disponibilità, gli utenti di una chiamata o di una conferenza o di quelli con una chiamata in attesa non sono stati impediti dall'avvio di nuove chiamate o conferenze. 
  
Dopo la configurazione, l'impostazione delle opzioni di occupato è attiva per tutti i client e i dispositivi di chiamata Skype for business dell'utente. In base alle impostazioni delle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non suonerebbe nei dispositivi di chiamata dell'utente, inclusi Macintosh, desktop di Windows, client mobili o telefoni IP, in cui l'utente ha eseguito l'accesso. 
  
Gli utenti visualizzeranno le notifiche di chiamata senza risposta nei client e dispositivi Skype for business e verranno informati anche tramite posta elettronica. I chiamanti la cui chiamata è stata rifiutata a causa di occupato su occupato vedrà una notifica nel loro client Skype for business che indica che l'utente che ha tentato di raggiungere è occupato su un'altra chiamata.
  
È possibile configurare la funzionalità di opzioni di occupato tramite i cmdlet di PowerShell per Skype for business per:
  
- Abilitare o disabilitare i criteri vocali per le opzioni di disponibilità per l'organizzazione.
    
- Amministrare occupato su occupato o segreteria telefonica su occupato per tutti gli utenti dell'organizzazione.
    
- Amministrare occupato su occupato o segreteria telefonica su occupato per tutti gli utenti ospitati in un pool Front end specifico.
    
- Amministrare occupato su occupato o segreteria telefonica su occupato per un elenco di utenti.
    
- Amministrare occupato su occupato o segreteria telefonica su occupato per un singolo utente.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilità con le applicazioni vocali

Le opzioni di occupato offrono interoperabilità con le applicazioni vocali seguenti in Skype for business:
  
- Gruppi di risposta (RGS)
    
  - Le opzioni di occupato impostate sui numeri dei Response Group verranno ignorate dal sistema. sono consentite più chiamate simultanee. 
    
  - L'esperienza di routing degli addetti corrente nei Response Group rimarrà invariata per gli agenti con impostazioni delle opzioni occupate.
    
  - Le chiamate provenienti da Response Group per gli utenti che sono agenti Response Group non verranno limitate dalle impostazioni delle opzioni occupate e l'esperienza di RGS corrente verrà mantenuta.
    
  - Le chiamate correlate non RGS agli agenti saranno onorate dalle impostazioni relative alle opzioni occupate.
    
- Intercettazione team
    
  - Le chiamate in arrivo per gli utenti che sono configurati per una chiamata del team avranno la priorità per ignorare occupato su occupato e segreteria telefonica su impostazioni occupato.
    
  - L'esperienza di chiamata del team corrente rimarrà invariata con le opzioni di occupato impostate per gli utenti.
    
  - Le chiamate non correlate alla chiamata del team a tali utenti verranno onorate dalle impostazioni relative alle opzioni occupate.
    
- Delega di boss/admin 
    
  - Le chiamate in arrivo per gli utenti che sono configurati per una delega di boss/amministratore o come capo o amministratore avranno la priorità di ignorare occupato su occupato e segreteria telefonica su impostazioni occupato.
    
  - L'esperienza di delega corrente del boss/amministratore rimarrà invariata con le opzioni di occupato impostate per gli amministratori o il boss.
    
  - Le chiamate di deleghe non boss/admin correlate agli amministratori saranno onorate dalle impostazioni relative alle opzioni occupate.
    
- Modalità di linea condivisa 
    
  - Le impostazioni delle opzioni di occupato sugli account utente configurati per l'aspetto della linea condivisa verranno ignorate. 
    
  - L'aspetto nativo della linea condivisa è occupato da occupato e la segreteria telefonica su Opzioni occupate verrà invece rispettata.
    
- Servizio parcheggio di chiamata 
    
  - Le chiamate parcheggiate che non sono state recuperate e squillano di nuovo a causa dei tempi di inattività potranno squillare anche se all'utente che ha parcheggiato la chiamata dalle opzioni di occupato. 
    
- Conferenze telefoniche
    
  - Gli utenti nelle chiamate in conferenza sono considerati occupati e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni di occupato.
    
  - Agli utenti nelle conferenze non è impedito di avviare nuove chiamate o conferenze in base alle opzioni di occupato.
    
  - Gli utenti nelle conferenze sono ancora in grado di ricevere nuovi inviti alla conferenza, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni occupate.
    
- Squillo simultaneo e inoltro di chiamata
    
    La funzionalità occupato su occupato non è progettata per l'utilizzo con squillo simultaneo e inoltro di chiamata.
    

