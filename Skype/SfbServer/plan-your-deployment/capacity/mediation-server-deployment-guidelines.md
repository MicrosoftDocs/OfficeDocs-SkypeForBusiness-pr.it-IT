---
title: Linee guida per la distribuzione di Mediation Server in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: In questo argomento vengono descritte le linee guida per la pianificazione della distribuzione di Mediation Server.
ms.openlocfilehash: 693a24f6e71b2eee0a3b2881295b65087fe50bf25b03a2647df6df970509f26e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317461"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Linee guida per la distribuzione di Mediation Server in Skype for Business Server
 
In questo argomento vengono descritte le linee guida per la pianificazione della distribuzione di Mediation Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Mediation Server è, per impostazione predefinita, collocato nel edizione Standard server o front-end server in un pool Front End nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderà da:
  
- Numero di peer gateway che il pool Mediation Server controlla.
    
- I periodi di traffico con volumi elevati attraverso tali gateway.
    
- Percentuale di chiamate che sono chiamate il cui supporto ignora il Mediation Server.
    
Durante la pianificazione, assicurarsi di prendere in considerazione i requisiti di elaborazione multimediale per le chiamate PSTN e le conferenze audio/video che non supportano il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di lavoro che devono essere supportate. Se la CPU non è sufficiente, sarà necessario distribuire un pool autonomo di Mediation Server. Inoltre, i gateway PSTN, i server IP-IP e gli SBC dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e dai Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBC o session border controller (SBC) che non sono in grado di interagire con un pool di Mediation Server, sarà necessario associarli a un pool autonomo costituito da un singolo Mediation Server. Alcune delle operazioni che i gateway PSTN, IP-PBXs o SBC dovranno eseguire includono:
  
- Eseguire il bilanciamento del carico DNS (Domain Name System) a livello di rete tra Mediation Server in un pool o instradare il traffico in modo uniforme a tutti i Mediation Server di un pool.
    
- Accettare il traffico da qualsiasi Mediation Server in un pool.
    
È possibile utilizzare lo Skype for Business Planning Tool per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, sarà necessario distribuire un pool Mediation Server autonomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

 I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un Mediation Server nel sito in cui termina ogni trunk. Disporre di un Mediation Server nel sito centrale instradare le chiamate per un gateway IP-PBX o PSTN in un sito di succursale non richiede l'uso del bypass multimediale, ma è consigliabile utilizzare un bypass multimediale. Questo perché, se è possibile abilitare il bypass multimediale, riduce la latenza del percorso multimediale e, di conseguenza, comporta una qualità multimediale migliorata perché il percorso multimediale non è necessario per seguire il percorso di segnalazione. Media Bypass consente inoltre di diminuire il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PBC Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program - Lync Server in [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. Il presupposto con resilienza del sito di succursale è che la presenza e le conferenze non siano resilienti nel sito. Per indicazioni sulla pianificazione del sito di succursale per la funzionalità [vocale, vedere Plan for VoIP aziendale resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo dall'IP-PBX agli endpoint Lync. Questo comportamento può essere più grave se un server Mediation Server in un sito centrale instrada le chiamate per un sistema IP-PBX in cui la route termina in un sito derivato, in quanto è necessario più tempo per il completamento dei segnali. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.
  
> [!NOTE]
> Per migliorare le prestazioni multimediali del Mediation Server autonomo, è consigliabile abilitare il ridimensionamento sul lato ricezione (RSS) sulle schede di rete in questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Receive-Side Scaling Enhancements in Windows Server](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Per informazioni dettagliate su come abilitare RSS, vedere la documentazione della scheda di rete. 
