---
title: Trunk MN in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype for Business Server VoIP Enterprise Voice supporta il trunking di M:N tra Mediation Server e componenti come gateway PSTN, controller Border sessione e IP-PBX.
ms.openlocfilehash: d9a4a4f08f71cf00e079a5fe9fc5598380936474
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802736"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Trunk M:N in Skype for Business Server
 
Skype for Business Server VoIP Enterprise Voice supporta il trunking di M:N tra Mediation Server e componenti come gateway PSTN, controller Border sessione e IP-PBX.
  
Skype for Business Server supporta una maggiore flessibilità nella definizione di un trunk per scopi di routing delle chiamate da versioni precedenti. Un trunk è un'associazione logica tra un Mediation Server e un numero di porta in ascolto con un gateway e un numero di porta in ascolto. Questo implica diversi elementi: un Mediation Server può avere più Trunks nello stesso gateway; un Mediation Server può avere più Trunks in Gateway diversi; viceversa, un gateway può avere più Trunks in diversi server di mediazione.
  
È comunque necessario creare un trunk radice ogni volta che si usa generatore di topologie per Adde un gateway alla topologia. Il numero di gateway che un server di mediazione specifico può gestire dipende dalla capacità di elaborazione del server durante le ore di punta occupato. Se si distribuisce un Mediation Server su hardware che supera i requisiti hardware minimi per Skype for Business Server, come descritto in [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), la stima del numero di chiamate non di bypass attive in un server di mediazione autonomo può essere gestito in base a circa 1000 chiamate. Una volta distribuite su hardware che soddisfano queste specifiche, è previsto che il Mediation Server esegua la transcodifica, ma continui a eseguire chiamate per più gateway, anche se i gateway non supportano il bypass multimediale.
  
Quando si definisce una route di chiamata, è necessario specificare i trunk associati alla route, ma non si specificano i server di mediazione associati alla route. Puoi invece usare generatore di topologia per associare Trunks a Mediation Servers. In altre parole, il routing determina il trunk da usare per una chiamata e, successivamente, il Mediation Server associato a tale trunk viene inviato alla segnalazione per la chiamata.
  
Il Mediation Server può essere distribuito come pool; questo pool può essere collocato con un pool Front-end oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato in un pool Front-End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrar). Queste nuove funzionalità aumentano la flessibilità di affidabilità e distribuzione per i server di mediazione, ma richiedono funzionalità associate nelle seguenti entità peer:
  
- **Gateway PSTN.** Un gateway abilitato per Skype for Business Server deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di fungere da servizio di bilanciamento del carico per un pool di server di mediazione e quindi di effettuare il bilanciamento del carico attraverso il pool .
    
- **Controller di bordo della sessione.** Per un trunk SIP, l'entità peer è un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet. Nella direzione dal pool di Mediation Server a SBC, SBC può ricevere connessioni da qualsiasi server di mediazione nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per raggiungere questo obiettivo è il bilanciamento del carico DNS, se supportato dal provider di servizi e da SBC. In alternativa, è possibile assegnare al provider di servizi gli indirizzi IP di tutti i server di mediazione nel pool e il provider di servizi li provisionerà nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBCs potrebbero supportare queste funzionalità. Inoltre, il provider di servizi può addebitare un supplemento per questa funzionalità. In genere, ogni trunk SIP all'SBC comporta una tariffa mensile.
    
- **IP-PBX.** Nella direzione dal pool di Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi server di mediazione nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la maggior parte dei sistemi IP-PBX non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette da IP-PBX a ogni Mediation Server nel pool. L'IP-PBX gestirà il proprio bilanciamento del carico distribuendo il traffico sul gruppo Trunk. Il presupposto è che il gruppo Trunk abbia una serie di regole di routing coerenti in IP-PBX. Se un determinato IP-PBX supporta questo concetto di gruppo Trunk e il modo in cui interseca l'architettura di ridondanza e clustering dell'IP-PBX deve essere determinato prima di poter decidere se un cluster di Mediation Server può interagire correttamente con un IP-PBX.
    
Un pool di Mediation Server deve avere una visualizzazione uniforme del gateway peer con cui interagisce. Questo significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione e hanno ugualmente la possibilità di interagire con essa per le chiamate in uscita. Di conseguenza, non è possibile segmentare il pool in modo che alcuni Mediation Server comunicano solo con determinati peer del gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario usare un pool separato di server di mediazione. Questo è il caso, ad esempio, se le funzionalità associate in gateway PSTN, trunk SIP o IP-PBX per interagire con un pool come descritto in precedenza in questo argomento non sono presenti.
  
Un particolare gateway PSTN, IP-PBX o un peer trunk SIP può essere indirizzato a più server di mediazione o trunk. Il numero di gateway che un determinato pool di server di mediazione può controllare dipende dal numero di chiamate che usano il bypass multimediale. Se un numero elevato di chiamate usa il bypass multimediale, un Mediation Server nel pool può gestire molte altre chiamate, perché è necessario solo l'elaborazione dei livelli di segnalazione. 
  

