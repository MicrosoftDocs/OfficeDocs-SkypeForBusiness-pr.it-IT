---
title: 'Lync Server 2013: linee guida per la distribuzione di Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55ec3444348b2717721dcad890a4712cd8b9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Linee guida per la distribuzione di Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-12_

Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server. Dopo aver esaminato queste linee guida, è consigliabile utilizzare lo strumento di pianificazione per creare e visualizzare le possibili topologie alternative, che possono essere utilizzate come modelli per l'aspetto della topologia sartoriale finale che si decide di distribuire.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Per impostazione predefinita, Mediation Server è collocato nel server Standard Edition o Front End Server in un pool Front-End nei siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipendono dai seguenti elementi:

  - Il numero di peer gateway che il pool di Mediation Server controlla

  - I periodi di traffico ad alto volume tramite quei gateway

  - La percentuale di chiamate che sono chiamate con il supporto bypassare il Mediation Server

Durante la pianificazione, tenere conto dei requisiti di elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V che non sono configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di occupato che devono essere supportate. Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server. i gateway PSTN, IP-PBX e SBCs dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e nei Mediation Server autonomi in uno o più pool autonomi.

Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di Mediation Server, tra cui i seguenti, dovranno essere associati a un pool autonomo costituito da di un singolo Mediation Server:

  - Eseguire il bilanciamento del carico DNS (Domain Name System) di Network layer su Mediation Server in un pool (o altrimenti instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)

  - Accettazione del traffico proveniente da qualsiasi server Mediation Server in un pool

È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Considerazioni relative al sito centrale e al sito derivato

I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un server Mediation Server presso il sito in cui ogni trunk termina. Per fare in modo che un server Mediation Server nel sito centrale instradi le chiamate per un IP-PBX o un gateway PSTN in un sito derivato, non è necessario utilizzare Media Bypass. Se tuttavia è possibile abilitare Media Bypass, sarà possibile ridurre la latenza del percorso del contenuto multimediale e, di conseguenza, migliorare la qualità multimediale in quanto non sarà più necessario che il percorso del contenuto multimediale segua il percorso di segnalazione. Media Bypass consente inoltre di diminuire il carico di elaborazione nel pool.

<div>


> [!NOTE]  
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>at.



</div>

Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway. (L'assunzione con resilienza del sito di succursale è che la presenza e la conferenza non sono resilienti nel sito). Per istruzioni sulla pianificazione dei siti di succursale per la voce, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Per le interazioni con un sistema IP-PBX, se il sistema IP-PBX non supporta correttamente le interazioni tra i media iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile che vengano ritagliate le prime parole del messaggio di saluto per le chiamate in arrivo dal sistema IP-PBX agli endpoint di Lync. Questo comportamento può essere più grave se un server Mediation Server in un sito centrale instrada le chiamate per un sistema IP-PBX in cui la route termina in un sito derivato, in quanto è necessario più tempo per il completamento dei segnali. Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.

Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.

<div>


> [!NOTE]  
> Per migliorare le prestazioni dei supporti di Mediation Server autonomo, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete su questi server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere la sezione relativa ai miglioramenti della scala di ricezione in Windows <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>server all'indirizzo. Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

