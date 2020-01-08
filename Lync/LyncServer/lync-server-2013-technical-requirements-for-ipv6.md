---
title: 'Lync Server 2013: Requisiti tecnici per IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Requisiti tecnici per IPv6 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

Se si prevede di configurare Lync Server 2013 per IPv6, tieni presente quanto segue:

  - Per usare gli indirizzi IPv6 con Lync Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6. DNS IPv6 usa record AAAA (Quad-A) host. Se si usano sia IPv4 che IPv6 nella distribuzione, è consigliabile configurare e gestire sia l'host di un record per IPv4 che i record AAAA host per IPv6. Anche quando si passa completamente la distribuzione a IPv6, è possibile che siano ancora necessari record host DNS IPv4 per gli utenti esterni che usano ancora IPv4.
    
    È possibile distribuire record host DNS IPv6 prima di iniziare a usare IPv6. Se il client o il server non usa IPv6, non verrà fatto riferimento al record. Le tecnologie di transizione consentiranno di decidere quale record usare, in base alla configurazione e ai criteri di tecnologia di transizione.

  - Ogni indirizzo IPv6 ha un ambito. I tre ambiti che è possibile usare per l'indirizzamento IPv6 sono indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), indirizzi locali univoci di IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e indirizzi locali del collegamento IPv6 (in modo simile agli indirizzi IP privati automatici in Windows Server per IPv4). Tutti i server all'interno di un pool devono avere indirizzi IPv6 con lo stesso ambito.

<div>


> [!IMPORTANT]  
> IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarti che gli indirizzi assegnati a livello di Windows Server e a livello di Lync Server 2013 funzionino come previsto. Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6.



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

