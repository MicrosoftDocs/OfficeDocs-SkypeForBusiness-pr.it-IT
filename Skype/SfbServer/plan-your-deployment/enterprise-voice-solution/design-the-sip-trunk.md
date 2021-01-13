---
title: Progettare il trunk SIP per il servizio E9-1-1 in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Pianificazione delle topologie del trunking SIP per una distribuzione di E9-1-1 che utilizza i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825796"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Progettare il trunk SIP per il servizio E9-1-1 in Skype for Business Server
 
Pianificazione delle topologie del trunking SIP per una distribuzione di E9-1-1 che utilizza i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
  
Skype for Business Server utilizza trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1. È possibile configurare trunk SIP per i servizi di emergenza per il servizio E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale. Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, una chiamata effettuata da un utente nel sito disconnesso avrà bisogno di un record di utilizzo telefonico speciale nei criteri vocali dell'utente che instraderà la chiamata a ECRC tramite il gateway PSTN (Public Switched Telephone Network). Lo stesso vale se i limiti di chiamata simultanei del controllo di ammissione di chiamata sono attivati.
  
Esistono due modi per implementare un trunk SIP in un ambiente di Skype for Business Server:
  
- Utilizzare i Mediation Server multihomed che utilizzano le interfacce indirizzate al pubblico verso l'esterno per comunicare con il provider trunk SIP.
    
- Utilizzare un session border controller (SBC) locale per fornire un punto di delimitazione sicuro tra i Mediation Server e i servizi del provider del trunk SIP.
    
Se si sceglie il secondo metodo, accertarsi che la marca e il modello SBC scelti siano stati certificati e supporti il passaggio dei dati di posizione del formato dell'oggetto (PIDF-LO) dei dati sulla presenza come parte del relativo invito SIP. In caso contrario, le chiamate arriveranno al provider di servizi di emergenza privato delle informazioni sulla posizione. Per informazioni dettagliate sulle SBCs certificate, vedere   ["infrastruttura qualificata per Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) e ["infrastruttura di telefonia per Skype for business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBCs per la ridondanza. È necessario prendere diverse decisioni in merito alla topologia di Mediation Server e alla configurazione del routing delle chiamate. Si tratterà sia di SBCs come peer uguali che di utilizzare il routing round robin per le chiamate tra di essi oppure si designa un SBC come primario e l'altro come secondario?
  
Per informazioni dettagliate sulla distribuzione di un trunk SIP in Skype for Business Server, vedere [SIP trunking in Skype for Business Server](sip-trunking.md). Le domande seguenti consentiranno di decidere come distribuire i trunk SIP per il servizio E9-1-1.
  
 **È necessario distribuire il trunk SIP su una connessione Internet dedicata affittata o condivisa?**
  
> È importante che le chiamate di emergenza si connettano sempre. Una linea dedicata fornisce una connessione che non verrà interrotta da altro traffico sulla rete e fornisce la possibilità di implementare la qualità del servizio (QoS). Tenere presente che se si sta effettuando la connessione a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec. 
    
 **La distribuzione di E9-1-1 è progettata per la tolleranza di emergenza?**
  
> Poiché si tratta di una soluzione di emergenza, è importante una resilienza. Distribuire i Mediation Server primari e secondari e i trunk SIP nei percorsi con tolleranza di emergenza. È consigliabile distribuire il Mediation Server primario più vicino agli utenti che supportano e instradare le chiamate di failover tramite il Mediation Server secondario (che si trova in una posizione geografica diversa). 
    
 **È necessario distribuire un trunk SIP separato per ogni succursale?**
  
> In Skype for Business Server sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni branch o la pressione delle chiamate verso il gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [SIP trunking in Skype for Business Server](sip-trunking.md).
    
 **Il controllo di ammissione di chiamata è abilitato?**
  
> Skype for Business Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata. Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione di chiamata (CAC) può avere un impatto negativo su una configurazione di E9-1-1. Le chiamate di emergenza verranno bloccate o instradate al gateway PSTN locale se un CAC è abilitato e il limite configurato viene superato su un collegamento in cui vengono instradate le chiamate di emergenza. Come indicato in precedenza in questo argomento, tali chiamate non disporranno di dati di posizione e devono essere instradate manualmente al ECRC.
    

