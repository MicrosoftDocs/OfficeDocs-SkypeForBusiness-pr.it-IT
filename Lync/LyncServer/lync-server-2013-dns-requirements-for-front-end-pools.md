---
title: 'Lync Server 2013: requisiti DNS per i pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b763f9b01e070fc434dae997bc1e2da68dcbc26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Requisiti DNS per i pool Front-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-07_

Questa sezione descrive i record DNS (Domain Name System) necessari per la distribuzione di pool Front-end.

<div>

## <a name="dns-records-for-front-end-pools"></a>Record DNS per i pool Front-End

Nella tabella seguente sono specificati i requisiti DNS per una distribuzione del pool Front End di Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Requisiti DNS per un pool Front-End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario di distribuzione</th>
<th>Requisito DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool Front end con più server front-end e un servizio di bilanciamento del carico hardware (indipendentemente dal fatto che il bilanciamento del carico DNS sia distribuito anche in tale pool)</p></td>
<td><p>Quando si usano sia il bilanciamento del carico DNS che un servizio di bilanciamento del carico hardware, è necessario ospitare record (A). Creare un record interno che risolva il nome di dominio completo (FQDN) del pool Front-end per il bilanciamento del carico DNS. Creare un record host interno (A) per i servizi Web interni all'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico. È necessario usare il nome servizi Web interni come definito in Generatore di topologie.</p>
<p>Ad esempio, se si usano sia il bilanciamento del carico DNS che il bilanciamento del carico hardware, si avrà un record a per ogni server front-end in un pool per il bilanciamento del carico DNS e un record per i servizi Web interni che puntano all'IP virtuale del servizio di bilanciamento del carico hardware :</p>
<ul>
<li><p>Bilanciamento del carico DNS: Pool01.contoso.net indirizzo IP del pool 10.10.10.5</p>
<div>

> [!WARNING]  
> Ogni server front-end avrà anche un record distinto:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Bilanciamento del carico hardware: indirizzo IP WebInternal.contoso.net di HLB VIP 192.168.10.5</p></li>
</ul>
<p>Tutto il traffico ad eccezione del traffico HTTP/HTTPS userà il record Pool01.contoso.net. Il traffico HTTP/HTTPS utilizzerà l'indirizzo dei servizi Web interni definiti di 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Pool Front end con bilanciamento del carico DNS distribuito</p></td>
<td><p>Un set di record interni che risolve il nome di dominio completo del pool nell'indirizzo IP di ogni server nel pool. È necessario un record per ogni server nel pool.</p></td>
</tr>
<tr class="odd">
<td><p>Pool Front end con bilanciamento del carico DNS distribuito</p></td>
<td><p>Un set di record interni che risolve il nome di dominio completo di ogni server nel pool con l'indirizzo IP del server. Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p>Pool Front-end con un singolo server front-end e un database back-end dedicato ma nessun bilanciamento del carico</p></td>
<td><p>Un record interno che risolve il nome di dominio completo del pool Front end con l'indirizzo IP del server front-end single Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>Accesso automatico client</p></td>
<td><p>Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;dominio&gt; sulla porta 5061 che esegue il mapping al nome di dominio completo del pool Front end che autentica e reindirizza le richieste client per l'accesso. Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisiti DNS per l'accesso automatico al client in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Individuazione del servizio Web di aggiornamento dispositivi da dispositivi Unified Communications (UC)</p></td>
<td><p>Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che risolve l'indirizzo IP del pool Front-end che ospita il servizio Web Update del dispositivo. Nella situazione in cui è attivato un dispositivo UC, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento del dispositivo di hosting del pool Front end e di ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono queste informazioni anche se il provisioning in banda è la prima volta che si accede a un utente.</p>
<div>

> [!IMPORTANT]  
> Se si dispone di una distribuzione esistente del servizio Web Update per dispositivi in Lync Server 2010, è già stato creato un record interno con il nome ucupdates. &lt;Dominio&gt;SIP. Per Microsoft Office Communications Server 2007 R2, è necessario creare un record DNS aggiuntivo con il nome ucupdates-R2. &lt;Dominio&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Proxy inverso per supportare il traffico HTTP</p></td>
<td><p>Un record esterno che risolve il nome di dominio completo della Web farm esterna nell'indirizzo IP esterno del proxy inverso. I client e i dispositivi UC usano questo record per connettersi al proxy inverso. Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determinare i requisiti DNS per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente viene illustrato un esempio dei record DNS necessari per l'FQDN della Web farm interna.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Record DNS di esempio per l'FQDN della Web farm interna

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN interno della Web farm</th>
<th>FQDN del pool</th>
<th>Record DNS (s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS un record per il ee-pool.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico usato dai server front-end.</p>
<p>Record DNS per webcon.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico usato dai server front-end.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Record DNS per ee-pool.contoso.com che viene risolto nell'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico usato dai server front-end Enterprise Edition nel pool Front-end.</p>
<p>Tieni presente che se usi il bilanciamento del carico DNS in questo pool, il tuo pool di front end e la Web farm interna non possono avere lo stesso nome FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

