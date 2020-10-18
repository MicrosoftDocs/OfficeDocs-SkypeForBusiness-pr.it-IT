---
title: 'Lync Server 2013: Panoramica del trunking SIP'
description: 'Lync Server 2013: Panoramica del trunking SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6132cc16d8aaeee4b27355ea8676672a0a5df93d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577262"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Panoramica del trunking SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

La distribuzione del trunking SIP può costituire un importante passo verso la semplificazione delle telecomunicazioni nella propria organizzazione e per prepararsi agli ultimi aggiornamenti relativi alle comunicazioni in tempo reale. Uno dei principali vantaggi del trunking SIP è rappresentato dalla possibilità di consolidare le connessioni dell'organizzazione alla rete PSTN (public switched telephone network) presso un sito centrale, mentre il relativo predecessore, il trunking TDM (time division multiplexing) in genere richiede un trunk separato per ogni sito derivato.

<div>

## <a name="sip-trunking-in-lync-server"></a>Trunking SIP in Lync Server

Le funzionalità di trunking SIP di Lync Server 2013 consentono di:

  - Un utente Enterprise all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero compatibile con E.164 che viene terminata sulla rete PSTN come servizio del provider di servizi corrispondente.

  - Qualsiasi sottoscrittore PSTN può contattare un utente Enterprise all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct Inward Dialing) associato all'utente Enterprise.

</div>

<div>

## <a name="cost-savings"></a>Risparmi sui costi

I risparmi sui costi associati al trunking SIP possono essere significativi:

  - Le chiamate interurbane in genere sono molto meno costose tramite un trunk SIP.

  - È possibile tagliare i costi di gestione e ridurre la complessità della distribuzione.

  - Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al provider di servizi di telefonia Internet (ITSP) con un costo significativamente inferiore. Nel trunking TDM i provider di servizi applicano alle chiamate una tariffa al minuto. Il costo del trunking SIP può basarsi sull'utilizzo della larghezza di banda, che può essere acquistato con incrementi inferiori, più economici. Il costo effettivo dipende dal modello di servizio dell'ITSP scelto.

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Confronto tra trunking SIP e hosting di un gateway PSTN o di un sistema IP-PBX

Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN con relativa complessità e con i costi di gestione a essi associati. L'utilizzo di un trunk SIP può determinare significativi risparmi sui costi grazie a una riduzione delle attività di manutenzione e amministrazione.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Servizi VoIP estesi

Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio. Con il trunking SIP, è possibile estendere le funzionalità VoIP e consentire a Lync Server 2013 di fornire un set di servizi più completo. Ad esempio:

  - Il rilevamento della presenza avanzata per i dispositivi che non eseguono Lync Server 2013 è in grado di offrire una migliore integrazione con i telefoni cellulari, consentendo di vedere quando un utente è su una chiamata di telefonia mobile.

  - La funzionalità per le chiamate di emergenza E9-1-1 consente alle autorità che rispondono a tali chiamate di determinare il luogo da cui proviene la chiamata dal numero di telefono.

<div>


> [!NOTE]  
> Contattare il provider di servizi Internet per un elenco dei servizi supportati e che possono essere abilitati per la propria organizzazione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

