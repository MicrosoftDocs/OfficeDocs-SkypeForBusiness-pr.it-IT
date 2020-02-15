---
title: 'Lync Server 2013: requisiti DNS per i pool Front End'
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
ms.openlocfilehash: 12fc719c52434e07599fb4b65604ea832dc95f7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Requisiti DNS per i pool Front end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-07_

In questa sezione vengono descritti i record DNS (Domain Name System) necessari per la distribuzione di pool Front End.

<div>

## <a name="dns-records-for-front-end-pools"></a>Record DNS per i pool Front End

Nella tabella seguente vengono specificati i requisiti DNS per la distribuzione di un pool Front End di Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Requisiti di DNS per un pool Front End

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
<td><p>Pool Front End con più Front End Server e un dispositivo di bilanciamento del carico hardware (indipendentemente dal fatto che nel pool sia implementato anche il bilanciamento del carico DNS)</p></td>
<td><p>Se si utilizza sia il bilanciamento del carico DNS che un dispositivo di bilanciamento del carico hardware, è necessario utilizzare record host (A). Creare un record A interno che venga risolto nel nome di dominio completo (FQDN) del pool Front End per il bilanciamento del carico DNS. Creare un record host (A) interno per i servizi Web interni nell'indirizzo IP virtuale del dispositivo di bilanciamento del carico. È necessario utilizzare il nome dei servizi Web interni come definito in Generatore di topologie.</p>
<p>Ad esempio, se si utilizzano sia il bilanciamento del carico DNS che il bilanciamento del carico hardware, è necessario un record a per ogni Front End Server in un pool per il bilanciamento del carico DNS e un record a per i servizi Web interni che puntano all'IP virtuale del dispositivo di bilanciamento del carico hardware. :</p>
<ul>
<li><p>Bilanciamento del carico DNS:   Pool01.contoso.net   Indirizzo IP del pool   10.10.10.5</p>
<div>

> [!WARNING]  
> Ogni Front End Server avrà anche un record A distinto:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Bilanciamento del carico hardware:   WebInternal.contoso.net   Indirizzo IP virtuale del dispositivo di bilanciamento del carico hardware   192.168.10.5</p></li>
</ul>
<p>Tutto il traffico eccetto quello HTTP/HTTPS utilizzerà il record Pool01.contoso.net. Il traffico HTTP/HTTPS utilizzerà l'indirizzo dei servizi Web interni 192.168.10.5 definito</p></td>
</tr>
<tr class="even">
<td><p>Pool Front End con bilanciamento del carico DNS</p></td>
<td><p>Un set di record A interni che risolvono l'FQDN del pool nell'indirizzo IP di ogni server nel pool. Deve esistere un solo record A per ogni server nel pool.</p></td>
</tr>
<tr class="odd">
<td><p>Pool Front End con bilanciamento del carico DNS</p></td>
<td><p>Un set di record A interni che risolvono l'FQDN di ogni server nell'indirizzo IP di tale server. Per ulteriori informazioni, vedere <a href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p>Pool Front End con un solo Front End Server e un database back-end dedicato, ma senza servizio di bilanciamento del carico</p></td>
<td><p>Un record A interno che risolve l'FQDN del pool Front End nell'indirizzo IP del singolo server Enterprise Edition Front End Server.</p></td>
</tr>
<tr class="odd">
<td><p>Accesso client automatico</p></td>
<td><p>Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;domain&gt; over Port 5061 che corrisponde al nome di dominio completo del pool Front end che autentica e reindirizza le richieste client per l'accesso. Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for Automatic client Sign-in in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Individuazione del servizio Web Aggiornamento dispositivi da parte di dispositivi per comunicazioni unificate</p></td>
<td><p>Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che si risolve nell'indirizzo IP del pool Front end che ospita il servizio Web aggiornamento dispositivi. Se viene acceso un dispositivo per comunicazioni unificate, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il pool Front End che ospita il servizio Web Aggiornamento dispositivi e ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono queste informazioni tramite il provisioning di tipo in-band la prima volta che un utente effettua l'accesso.</p>
<div>

> [!IMPORTANT]  
> Se si dispone di una distribuzione esistente del servizio Web aggiornamento dispositivi in Lync Server 2010, è stato già creato un record interno con il nome ucupdates. &lt;Dominio&gt;SIP. Per Microsoft Office Communications Server 2007 R2, è necessario creare un record DNS aggiuntivo con il nome ucupdates-R2. &lt;Dominio&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Proxy inverso per il supporto del traffico HTTP</p></td>
<td><p>Un record A esterno che risolve l'FQDN della Web farm esterna nell'indirizzo IP esterno del proxy inverso. I client e i dispositivi per comunicazioni unificate utilizzano questo record per la connessione al proxy inverso. Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente viene illustrato un esempio dei record DNS necessari per il nome di dominio completo (FQDN) della Web farm interna.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Record DNS di esempio per il nome di dominio completo (FQDN) della Web farm interna

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN Web farm interna</th>
<th>FQDN pool</th>
<th>Record A DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Record A DNS per ee-pool.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico utilizzato dai Front End Server.</p>
<p>Record A DNS per webcon.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico utilizzato dai Front End Server.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Record A DNS per ee-pool.contoso.com che viene risolto nell'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico utilizzato dai server Enterprise Edition Front End Server nel pool Front End.</p>
<p>Si noti che se si utilizza il bilanciamento del carico DNS nel pool, il pool Front End e la Web farm interna non potranno avere lo stesso FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

