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
ms.openlocfilehash: 4adf8dcee7ccd7adb393c8d13f7e9a8b186d2bb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519663"
---
# <a name="sip-trunking-in-lync-server-2013"></a>Trunking SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-13_

Il protocollo SIP (Session Initiation Protocol) viene utilizzato per avviare e gestire sessioni di comunicazioni Voice over IP (VoIP) per servizi telefonici di base e per altri servizi di comunicazione in tempo reale, ad esempio messaggistica istantanea, conferenze, informazioni sulla presenza e sessioni multimediali. In questa sezione vengono fornite informazioni sulla pianificazione per l'implementazione di *trunk SIP*, un tipo di connessione SIP che si estende oltre i confini della rete locale.

<div>

## <a name="what-is-sip-trunking"></a>Cos'è il trunking SIP?

Un trunk SIP è una connessione IP che consente di stabilire un collegamento di comunicazione SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall. In genere, un trunk SIP viene utilizzato per connettere il sito centrale dell'organizzazione a un ITSP. In alcuni casi, è anche possibile scegliere di utilizzare il trunking SIP per connettere un sito derivato a un ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Confronto tra trunk SIP e connessioni SIP dirette

Il termine *trunk* deriva dalla tecnologia a commutazione di circuito. Si riferisce a una linea fisica dedicata che collega il dispositivo di commutazione telefonica. Analogamente al predecessore, ai trunk TDM (Time Division Multiplexing), i trunk SIP sono connessioni tra due reti SIP separate, ovvero Lync Server 2013 Enterprise e ITSP. A differenza dei trunk a commutazione di circuito, i trunk SIP sono connessioni virtuali che possono essere stabilite su qualsiasi tipo di connessione di trunking SIP supportato. Per informazioni dettagliate sui tipi di connessione supportati, vedere [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Le connessioni SIP dirette sono invece connessioni SIP che non oltrepassano il confine di rete locale, ovvero si connettono a un gateway PSTN o un PBX nella rete interna. Per informazioni dettagliate su come utilizzare le connessioni SIP dirette con Lync Server 2013, vedere [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Panoramica del trunking SIP in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componenti e topologie per il trunking SIP in Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Trunking SIP del sito di succursale in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Elenco di controllo per la distribuzione del trunk SIP per Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

