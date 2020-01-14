---
title: 'Lync Server 2013: Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0650e156dca03ac5024dfe4f3045a0d8f155643
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Nella topologia del pool di Edge Server due o più Edge Server vengono distribuiti come pool con bilanciamento del carico nella rete perimetrale del Data Center. Il bilanciamento del carico DNS (Domain Name System) viene usato per il traffico sia per le interfacce esterne che per quelle interne.

Se l'organizzazione richiede il supporto per più di 15.000 connessioni client del servizio Edge di Access, le connessioni client del servizio Web di servizi di conferenza Active Lync Server di 1.000 o le sessioni A/V Edge di 500 simultanee e/o l'elevata disponibilità del server perimetrale sono importanti, questa topologia offre i vantaggi della scalabilità e del supporto per il failover.

La figura non Mostra gli amministratori, un ruolo facoltativo del server distribuito nella rete interna tra i server Edge e i pool o il server front-end. Per informazioni dettagliate sulla topologia di Director, vedere [componenti necessari per il Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figura rappresenta un singolo proxy inverso.

<div>


> [!NOTE]  
> La figura mostrata riguarda l'orientamento e l'indirizzo IP di esempio, ma non intende rappresentare flussi di comunicazione effettivi con il traffico in entrata e in uscita corretto. La figura rappresenta una visualizzazione di alto livello del traffico possibile. I dettagli relativi al flusso di traffico in ingresso (alle porte in ascolto) e in uscita (per i server o i client di destinazione) sono rappresentati nel diagramma di riepilogo della porta in ogni scenario. Ad esempio, TCP 443 è effettivamente in ingresso (al proxy Edge o reverse) solo ed è solo un flusso bidirezionale da una prospettiva di protocollo (TCP). Inoltre, la figura mostra la natura del traffico che cambia quando si verifica NAT (Network Address Translation) (l'indirizzo di destinazione viene modificato in ingresso, l'indirizzo di origine viene modificato in uscita). Ad esempio, i firewall esterni e interni e le interfacce server vengono visualizzati solo per scopi di riferimento. Infine, se necessario, vengono mostrati i rapporti di gateway e route predefiniti di esempio. Si noti inoltre che il diagramma usa la zona DNS <EM>. com</EM> per rappresentare la zona DNS esterna sia per il proxy inverso che per i server perimetrali e la zona DNS <EM>.NET</EM> si riferisce alla zona DNS interna.



</div>

Una novità di Microsoft Lync Server 2013 è il supporto per l'indirizzamento IPv6. Analogamente all'indirizzamento IPv4, gli indirizzi IPv6 devono essere assegnati in modo che gli indirizzi facciano parte dello spazio degli indirizzi IPv6 assegnato. Gli indirizzi in questo argomento sono ad esempio solo. Devi acquisire gli indirizzi IPv6 che funzioneranno nella distribuzione, specificare l'ambito corretto e interagire con l'indirizzamento interno ed esterno. Windows Server offre una caratteristica importante per l'operazione di transizione IPv6 e la comunicazione IPv4-IPv6 chiamata *dual stack*. Lo stack duale è uno stack di rete distinto per IPv4 e per IPv6. Lo stack duale consente di assegnare contemporaneamente l'indirizzo per IPv4 e IPv6 e consente al server di comunicare con altri host e client in base alle proprie esigenze.

I tipi di indirizzo tipici che verranno usati per l'indirizzamento IPv6 saranno gli indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e i collegamenti IPv6-indirizzi locali (in modo simile all'IP privato automatico indirizzi in Windows Server per IPv4)

Esistono le tecnologie NAT (Network Address Translation Technologies) per IPv6 che consentiranno l'uso di NAT IPv6 per IPv4 (comunemente indicato come NAT64) e per NAT IPv6 to IPv6 (comunemente denominato NAT66). L'esistenza di tecnologie NAT indica che i cinque scenari presentati per Lync Server Edge Server sono ancora validi.

<div>


> [!WARNING]  
> IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarsi che gli indirizzi assegnati a livello di Windows Server e a livello di Lync Server 2013 funzionino come previsto. Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6.



</div>

![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")

<div>


> [!IMPORTANT]  
> Se si usa il controllo di ammissione chiamata (CAC), è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale. CAC usa gli indirizzi IPv4 e deve renderli disponibili per l'uso.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

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

