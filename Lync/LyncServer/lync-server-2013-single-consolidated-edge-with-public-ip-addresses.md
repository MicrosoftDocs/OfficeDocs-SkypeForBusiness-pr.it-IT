---
title: 'Lync Server 2013: Singola topologia perimetrale consolidata con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf6655c596be657d1779a404c6f1f5b108f3251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Se l'organizzazione ha bisogno del supporto per meno di 15.000 connessioni client del servizio Edge di Access, le connessioni client del servizio Web di servizi di conferenza Active Lync Server di 1.000 500 e le sessioni contemporanee A/V Edge e la disponibilità elevata di Edge Server non sono importanti, questa topologia offre i vantaggi del costo hardware più basso e della distribuzione più semplice. Se è necessaria una maggiore capacità o è necessaria una disponibilità elevata, è necessario distribuire una topologia di Edge Server consolidato in scala.

  - <span></span>  
    [Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> Quando si usa l'indirizzo IP pubblico nell'Edge Server, il gateway predefinito nel server perimetrale non è più il firewall o il router, ma il router o il firewall a bordo del perimetro pubblico, che sarà un indirizzo pubblico. Il proxy inverso continua a usare il router o il firewall associato alla rete perimetrale più esterna. La differenza tra il proxy inverso e il server perimetrale con indirizzi IP pubblici è che il proxy inverso sta ancora usando NAT e il server perimetrale usa una relazione di route.



</div>

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

**Singolo bordo consolidato con topologia indirizzi IP pubblici**

![2db9f9e1-75aa-4DE0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4DE0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> Se si usa il controllo di ammissione chiamata (CAC), è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale. CAC usa gli indirizzi IPv4 e deve renderli disponibili per l'uso.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Riepilogo di DNS - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

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

