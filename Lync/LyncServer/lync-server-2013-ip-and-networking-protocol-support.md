---
title: 'Lync Server 2013: supporto del protocollo di rete e IP'
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
ms.openlocfilehash: ea7312cff97b6c339d960c14902e912f6e2e7bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Supporto del protocollo di rete e IP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Lync Server 2013 supporta i protocolli IP e di rete seguenti:

  - **Protocolli IP.**    Lync Server 2013 supporta IP versione 4 (IPv4) o IP versione 6 (IPv6) per la rete del server.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 può funzionare in una rete con doppio stack IP abilitato.

    
    </div>

  - **Protocolli di trasporto SIP.**    A livello generico, SIP può utilizzare almeno tre tipi di trasporto: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) e TLS (Transport Layer Security). Nella configurazione di trasporto SIP predefinita, TLS viene eseguito su TCP. TLS viene utilizzato all'interno della rete Lync Server 2013. Nel perimetro della rete, Lync Server 2013 può interoperare su TCP. Lync Server 2013 non supporta UDP per il trasporto SIP perché non soddisfa gli standard minimi per la sicurezza delle comunicazioni aziendali, l'affidabilità e la scalabilità. Per informazioni dettagliate, vedere l'articolo del Blog di NextHop, "per UDP o non UDP, ovvero la domanda" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).
    
    <div>
    

    > [!NOTE]  
    > Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

