---
title: 'Lync Server 2013: trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Trunking SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-13_

SIP (Session Initiation Protocol) viene usato per avviare e gestire sessioni di comunicazioni VoIP (Voice over IP) per il servizio telefonico di base e per servizi di comunicazione in tempo reale aggiuntivi, ad esempio messaggistica istantanea, conferenza, rilevamento presenza e multimediali. Questa sezione fornisce informazioni sulla pianificazione per l'implementazione di *trunk SIP*, un tipo di connessione SIP che si estende oltre il limite della rete locale.

<div>

## <a name="what-is-sip-trunking"></a>Che cos'è il trunking SIP?

Un trunk SIP è una connessione IP che stabilisce un collegamento di comunicazioni SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall. In genere, viene usato un trunk SIP per connettere il sito centrale dell'organizzazione a un ITSP. In alcuni casi, è anche possibile scegliere di usare il trunking SIP per connettere il sito di succursale a un ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Trunk SIP e connessioni SIP dirette

Il termine *trunk* è derivato dalla tecnologia Circuit-Switched. Si riferisce a una linea fisica dedicata che connette il dispositivo di commutazione telefonica. Come il predecessore, i trunk di Time Division Multiplexing (TDM), trunk SIP sono connessioni tra due reti SIP separate: Lync Server 2013 Enterprise e ITSP. Diversamente dai trunk a scambio di circuiti, i trunk SIP sono connessioni virtuali che possono essere stabilite su uno dei tipi di connessione di trunking SIP supportati. Per informazioni dettagliate sui tipi di connessione supportati, vedere [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Le connessioni SIP dirette, invece, sono connessioni SIP che non superano il limite di rete locale, ovvero si connettono a un gateway PSTN (Public Switched Telephone Network) o PBX (Private Branch Exchange) all'interno della rete interna. Per informazioni dettagliate su come usare le connessioni SIP dirette con Lync Server 2013, vedere [connessioni SIP dirette in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Panoramica del trunking SIP in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Come implementare il trunking SIP in Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componenti e topologie per il trunking SIP in Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Trunking SIP del sito della filiale in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Elenco di controllo di distribuzione per i trunk SIP per Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

