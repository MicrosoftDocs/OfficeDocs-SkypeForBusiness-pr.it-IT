---
title: 'Lync Server 2013: singola pagina perimetrale consolidata con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3dbf838d9a25f0be0d8399f6327c2d442092b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Se l'organizzazione ha bisogno di supporto per meno di 15.000 connessioni client del servizio Access Edge, 1.000 le connessioni client Active Lync Server Web Conferencing Service e 500 sessioni A/V Edge simultanee e la disponibilità elevata del server perimetrale non è importante, questa topologia offre i vantaggi del costo hardware inferiore e la distribuzione più semplice. Se si desidera una maggiore capacità o disponibilità, è consigliabile distribuire una topologia di server perimetrale consolidata con scalabilità implementata.

  - <span></span>  
    [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> Quando si utilizza l'indirizzo IP pubblico nel server perimetrale, il gateway predefinito sul server perimetrale non è più il firewall o il router, ma il router o il firewall al perimetro pubblico (che sarà un indirizzo pubblico). Il proxy inverso continua a utilizzare il router o il firewall associato alla rete perimetrale più esterna. La differenza tra il proxy inverso e il server perimetrale con indirizzi IP pubblici è che il proxy inverso sta ancora utilizzando NAT e il server perimetrale utilizza una relazione di route.



</div>

Nella figura non sono visualizzati i direttori, un ruolo del server facoltativo distribuito nella rete interna tra i server perimetrali e i pool o il server front end. Per informazioni dettagliate sulla topologia per i Director, vedere [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md). Nella figura è rappresentato un singolo proxy inverso.

<div>


> [!NOTE]  
> La figura mostrata è indicativa e include indirizzi IP di esempio, ma non deve essere interpretata come reale rappresentazione dei flussi di comunicazioni effettivi con un'indicazione corretta del traffico in entrata e in uscita. La figura rappresenta una visualizzazione di livello generale del traffico possibile. Le informazioni dettagliate sul flusso di traffico in entrata (verso le porte di attesa ) e in uscita (verso server o client di destinazione) vengono fornite nel diagramma di riepilogo delle porte in ogni scenario. La porta TCP 443 ad esempio è in realtà dedicata solo al traffico in entrata (verso il server perimetrale o il proxy inverso) e rappresenta un flusso bidirezionale solo dal punto di vista del protocollo (TCP). Nella figura inoltre viene mostrata la natura del traffico con le modifiche implementate con il processo NAT (Network Address Translation), ovvero l'indirizzo di destinazione diventa indirizzo in ingresso e quello di origine diventa indirizzo in uscita. Vengono mostrati inoltre solo come riferimento esempi di firewall interni ed esterni e di interfacce server. Vengono forniti anche esempi delle relazioni predefinite tra gateway e ruote, se applicabili. Si noti inoltre che il diagramma utilizza la zona DNS <EM>. com</EM> per rappresentare la zona DNS esterna sia per il proxy inverso sia per i server perimetrali e che la zona DNS <EM>.NET</EM> si riferisce alla zona DNS interna.



</div>

New to Microsoft Lync Server 2013 è il supporto per l'indirizzamento IPv6. Analogamente agli indirizzi IPv4, gli indirizzi IPv6 devono essere assegnati in modo che facciano parte dello spazio degli indirizzi IPv6 assegnato. Gli indirizzi riportati in questo argomento vengono forniti unicamente a scopo esemplificativo. È necessario acquisire indirizzi IPv6 che funzionino nella propria distribuzione, forniscano l'ambito corretto e interagiscano con gli indirizzi interni ed esterni. Windows Server fornisce una caratteristica importante per l'operazione di transizione IPv6 e la comunicazione IPv4-IPv6 chiamata *dual stack*. Il dual stack è uno stack di rete separato e distinto per IPv4 e per IPv6. Consente di assegnare indirizzi per IPv4 e IPv6 simultaneamente e permette al server di comunicare con altri host e client in base ai rispettivi requisiti.

I tipi di indirizzi tipici che verranno utilizzati per l'indirizzamento IPv6 saranno gli indirizzi globali IPv6 (simili agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (simili agli intervalli di indirizzi IPv4 privati) e gli indirizzi IPv6 (simili all'IP privato automatico). indirizzi in Windows Server per IPv4)

Sono disponibili tecnologie NAT (Network Address Translation) per IPv6 che consentono la conversione NAT da IPv6 a IPv4 (denominata comunemente NAT64) e la conversione NAT da IPv6 a IPv6 (denominata comunemente NAT66). L'esistenza di tecnologie NAT significa che i cinque scenari presentati per i server perimetrali di Lync Server sono ancora validi.

<div>


> [!WARNING]  
> IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider di servizi Internet per garantire che gli indirizzi assegnati a livello di Windows Server e al livello di Lync Server 2013 funzionino come previsto. Vedere i collegamenti alla fine dell'argomento per risorse aggiuntive sull'indirizzamento IPv6 e la pianificazione.



</div>

**Topologia perimetrale consolidata singola con indirizzi IP pubblici**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> Se si utilizza il controllo di ammissione di chiamata, è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale. Questo servizio infatti si basa sugli indirizzi IPv4 e deve disporre di tali indirizzi per funzionare correttamente.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Architettura di indirizzamento IP versione 6](https://tools.ietf.org/html/rfc4291)  
[Formato di indirizzo unicast globale IPv6](https://tools.ietf.org/html/rfc3587)  
[Indirizzi unicast IPv6 locali univoci](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

