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
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800091"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Linee guida per la distribuzione di Mediation Server in Skype for Business Server
 
In questo argomento vengono descritte le linee guida per la pianificazione della distribuzione di Mediation Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Per impostazione predefinita, il Mediation Server è collocato nel server Standard Edition o nel Front End Server in un pool Front End nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderanno da:
  
- Numero di peer gateway che il pool Mediation Server controlla.
    
- I periodi di traffico ad alto volume attraverso tali gateway.
    
- Percentuale di chiamate il cui contenuto multimediale ignora il Mediation Server.
    
Durante la pianificazione, assicurarsi di prendere in considerazione i requisiti di elaborazione multimediale per le chiamate PSTN e le conferenze audio/video che non supportano il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orari di punta che devono essere supportate. Se la CPU non è sufficiente, sarà necessario distribuire un pool autonomo di Mediation Server. Inoltre, i gateway PSTN, i server IP-IP e gli SBC dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e dai Mediation Server autonomi in uno o più pool autonomi.
  
Se sono stati distribuiti gateway PSTN, IP-PBC o Session Border Controller (SBC) che non sono in grado di interagire con un pool di Mediation Server, dovranno essere associati a un pool autonomo costituito da un singolo Mediation Server. Alcune delle operazioni che i gateway PSTN, IP-PBXs o SBC dovranno eseguire includono:
  
- Eseguire il bilanciamento del carico DNS (Domain Name System) a livello di rete tra Mediation Server in un pool (o instradare il traffico in modo uniforme a tutti i Mediation Server in un pool).
    
- Accettare il traffico da qualsiasi Mediation Server in un pool.
    
È possibile utilizzare lo strumento di pianificazione di Skype for Business per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente non è in grado di soddisfare questi requisiti, sarà necessario distribuire un pool Mediation Server autonomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

 I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina. Disporre di un Mediation Server nel sito centrale instradare le chiamate per un gateway IP-PBX o PSTN in un sito di succursale non richiede l'uso del bypass multimediale, ma è consigliabile utilizzare un bypass multimediale. Questo perché, se è possibile abilitare il bypass multimediale, riduce la latenza del percorso multimediale e, di conseguenza, migliora la qualità multimediale perché il percorso multimediale non è necessario per seguire il percorso di segnalazione. Media Bypass consente inoltre di diminuire il carico di elaborazione nel pool.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel programma Unified Communications Open Interoperability Program- Lync Server in [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience.](http://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. La resilienza dei siti di succursale presuppone che la presenza e le conferenze non siano resilienti nel sito. Per indicazioni sulla pianificazione dei siti di succursale per la funzionalità vocale, vedere Pianificare [VoIP aziendale resilienza in Skype for Business Server.](../enterprise-voice-solution/enterprise-voice-resiliency.md)
  
Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo da IP-PBX agli endpoint Lync. Questo comportamento può essere più grave se un server Mediation Server in un sito centrale instrada le chiamate per un sistema IP-PBX in cui la route termina in un sito derivato, in quanto è necessario più tempo per il completamento dei segnali. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.
  
Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.
  
> [!NOTE]
> Per migliorare le prestazioni multimediali del Mediation Server autonomo, è necessario abilitare il ridimensionamento sul lato ricezione (RSS) nelle schede di rete in questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "[Miglioramenti al ridimensionamento](https://go.microsoft.com/fwlink/p/?LinkId=268731)sul lato ricezione in Windows Server". Per informazioni dettagliate su come abilitare RSS, vedere la documentazione della scheda di rete. 
  

