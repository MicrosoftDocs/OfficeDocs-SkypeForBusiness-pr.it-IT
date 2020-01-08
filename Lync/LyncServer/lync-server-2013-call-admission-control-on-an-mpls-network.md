---
title: 'Lync Server 2013: controllo di ammissione di chiamata in una rete MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee138a0f61bace067db12c9df4f06338aa13ac8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a>Controllo di ammissione alle chiamate in una rete MPLS con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

In una rete di commutazione di etichette Multiprotocol (MPLS), tutti i siti sono connessi da una mesh completa. Ossia, tutti i siti sono connessi direttamente alla backbone MPLS del provider di servizi Internet e ogni sito è il provisioning della larghezza di banda da usare in un collegamento WAN al cloud MPLS. Non esiste un hub di rete o un sito centrale per controllare il routing IP. La figura seguente mostra una rete semplice basata sulla tecnologia MPLS.

**Esempio di rete MPLS**

![CAC con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC con MPLS")

Per distribuire il controllo di ammissione di chiamata (CAC) in una rete MPLS, è possibile creare un'area di rete per rappresentare il cloud MPLS e creare un sito di rete per rappresentare ogni sito satellite MPLS. Nella figura seguente viene illustrato il modo in cui i siti della rete e della rete devono essere configurati per rappresentare la rete MPLS di esempio nella figura precedente. I limiti generali della larghezza di banda e i limiti della sessione di larghezza di banda si basano sulla capacità del collegamento WAN da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.

**Area geografica e siti di rete per una rete MPLS**

![Controllo di ammissione alle chiamate (CAC) con]il controllo di ammissione al diagramma MPLS(images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "(CAC) con il diagramma MPLS")

</div>

<span> </span>

</div>

</div>

</div>

