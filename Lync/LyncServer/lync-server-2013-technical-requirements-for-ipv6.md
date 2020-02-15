---
title: Lync Server 2013 requisiti tecnici per IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e0d822e14ea1792751338bd3606766cc98ab96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Requisiti tecnici per IPv6 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

Se si prevede di configurare Lync Server 2013 per IPv6, tenere presente quanto segue:

  - Per utilizzare gli indirizzi IPv6 con Lync Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6. Il DNS IPv6 utilizza record AAAA (A quadrupla) dell'host. Se si utilizzano entrambi gli indirizzamenti IPv4 e IPv6 nella distribuzione, è consigliabile configurare e gestire sia i record A dell'host per IPv4 che i record AAAA dell'host per IPv6. Anche in caso di transizione completa della distribuzione a IPv6, è possibile che siano comunque necessari record dell'host DNS IPv4 per gli utenti esterni che continuano a utilizzare IPv4.
    
    È possibile distribuire record DNS IPv6 prima di iniziare a utilizzare IPv6. Se il client o il server non utilizza IPv6, il record non verrà utilizzato come riferimento. Le tecnologie transitorie sceglieranno quale record utilizzare in base alla configurazione e ai criteri della tecnologia.

  - Ogni indirizzo IPv6 prevede un ambito. I tre ambiti che è possibile utilizzare per l'indirizzamento IPv6 sono gli indirizzi globali IPv6 (simili agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (simili agli intervalli di indirizzi IPv4 privati) e gli indirizzi del collegamento IPv6 (simili agli indirizzi IP privati automatici in Windows Server per IPv4). Tutti i server di un pool devono disporre di indirizzi IPv6 con lo stesso ambito.

<div>


> [!IMPORTANT]  
> IPv6 è un argomento complesso che richiede una pianificazione accurata con il team di rete e il provider di servizi Internet per garantire che gli indirizzi assegnati a livello di Windows Server e al livello di Lync Server 2013 funzionino come previsto. Vedere i collegamenti alla fine dell'argomento per risorse aggiuntive sull'indirizzamento IPv6 e la pianificazione.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Architettura di indirizzamento IP versione 6](http://tools.ietf.org/html/rfc4291)  
[Formato di indirizzo unicast globale IPv6](http://tools.ietf.org/html/rfc3587)  
[Indirizzi unicast IPv6 locali univoci](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

