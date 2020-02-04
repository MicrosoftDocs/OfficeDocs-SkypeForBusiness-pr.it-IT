---
title: 'Lync Server 2013: Panoramica del trunking SIP'
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
ms.openlocfilehash: 340c27b3e874ea3d9f55aac2b415bd1a440aab9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Panoramica del trunking SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

La distribuzione del trunking SIP può essere un grande passo verso la semplificazione delle telecomunicazioni dell'organizzazione e la preparazione di miglioramenti aggiornati alle comunicazioni in tempo reale. Uno dei vantaggi principali del trunking SIP è che puoi consolidare le connessioni dell'organizzazione con la rete PSTN (Public Switched Telephone Network) in un sito centrale, in contrapposizione al suo predecessore, il trunking di Time Division Multiplexing (TDM), che in genere richiede un trunk separato da ogni sito di succursale.

<div>

## <a name="sip-trunking-in-lync-server"></a>Trunking SIP in Lync Server

Le funzionalità di trunking SIP di Lync Server 2013 consentono le operazioni seguenti:

  - Un utente aziendale, sia all'interno che all'esterno del firewall aziendale, può effettuare una chiamata locale o una chiamata a lunga distanza specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.

  - Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct Interior Dialing) associato all'utente aziendale.

</div>

<div>

## <a name="cost-savings"></a>Risparmi sui costi

Il risparmio di costi associato al trunking SIP può essere sostanziale:

  - Le chiamate interurbane in genere costano molto meno attraverso un trunk SIP.

  - È possibile tagliare i costi di gestibilità e ridurre la complessità della distribuzione.

  - Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al proprio ITSP a costi decisamente più bassi. In TDM trunking i provider di servizi caricano le chiamate al minuto. Il costo del trunking SIP può essere basato sull'utilizzo della larghezza di banda, che è possibile acquistare in incrementi più piccoli e più economici. Il costo effettivo dipende dal modello di servizio della ITSP scelta.

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Trunking SIP e hosting di un gateway PSTN o IP-PBX

Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN e i costi e la complessità della gestione. L'uso di un trunk SIP può determinare un notevole risparmio di costi tramite la riduzione della manutenzione e dell'amministrazione.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Servizi VoIP espansi

Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio. Con il trunking SIP è possibile estendere le funzionalità VoIP e consentire a Lync Server 2013 di offrire un set di servizi più completo. Ad esempio:

  - Il rilevamento della presenza avanzata per i dispositivi che non esegue Lync Server 2013 può offrire una migliore integrazione con i telefoni cellulari, consentendo di verificare quando un utente si trova in una chiamata telefonica mobile.

  - La chiamata di emergenza E9-1-1 consente alle autorità che rispondono alle chiamate di 911 di determinare la posizione del chiamante dal proprio numero di telefono.

<div>


> [!NOTE]  
> Contattare l'ITSP per un elenco dei servizi supportati e che possono essere abilitati per l'organizzazione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

