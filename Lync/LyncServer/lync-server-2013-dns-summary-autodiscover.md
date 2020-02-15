---
title: 'Lync Server 2013: Riepilogo DNS-individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236a3625b755697580e57c926dd5714a44c0347f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Riepilogo DNS-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-13_

L'individuazione automatica è un servizio flessibile che accetterà la comunicazione tramite HTTP o HTTPS. A tale scopo, il DNS (Domain Name System) e i certificati utilizzati dai server che ospitano il servizio di individuazione automatica devono essere configurati correttamente. I requisiti dei certificati sono descritti in [Riepilogo dei certificati-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La logica di ricerca DNS per i client di Lync Server utilizza un ordine di risoluzione specifico. È necessario includere sempre entrambi gli LyncdiscoverInternal. &lt;domain&gt; e lyncdiscover. &lt;dominio&gt; nel DNS. Esclusione di LyncdiscoverInternal. &lt;il&gt; record di dominio causerà la mancata connessione dei client interni ai servizi previsti o la ricezione della risposta di individuazione automatica errata.



</div>

### <a name="internal-dns-records"></a>Record DNS interni

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di record</th>
<th>Nome host</th>
<th>Viene risolto in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
<td><p>FQDN dei servizi Web interni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
<td><p>Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si utilizza un servizio di bilanciamento del carico) del pool di server Director, se si dispone di uno o del pool Front End, se non si dispone di un Director.</p></td>
</tr>
</tbody>
</table>


È necessario creare uno dei record DNS esterni seguenti:

### <a name="external-dns-records"></a>Record DNS esterni

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di record</th>
<th>Nome host</th>
<th>Viene risolto in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>FQDN dei servizi Web esterni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>Lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>Indirizzo IP esterno o pubblico del proxy inverso.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Il traffico esterno passa attraverso il proxy inverso.



</div>

<div>


> [!NOTE]  
> I client dei dispositivi mobili non supportano certificati SSL (Secure Sockets Layer) multipli da domini diversi. Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato in HTTPS. Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che esegue il reindirizzamento a un indirizzo director.contoso.net non è supportato in HTTPS. In una topologia di questo tipo, un client di dispositivo portatile deve utilizzare il protocollo HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto in HTTP. Per le richieste successive viene quindi utilizzato HTTPS. Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP). Per informazioni dettagliate, vedere la sezione relativa alla creazione di una regola di pubblicazione Web per la porta 80 in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</A>. Il reindirizzamento CNAME allo stesso dominio è supportato in HTTPS. In questo caso, il certificato del dominio di destinazione copre il dominio di origine.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Riepilogo del certificato-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

