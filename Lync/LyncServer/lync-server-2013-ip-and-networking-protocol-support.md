---
title: 'Lync Server 2013: Supporto del protocollo di rete e IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Supporto del protocollo di rete e IP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Lync Server 2013 supporta i protocolli IP e di rete seguenti:

  - **Protocolli IP.**    Lync Server 2013 supporta IP versione 4 (IPv4) o IP versione 6 (IPv6) per la rete del server.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 può funzionare in una rete con lo stack Dual IP abilitato.

    
    </div>

  - **Protocolli di trasporto SIP.**    In genere, SIP può usare almeno tre tipi di trasporto: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) e Transport Layer Security (TLS). Nella configurazione predefinita del trasporto SIP, TLS viene eseguito su TCP. TLS viene usato nella rete Lync Server 2013. Sul bordo della rete, Lync Server 2013 può interagire con TCP. Lync Server 2013 non supporta UDP per il trasporto SIP perché non soddisfa gli standard minimi per la sicurezza, l'affidabilità e la scalabilità delle comunicazioni aziendali. Per informazioni dettagliate, vedere l'articolo su Blog di NextHop, "per UDP o non UDP, che è la domanda" [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).
    
    <div>
    

    > [!NOTE]  
    > Il contenuto di ogni blog e il relativo URL sono soggetti a modifiche senza preavviso.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

