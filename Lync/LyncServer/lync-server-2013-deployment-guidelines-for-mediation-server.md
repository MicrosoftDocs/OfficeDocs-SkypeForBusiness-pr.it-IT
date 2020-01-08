---
title: 'Lync Server 2013: linee guida per la distribuzione di Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Linee guida per la distribuzione di Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-12_

Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server. Dopo aver rivisto queste linee guida, è consigliabile usare lo strumento di pianificazione per creare e visualizzare le possibili topologie alternative, che possono essere usate come modelli per l'aspetto della topologia sartoriale finale che si decide di distribuire.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Mediation Server collocato o autonomo?

Mediation Server è collocato per impostazione predefinita nel server Standard Edition o front end server in un pool Front-end presso i siti centrali. Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderà dalle operazioni seguenti:

  - Numero di peer gateway che il pool di Mediation Server controlla

  - I periodi di traffico ad alto volume tramite questi gateway

  - Percentuale di chiamate che vengono chiamate il cui elemento multimediale ignora il Mediation Server

Durante la pianificazione, assicurati di tenere conto dei requisiti per l'elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V non configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario occupato che devono essere supportate. Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server; i gateway PSTN, IP-PBX e SBCs dovranno essere divisi in subset controllati dai server di mediazione collocati in un pool e i Mediation Server autonomi in uno o più pool autonomi.

Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di server di mediazione, inclusi i seguenti, sarà necessario associarli a un pool autonomo costituito da di un singolo Mediation Server:

  - Eseguire il bilanciamento del carico DNS (Network layer Domain Name System) in Mediation Servers in un pool (o in caso contrario instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)

  - Accettare il traffico da qualsiasi Mediation Server in un pool

È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione di Mediation Server con il pool Front-end può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Considerazioni sul sito centrale e sulla filiale

I Mediation Server nel sito centrale possono essere usati per instradare le chiamate per i PBX IP o i gateway PSTN nei siti di succursale. Se si distribuiscono trunk SIP, tuttavia, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina. L'uso di un Mediation Server presso la route del sito centrale richiede un gateway IP-PBX o PSTN presso un sito di succursale non richiede l'utilizzo di bypass multimediale. Tuttavia, se è possibile abilitare il bypass multimediale, in questo modo si ridurrà la latenza del percorso multimediale e, di conseguenza, si tradurrebbe in una qualità multimediale migliorata perché il percorso del supporto non è più necessario per seguire il percorso di segnalazione. Il bypass multimediale ridurrà anche il carico di elaborazione nel pool.

<div>


> [!NOTE]  
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>at.



</div>

Se è necessaria la resilienza del sito di succursale, è necessario distribuire un Survivable Branch Appliance o una combinazione di un server front-end, un Mediation Server e un gateway nel sito della filiale. Il presupposto con la resilienza del sito di succursale è che la presenza e i servizi di conferenza non sono resilienti nel sito. Per indicazioni sulla pianificazione del sito di succursale per la voce, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e interazioni RFC 3960, può essere possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo da IP-PBX agli endpoint di Lync. Questo comportamento può essere più grave se un Mediation Server presso un sito centrale sta instradando le chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione. Se si verifica questo comportamento, la distribuzione di un Mediation Server presso il sito della filiale è l'unico modo per ridurre il ritaglio delle prime parole.

Infine, se il sito centrale ha un PBX TDM o se il tuo IP-PBX non elimina la necessità di un gateway PSTN, devi distribuire un gateway sulla route di chiamata che connette Mediation Server e il PBX.

<div>


> [!NOTE]  
> Per migliorare le prestazioni multimediali di Mediation Server autonomo, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete in questi server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "miglioramenti al ridimensionamento sul lato ricezione in Windows Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>" all'indirizzo. Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

