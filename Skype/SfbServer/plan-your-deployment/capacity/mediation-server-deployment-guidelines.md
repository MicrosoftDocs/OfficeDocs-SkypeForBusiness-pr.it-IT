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
description: Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800091"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Linee guida per la distribuzione di Mediation Server in Skype for Business Server
 
Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Mediation Server è, per impostazione predefinita, collocato nel server Standard Edition o front end server in un pool Front end nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipendono da:
  
- Il numero di peer gateway che vengono controllati dal pool di Mediation Server.
    
- I periodi di traffico ad alto volume attraverso tali gateway.
    
- La percentuale di chiamate che sono chiamate con il supporto bypassare il Mediation Server.
    
Quando si pianifica, assicurarsi di prendere in considerazione i requisiti di elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V che non supportano il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di occupato che devono essere supportate. Se non si dispone di un numero sufficiente di CPU, è necessario distribuire un pool autonomo di Mediation Server. Inoltre, i gateway PSTN, IP-PBX e SBCs dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e nei Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non dispongono della possibilità di interagire con un pool di Mediation Server, dovranno essere associati a un pool autonomo costituito da un singolo Mediation Server. Di seguito sono riportate alcune delle operazioni che i gateway PSTN, IP-PBXs o SBCs devono includere:
  
- Eseguire il bilanciamento del carico DNS (Domain Name System) di Network layer su Mediation Server in un pool (o altrimenti instradare il traffico in modo uniforme a tutti i Mediation Server in un pool).
    
- Accetta il traffico proveniente da qualsiasi Mediation Server in un pool.
    
È possibile utilizzare lo strumento di pianificazione di Skype for business per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente in uso non è in grado di soddisfare questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

 I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se si distribuiscono trunk SIP, tuttavia, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina. La presenza di un Mediation Server nella route del sito centrale richiede un gateway IP-PBX o PSTN in un sito di succursale non richiede l'utilizzo del bypass multimediale, ma è consigliato un bypass multimediale. Questo perché, se è possibile abilitare il bypass multimediale, la latenza del percorso multimediale verrà ridotta e, di conseguenza, si otterrà una migliore qualità multimediale perché il percorso multimediale non è necessario per seguire il percorso di segnalazione. Media Bypass consente inoltre di diminuire il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con tutti i gateway PSTN, IP-PBX e SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server at [Explore Tested Devices, Infrastructure, and Tools that support and extend your Skype for Business Experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. (L'assunzione con resilienza del sito di succursale è che la presenza e la conferenza non sono resilienti nel sito). Per istruzioni sulla pianificazione dei siti di succursale per la voce, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Per le interazioni con un sistema IP-PBX, se il sistema IP-PBX non supporta correttamente le interazioni tra i media iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile che vengano ritagliate le prime parole del messaggio di saluto per le chiamate in arrivo dal sistema IP-PBX agli endpoint di Lync. Questo comportamento può essere più grave se un server Mediation Server in un sito centrale instrada le chiamate per un sistema IP-PBX in cui la route termina in un sito derivato, in quanto è necessario più tempo per il completamento dei segnali. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.
  
> [!NOTE]
> Per migliorare le prestazioni dei supporti di Mediation Server autonomo, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete su questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere la[sezione relativa ai miglioramenti della scala di ricezione in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731). Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete. 
  

