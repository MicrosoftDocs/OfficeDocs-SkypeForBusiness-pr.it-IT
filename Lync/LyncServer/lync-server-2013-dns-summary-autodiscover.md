---
title: 'Lync Server 2013: Sommario DNS-individuazione automatica'
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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Riepilogo DNS-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-13_

L'individuazione automatica è un servizio flessibile in quanto accetterà la comunicazione tramite HTTP o HTTPS. A tale scopo, il DNS (Domain Name System) e i certificati usati dai server che ospitano il servizio di individuazione automatica devono essere configurati correttamente. I requisiti di certificato sono inclusi nel [Riepilogo dei certificati-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La logica di ricerca DNS per i client di Lync Server usa un ordine di risoluzione specifico. Dovresti sempre includere sia LyncdiscoverInternal. &lt;domain&gt; e lyncdiscover. &lt;dominio&gt; nel DNS. Escludendo il LyncdiscoverInternal. &lt;il&gt; record di dominio indurrà i client interni a non connettersi ai servizi previsti o a ricevere la risposta di individuazione automatica errata.



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
<th>Risolve in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt;nome di dominio interno&gt;</p></td>
<td><p>FQDN dei servizi Web interni per il pool di Director, se è presente oppure per il pool di front-end se non si dispone di un amministratore.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;nome di dominio interno&gt;</p></td>
<td><p>Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si usa un servizio di bilanciamento del carico del pool di Director, se si ha uno o del pool di front-end se non si ha un amministratore.</p></td>
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
<th>Risolve in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>FQDN dei servizi Web esterni per il pool di Director, se è presente oppure per il pool di front-end se non si ha un amministratore.</p></td>
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
> I client di dispositivi mobili non supportano più certificati SSL (Secure Sockets Layer) provenienti da domini diversi. Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato su HTTPS. Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che reindirizza a un indirizzo di director.contoso.net non è supportato tramite HTTPS. In tale topologia, un client di dispositivi mobili deve usare HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto tramite HTTP. Le richieste successive usano HTTPS. Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP). Per informazioni dettagliate, vedere "per creare una regola di pubblicazione Web per la porta 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per la mobilità in Lync Server 2013</A>. Il reindirizzamento CNAME allo stesso dominio è supportato tramite HTTPS. In questo caso, il certificato del dominio di destinazione copre il dominio di origine.



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

