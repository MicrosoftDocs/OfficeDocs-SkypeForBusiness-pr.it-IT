---
title: Progettare il trunk SIP per E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Pianificazione delle topologie di trunking SIP per una distribuzione E9-1-1 che usa i provider di trunking SIP in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 1d3b55fd6bb61fbf83f1a2294c96503b816f9c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187739"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Progettare il trunk SIP per E9-1-1 in Skype for Business Server
 
Pianificazione delle topologie di trunking SIP per una distribuzione E9-1-1 che usa i provider di trunking SIP in Skype for Business Server VoIP aziendale.
  
Skype for Business Server usa trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1. È possibile configurare trunk SIP per i servizi di emergenza per E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale. Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, la chiamata effettuata da un utente nel sito disconnesso avrà bisogno di un record di utilizzo telefonico speciale nel criterio vocale dell'utente che instraderà la chiamata al ECRC tramite il gateway PSTN (Public Switched Telephone Network) locale. Lo stesso vale se i limiti delle chiamate simultanee del controllo di ammissione di chiamata sono in vigore.
  
Esistono due modi per implementare un trunk SIP in un ambiente di Skype for Business Server:
  
- Usare i server di mediazione multihome che usano le interfacce indirizzate verso l'esterno per comunicare con il provider trunk SIP.
    
- Usare un SBC (Session Border Controller) locale per garantire un punto di demarcazione sicuro tra i servizi Mediation Server e il provider trunk SIP.
    
Se si sceglie quest'ultimo metodo, assicurarsi che la creazione e il modello SBC scelti siano stati certificati e supporti il passaggio dei dati della posizione (PIDF-LO) del formato dei dati della presenza durante il SIP INVITE. In caso contrario, le chiamate arriveranno presso il provider di servizi di emergenza privato delle informazioni sulla posizione. Per informazioni dettagliate sulle SBCs certificate, vedere ["infrastruttura qualificata per Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) e ["infrastruttura per la telefonia per Skype for business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBCs per la ridondanza. È necessario prendere diverse decisioni per quanto riguarda la topologia di Mediation Server e la configurazione del routing delle chiamate. Si tratterà sia di SBCs come peer uguali che di usare il routing round robin per le chiamate tra di essi oppure si designa un SBC come primario e l'altro come secondario?
  
Per informazioni dettagliate sulla distribuzione di un trunk SIP in Skype for Business Server, vedere [trunking SIP in Skype for Business Server](sip-trunking.md). Le domande seguenti consentiranno di decidere come distribuire i trunk SIP per E9-1-1.
  
 **È consigliabile distribuire il trunk SIP in una connessione Internet dedicata o affittata?**
  
> È importante che le chiamate di emergenza si connettano sempre. Una linea dedicata offre una connessione che non verrà superata da altri traffici sulla rete e offre la possibilità di implementare la qualità del servizio (QoS). Tenere presente che, se ci si connette a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec. 
    
 **La distribuzione E9-1-1 è progettata per la tolleranza ai disastri?**
  
> Poiché si tratta di una soluzione di emergenza, la resilienza è importante. Distribuire i server di mediazione primari e secondari e i trunk SIP in posizioni tolleranti al disastro. È consigliabile distribuire il server di mediazione principale più vicino agli utenti supportati e instradare le chiamate di failover tramite il Mediation Server secondario (che si trova in una posizione geografica diversa). 
    
 **È necessario distribuire un trunk SIP separato per ogni filiale?**
  
> Skype for Business Server offre diverse strategie per la gestione della resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni ramo o spingere le chiamate verso il gateway locale durante le interruzioni. Per informazioni dettagliate, Vedi [trunking SIP in Skype for Business Server](sip-trunking.md).
    
 **Il controllo di ammissione delle chiamate (CAC) è abilitato?**
  
> Skype for Business Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata. Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione delle chiamate (CAC) possono avere un impatto negativo su una configurazione E9-1-1. Le chiamate di emergenza verranno bloccate o indirizzate al gateway PSTN locale se è abilitato un CAC e il limite configurato viene superato in un collegamento in cui vengono instradate le chiamate di emergenza. Come indicato in precedenza in questo argomento, tali chiamate non avranno dati sulla posizione e dovranno essere indirizzate manualmente al ECRC.
    

