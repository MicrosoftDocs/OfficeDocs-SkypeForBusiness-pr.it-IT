---
title: 'Lync Server 2013: singola pagina perimetrale consolidata con indirizzi IP privati e NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a798269bf2cd261b6304b5379bfe4fb0852b3716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Se l'organizzazione richiede supporto per meno di 15.000 connessioni client del servizio Access Edge, 1.000 le connessioni client Active Lync Server Web Conferencing Service e 500 sessioni A/V Edge simultanee e la disponibilità elevata del server perimetrale non è importante, questa topologia offre i vantaggi del costo hardware inferiore e la distribuzione più semplice. Se si desidera una maggiore capacità o disponibilità, è necessario distribuire la topologia perimetrale consolidata con scalabilità implementata. Per informazioni dettagliate, vedere uno degli argomenti seguenti:

  - <span></span>  
    [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

**Topologia perimetrale consolidata su un solo computer**

![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> Se si utilizza il controllo di ammissione di chiamata, è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale. Questo servizio infatti si basa sugli indirizzi IPv4 e deve disporre di tali indirizzi per funzionare correttamente.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

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

