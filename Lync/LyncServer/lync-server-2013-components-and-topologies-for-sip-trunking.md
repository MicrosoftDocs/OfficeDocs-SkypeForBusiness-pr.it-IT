---
title: 'Lync Server 2013: componenti e topologie per il trunking SIP'
description: 'Lync Server 2013: componenti e topologie per il trunking SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549522"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Componenti e topologie per il trunking SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Nella figura seguente viene illustrata la topologia di trunking SIP in Lync Server.

**Topologia di trunking SIP**

![Topologia del trunking SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia del trunking SIP")

Come illustrato nella figura, una rete privata virtuale (VPN, Virtual Private Network) IP viene utilizzata per la connettività tra l'azienda e il provider di servizi PSTN. Lo scopo di questa rete privata è quello di fornire connettività IP, migliorare la protezione e, facoltativamente, ottenere garanzie relative alla qualità del servizio. Data la natura delle VPN, non è necessario utilizzare TLS per il traffico di segnalazione SIP o SRTP per il traffico multimediale. Le connessioni tra l'azienda e il provider di servizi sono pertanto normali connessioni TCP per SIP e RTP (tramite UDP) per i contenuti multimediali potenzialmente inviati tramite una rete VPN IP. Accertarsi che le porte di tutti i firewall tra i router VPN siano aperte per consentire ai router VPN di comunicare e che gli indirizzi IP nei perimetri esterni dei router VPN consentano l'esecuzione del routing pubblicamente.

<div>


> [!IMPORTANT]  
> Contattare il provider di servizi per determinare se fornisce supporto per la disponibilità elevata, incluso il failover. In tal caso, sarà necessario determinare le procedure per configurarlo. Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP su ogni Mediation Server oppure è necessario configurare più trunk SIP su ogni Mediation Server?<BR>Se si dispone di più siti centrali, chiedere anche se il provider di servizi ha la possibilità di abilitare le connessioni da e verso un altro sito centrale.



</div>

<div>


> [!NOTE]  
> Per il trunking SIP, è consigliabile distribuire i Mediation Server autonomi. Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and define Peers in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Protezione del Mediation Server per il trunking SIP

Per motivi di sicurezza è opportuno configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN. La procedura per la configurazione di una VLAN varia in base al produttore del router. Per informazioni dettagliate, rivolgersi al fornitore del router.

È consigliabile attenersi alle linee guida seguenti:

  - Configurare una LAN virtuale (VLAN) tra il Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, area demilitarizzata e subnet schermata).

  - Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.

  - Bloccare tutte le regole di routing che instradano il traffico dal router a Anywhere but Mediation Server.

Se si utilizza un server VPN, è consigliabile attenersi alle linee guida seguenti:

  - Configurare una VLAN tra il server VPN e il Mediation Server.

  - Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.

  - Blocca tutte le regole di routing che instradano il traffico del server VPN ovunque tranne il Mediation Server.

  - Crittografare i dati sulla VPN utilizzando Generic Routing Encapsulation (GRE).

</div>

</div>

<span> </span>

</div>

</div>

</div>

