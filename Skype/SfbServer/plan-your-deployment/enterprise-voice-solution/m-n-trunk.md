---
title: Trunk MN in Skype for Business Server
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype for Business Server VoIP aziendale supporta il trunking M:N tra Mediation Server e componenti quali gateway PSTN, session border controller e IP-PBX.
ms.openlocfilehash: dc140847e26860716e4beea5abe873f58bd63e90449fb93610329187321d18e9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286475"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Trunk M:N in Skype for Business Server
 
Skype for Business Server VoIP aziendale supporta il trunking M:N tra Mediation Server e componenti quali gateway PSTN, session border controller e IP-PBX.
  
Skype for Business Server supporta una maggiore flessibilità nella definizione di un trunk a scopo di routing delle chiamate rispetto alle versioni precedenti. Un trunk è un'associazione logica tra un Mediation Server e un numero di porta di attesa con un gateway e un numero di porta di attesa. Ciò implica diversi aspetti: un Mediation Server può avere più trunk per lo stesso gateway; un Mediation Server può avere più trunk a gateway diversi; al contrario, un gateway può avere più trunk per Mediation Server diversi.
  
È comunque necessario creare un trunk radice ogni volta che si utilizza Generatore di topologie per aggiungere un gateway alla topologia. Il numero di gateway che un determinato Mediation Server è in grado di gestire dipende dalla capacità di elaborazione del server durante le ore di punta. Se si distribuisce un Mediation Server su hardware che supera i requisiti hardware minimi per Skype for Business Server, come descritto [in Server requirements for Skype for Business Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)la stima del numero di chiamate attive non bypass che un Mediation Server autonomo può gestire è di circa 1000 chiamate. Quando viene distribuito su hardware in base a queste specifiche, il Mediation Server dovrebbe eseguire la transcoding, ma comunque instradare le chiamate per più gateway anche se i gateway non supportano il bypass multimediale.
  
Quando si definisce una route di chiamata, si specificano i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati a tale route. È invece possibile utilizzare Generatore di topologie per associare i trunk ai Mediation Server. In altre parole, il routing determina quale trunk utilizzare per una chiamata e, successivamente, al Mediation Server associato a tale trunk viene inviata la segnalazione per tale chiamata.
  
Il Mediation Server può essere distribuito come pool. questo pool può essere collocato con un pool Front End oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato con un pool Front End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrazione). Nel loro insieme, queste nuove funzionalità aumentano l'affidabilità e la flessibilità di distribuzione per Mediation Server, ma richiedono funzionalità associate nelle entità peer seguenti:
  
- **Gateway PSTN.** Un gateway qualificato Skype for Business Server deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di agire come servizio di bilanciamento del carico per un pool di Mediation Server e quindi di bilanciare il carico delle chiamate nel pool.
    
- **Session Border Controller.** Per un trunk SIP, l'entità peer è un session border controller (SBC) presso un provider di servizi di telefonia Internet. Nella direzione dal pool Mediation Server al servizio SBC, il controller SBC può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per ottenere questo risultato è tramite il bilanciamento del carico DNS, se supportato dal provider di servizi e da SBC. Un'alternativa consiste nel fornire al provider di servizi gli indirizzi IP di tutti i Mediation Server nel pool e il provider di servizi ne eseguirà il provisioning nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBC possono supportare queste funzionalità. Inoltre, il provider di servizi può addebitare costi aggiuntivi per questa funzionalità. In genere, ogni trunk SIP alla SBC comporta una tariffa mensile.
    
- **IP-PBX.** Nella direzione dal pool Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la IP-PBXs non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette da IP-PBX a ogni Mediation Server del pool. Il sistema IP-PBX gestirà quindi il bilanciamento del carico distribuendo il traffico sul gruppo di trunk. Si presuppone che il gruppo di trunk disponga di un insieme coerente di regole di routing nel sistema IP-PBX. Prima di poter decidere se un cluster Mediation Server può interagire correttamente con un IP-PBX, è necessario stabilire se un particolare IP-PBX supporta questo concetto di gruppo trunk e come si interseca con l'architettura di ridondanza e clustering del sistema IP-PBX.
    
Un pool Mediation Server deve disporre di una visualizzazione uniforme del gateway peer con cui interagisce. Ciò significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione ed è altrettanto probabile che interagiranno con esso per le chiamate in uscita. Pertanto, non è possibile segmentare il pool in modo che alcuni Mediation Server comunichino solo con determinati peer gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario utilizzare un pool separato di Mediation Server. Ciò si verifica, ad esempio, se le funzionalità associate nei gateway PSTN, nei trunk SIP o IP-PBXs per interagire con un pool come descritto in precedenza in questo argomento non sono presenti.
  
Un determinato gateway PSTN, IP-PBX o trunk peer SIP può essere instradato a più Mediation Server o trunk. Il numero di gateway che un determinato pool di Mediation Server può controllare dipende dal numero di chiamate che utilizzano il bypass multimediale. Se un numero elevato di chiamate utilizza il bypass multimediale, un Mediation Server nel pool può gestire molte altre chiamate, perché è necessaria solo l'elaborazione del livello di segnalazione. 
  

