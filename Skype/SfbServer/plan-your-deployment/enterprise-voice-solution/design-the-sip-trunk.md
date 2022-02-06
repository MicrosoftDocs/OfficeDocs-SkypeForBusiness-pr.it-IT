---
title: Progettare il trunk SIP per E9-1-1 in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 'Pianificazione delle topologie di trunking SIP per una distribuzione E9-1-1 che utilizza provider di trunking SIP, in Skype for Business Server VoIP aziendale.'
---

# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Progettare il trunk SIP per E9-1-1 in Skype for Business Server
 
Pianificazione delle topologie di trunking SIP per una distribuzione E9-1-1 che utilizza provider di trunking SIP, in Skype for Business Server VoIP aziendale.
  
Skype for Business Server i trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1. È possibile configurare i trunk SIP del servizio di emergenza per E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale. Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, una chiamata effettuato da un utente nel sito disconnesso avrà bisogno di uno speciale record di utilizzo del telefono nei criteri vocali dell'utente che instraderà la chiamata all'ECRC attraverso il gateway PSTN (Public Switched Telephone Network) locale. Lo stesso vale se sono in vigore limiti di chiamata simultanei per il controllo di ammissione di chiamata.
  
Esistono due modi per implementare un trunk SIP in un Skype for Business Server ambiente:
  
- Utilizzare Mediation Server multihomed che utilizzano le interfacce indirizzate pubblicamente verso l'esterno per comunicare con il provider trunk SIP.
    
- Utilizzare un session border controller (SBC) locale per fornire un punto di demarcazione sicuro tra Mediation Server e i servizi del provider trunk SIP.
    
Se si sceglie quest'ultimo metodo, assicurarsi che il modello e il modello SBC scelto siano stati certificati e supportino il passaggio dei dati di posizione PIDF-LO (Presence Information Data Format Location Object) come parte del relativo SIP INVITE. In caso contrario, le chiamate arriveranno al provider di servizi di emergenza privato delle informazioni sulla posizione. Per informazioni dettagliate sugli SBC certificati, vedere ["Infrastruttura qualificata per Microsoft Lync"](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) e ["Infrastruttura](../../../SfbPartnerCertification/certification/infra-gateways.md) di telefonia per Skype for Business". 
  
I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBC per la ridondanza. È necessario prendere diverse decisioni relative alla topologia Mediation Server e alla configurazione del routing delle chiamate. Verranno trattati entrambi gli SBC come peer uguali e verrà utilizzato il routing round robin per le chiamate tra di essi oppure si designerà uno SBC come primario e l'altro come secondario?
  
Per informazioni dettagliate sulla distribuzione di un trunk SIP in Skype for Business Server, vedere [Trunking SIP in Skype for Business Server](sip-trunking.md). Le domande seguenti consentono di decidere come distribuire i trunk SIP per E9-1-1.
  
 **È consigliabile distribuire il trunk SIP su una connessione Internet condivisa o con lease dedicata?**
  
> È importante che le chiamate di emergenza si connettono sempre. Una linea dedicata fornisce una connessione che non sarà preempted da altro traffico sulla rete e offre la possibilità di implementare qualità del servizio (QoS). Tenere presente che se ci si connette a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec. 
    
 **La distribuzione di E9-1-1 è progettata per la tolleranza di emergenza?**
  
> Poiché si tratta di una soluzione di emergenza, la resilienza è importante. Distribuire i Mediation Server primari e secondari e i trunk SIP in posizioni a tolleranza di emergenza. È buona idea distribuire il Mediation Server primario più vicino agli utenti che supporta e instradare le chiamate di failover attraverso il Mediation Server secondario (che si trova in una posizione geografica diversa). 
    
 **È consigliabile distribuire un trunk SIP separato per ogni succursale?**
  
> Skype for Business Server fornisce diverse strategie per gestire la resilienza vocale nelle succursali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni succursale o distribuire chiamate al gateway locale durante le interruzioni. Per informazioni dettagliate, [vedere Trunking SIP in Skype for Business Server](sip-trunking.md).
    
 **Il servizio Controllo di ammissione di chiamata è abilitato?**
  
> Skype for Business Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata. Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione di chiamata (CAC) può avere un impatto negativo su una configurazione E9-1-1. Le chiamate di emergenza verranno bloccate o instradate al gateway PSTN locale se è abilitato un controllo di ammissione di chiamata e il limite configurato viene superato su un collegamento in cui vengono instradate le chiamate di emergenza. Come indicato in precedenza in questo argomento, tali chiamate non avranno dati sulla posizione e devono essere instradati manualmente all'ECRC.
