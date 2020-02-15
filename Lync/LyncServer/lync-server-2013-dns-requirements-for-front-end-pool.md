---
title: 'Lync Server 2013: requisiti DNS per il pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078b8dc63e630487e13f1d187896bcf0617c0d15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisiti DNS per il pool Front end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-07_

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.

È necessario configurare i record DNS (Domain Name System) necessari prima di pubblicare la topologia in Generatore di topologie. Inoltre, alcuni dei nomi di dominio completi (FQDN) utilizzati per la configurazione di una distribuzione di Lync Server 2013 sono FQDN del server fisico e logico, pertanto è necessaria una configurazione DNS supplementare prima della pubblicazione.

<div>


> [!WARNING]  
> Lync Server 2013 non supporta domini con etichetta singola. Una foresta con un dominio radice denominato <STRONG>contoso.local</STRONG> ad esempio è supportata, ma un dominio radice denominato <STRONG>local</STRONG> non è supportato. Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta singola," at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Il nome specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. Quando si assegnano FQDN dei server in cui sono in esecuzione Lync Server, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno). Non usare i caratteri Unicode o i caratteri di sottolineatura. I caratteri non standard di un FQDN spesso non sono supportati dalle autorità di certificazione (CA) pubbliche e DNS esterne (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).



</div>

Prima di utilizzare la topologia dopo che è stata distribuita, verificare che siano stati creati i record DNS e Active Directory seguenti, in base alle esigenze per le caratteristiche specifiche:

  - Ogni ruolo del server che sarà presente nella topologia viene pubblicato come un oggetto Active Directory (l'aggiunta del computer al dominio lo otterrà).

  - Deve esistere un record A DNS per ogni server.

  - Un record SRV DNS esiste per ogni dominio SIP se si prevede di utilizzare l'accesso automatico per i client nel formato \_sipinternaltls\_TCP. \<Dominio\>SIP. Se si userà la configurazione manuale per i client, questo record non è necessario.

  - Un record A DNS per ogni URL semplice configurato, di cui sono in genere quattro: Meet, dialin, LWA e Scheduler. Inoltre, è disponibile l'URL semplice di amministrazione che è un URL speciale per accedere al pannello di controllo di Lync Server 2013.

  - Il server che esegue SQL Server deve essere aggiunto al dominio e raggiungibile dal computer da cui viene eseguita la pubblicazione del generatore di topologie.

La tabella seguente è basata sulle architetture di riferimento presentate nella sezione di pianificazione. Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) nella documentazione relativa alla pianificazione.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Record DNS necessari per il pool Front End

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione</th>
<th>Tipo</th>
<th>FQDN</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (bilanciamento del carico DNS). Richiede un record a DNS per l'indirizzo IP di ogni Front End Server all'interno del pool, eseguendo il mapping all'FQDN del pool.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (IP virtuale (VIP) del dispositivo di bilanciamento del carico hardware).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 Front End Server (nodo 1).</p>
<p>Pool01 Front End Server (nodo 2).</p>
<p>Pool01 Front End Server (nodo 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 Front End Server (nodo 2).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) per traffico Web da client a server.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01 back-end server che esegue SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Obbligatorio per Lync Phone Edition o per l'accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa. Non necessario in tutti i casi.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Presuppone un secondo dominio SIP. Obbligatorio per Lync Phone Edition, accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa. Non necessario in tutti i casi.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL semplice per le conferenze telefoniche con accesso esterno pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL semplice per le conferenze pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>interfaccia amministrazione</p></td>
<td><p>Record facoltativo, URL semplice per il pannello di controllo di Lync Server 2013 pubblicato internamente-Front End Server (o Director, se installato) risponde a query URL semplici. È consigliabile utilizzare solo il nome host (nessun nome di dominio).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = indirizzo IP virtuale per il dispositivo di bilanciamento del carico hardware



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Record SRV DNS per il pool Front End


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione</th>
<th>Tipo</th>
<th>FQDN</th>
<th>FQDN di destinazione</th>
<th>Porta</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp. _udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Origine di protocollo Network Time Protocol (NTP) necessaria per i dispositivi che eseguono Lync Phone Edition. Internamente deve puntare al controller di dominio. Se quest'ultimo non è definito, tenterà di usare il server NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

