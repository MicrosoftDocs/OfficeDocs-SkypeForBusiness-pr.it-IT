---
title: 'Lync Server 2013: Componenti e topologie per il trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Componenti e topologie per il trunking SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Nella figura seguente viene illustrata la topologia di trunking SIP in Lync Server.

**Topologia di trunking SIP**

(images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia di trunking") SIP ![topologia]trunking SIP

Come illustrato nel diagramma, per la connettività tra la rete aziendale e il provider di servizi PSTN (Public Switched Telephone Network) viene usata una rete privata virtuale IP (VPN). Lo scopo di questa rete privata è offrire connettività IP, migliorare la sicurezza e, facoltativamente, ottenere garanzie di qualità del servizio (QoS). A causa della natura di una VPN, non è necessario usare Transport Layer Security (TLS) per il traffico di segnalazione SIP o il protocollo di trasporto in tempo reale (SRTP) sicuro per il traffico multimediale. Le connessioni tra l'organizzazione e il provider di servizi sono quindi costituite da connessioni TCP semplici per SIP e per il protocollo RTP (Plain Real-Time Transport Protocol) (tramite UDP) per i contenuti multimediali tramite una rete VPN IP. Assicurarsi che tutti i firewall tra i router VPN dispongano delle porte aperte per consentire ai router VPN di comunicare e che gli indirizzi IP sui bordi esterni dei router VPN siano instradabili pubblicamente.

<div>


> [!IMPORTANT]  
> Contattare il provider di servizi per determinare se fornisce il supporto per l'elevata disponibilità, incluso il failover. In caso affermativo, dovrai determinare le procedure per configurarlo. Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP in ogni Mediation Server oppure è necessario configurare più trunk SIP in ogni Mediation Server?<BR>Se si hanno più siti centrali, chiedere anche se il provider di servizi ha la possibilità di abilitare le connessioni da e verso un altro sito centrale.



</div>

<div>


> [!NOTE]  
> Per il trunking SIP consigliamo vivamente di distribuire server di mediazione autonomi. Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Protezione del server Mediation per il trunking SIP

Per motivi di sicurezza, è necessario configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN. Il processo effettivo per la configurazione di una VLAN varia da un produttore di router a un altro. Per informazioni dettagliate, contattare il fornitore del router.

Ti consigliamo di seguire queste linee guida:

  - Configurare una LAN virtuale (VLAN) tra il Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).

  - Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.

  - Bloccare le regole di routing che instradano il traffico dal router a un punto qualsiasi ma al Mediation Server.

Se si usa un server VPN, è consigliabile seguire queste linee guida:

  - Configurare una VLAN tra il server VPN e il Mediation Server.

  - Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.

  - Bloccare qualsiasi regola di routing che instrada il traffico del server VPN ovunque, eccetto il Mediation Server.

  - Crittografare i dati nella rete VPN usando Generic Routing Encapsulation (GRE).

</div>

</div>

<span> </span>

</div>

</div>

</div>

