---
title: Linee guida per la distribuzione di Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.
ms.openlocfilehash: fdfc18871e4aa9ea30d7a02063e7d1a0bc05b6ca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187913"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Linee guida per la distribuzione di Mediation Server in Skype for Business Server
 
Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Mediation Server è, per impostazione predefinita, collocato nel server Standard Edition o front end server in un pool Front-end presso i siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderà da:
  
- Numero di peer gateway che il pool di Mediation Server controlla.
    
- I periodi di traffico ad alto volume tramite questi gateway.
    
- La percentuale di chiamate che sono chiamate di cui il media Ignora il Mediation Server.
    
Durante la pianificazione, tenere presente i requisiti per l'elaborazione multimediale per le chiamate PSTN e le conferenze A/V che non supportano il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario occupato che devono essere supportati. Se non si dispone di una CPU sufficiente, è necessario distribuire un pool autonomo di Mediation Server. Inoltre, i gateway PSTN, IP-PBX e SBCs dovranno essere divisi in subset controllati dai server di mediazione collocati in un pool e i Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non hanno la possibilità di interagire con un pool di server di mediazione, è necessario che siano associati a un pool autonomo costituito da un singolo Mediation Server. Alcune delle operazioni che i gateway PSTN, i PBX IP o SBCs devono includere:
  
- Eseguire il bilanciamento del carico DNS (Network layer Domain Name System) in Mediation Servers in un pool (o in caso contrario indirizzare il traffico in modo uniforme a tutti i server di mediazione in un pool).
    
- Accettare il traffico da qualsiasi Mediation Server in un pool.
    
Puoi usare lo strumento di pianificazione di Skype for business per valutare se la collocazione di Mediation Server con il pool Front-end può gestire il caricamento. Se l'ambiente non soddisfa questi requisiti, sarà necessario distribuire un pool di Mediation Server autonomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerazioni sul sito centrale e sulla filiale

 I Mediation Server nel sito centrale possono essere usati per instradare le chiamate per i PBX IP o i gateway PSTN nei siti di succursale. Se si distribuiscono trunk SIP, tuttavia, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina. La presenza di un Mediation Server presso la route del sito centrale richiede un gateway IP-PBX o PSTN presso un sito di succursale non richiede l'uso di bypass multimediale, ma è consigliato un bypass multimediale. Questo perché, se è possibile abilitare il bypass multimediale, ridurrà la latenza del percorso multimediale e, di conseguenza, il risultato migliorerà la qualità multimediale, perché il percorso del supporto non è necessario per seguire il percorso di segnalazione. Il bypass multimediale ridurrà anche il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server presso [Esplora dispositivi, infrastrutture e strumenti testati che supportano ed estendono l'esperienza di Skype for business](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Se è necessaria la resilienza del sito di succursale, è necessario distribuire un Survivable Branch Appliance o una combinazione di un server front-end, un Mediation Server e un gateway nel sito della filiale. Il presupposto con la resilienza del sito di succursale è che la presenza e i servizi di conferenza non sono resilienti nel sito. Per informazioni sulla pianificazione del sito di succursale per la voce, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e interazioni RFC 3960, può essere possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo da IP-PBX agli endpoint di Lync. Questo comportamento può essere più grave se un Mediation Server presso un sito centrale sta instradando le chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione. Se si verifica questo comportamento, la distribuzione di un Mediation Server presso il sito della filiale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se il sito centrale ha un PBX TDM o se il tuo IP-PBX non elimina la necessità di un gateway PSTN, devi distribuire un gateway sulla route di chiamata che connette Mediation Server e il PBX.
  
> [!NOTE]
> Per migliorare le prestazioni multimediali di Mediation Server autonomo, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete in questi server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "[miglioramenti della scala sul lato ricezione in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete. 
  

