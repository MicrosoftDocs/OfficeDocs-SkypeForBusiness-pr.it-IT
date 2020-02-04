---
title: 'Lync Server 2013: Requisiti di DNS per il pool Front End'
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
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisiti di DNS per il pool Front End in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-07_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

È necessario configurare i record DNS (Domain Name System) necessari prima di pubblicare la topologia in Generatore di topologie. Inoltre, alcuni dei nomi di dominio completi (FQDN) usati nella configurazione di una distribuzione di Lync Server 2013 sono FQDN dei server logici e non fisici, quindi è necessaria una configurazione DNS aggiuntiva prima della pubblicazione.

<div>


> [!WARNING]  
> Lync Server 2013 non supporta i domini con etichetta singola. Ad esempio, è supportata una foresta con un dominio radice denominato <STRONG>contoso. local</STRONG> , ma un dominio radice denominato <STRONG>local</STRONG> non è supportato. Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta singola," at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Il nome specificato deve essere uguale al nome del computer configurato nel server. Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve, non un FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. <STRONG>Usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi dei server che usano Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dalle autorità di certificazione pubbliche e DNS esterne (CAs) (quando il nome di dominio completo deve essere assegnato a SN nel certificato).



</div>

Prima di utilizzare la topologia dopo la distribuzione, verificare che vengano creati i seguenti record DNS e Active Directory (in base alle esigenze delle caratteristiche specifiche):

  - Ogni ruolo del server che esisterà nella topologia viene pubblicato come oggetto Active Directory (l'aggiunta del computer al dominio verrà realizzata).

  - Un record DNS esiste per ogni server.

  - Un record SRV DNS esiste per ogni dominio SIP se si prevede di usare l'accesso automatico per i client in forma \_di\_sipinternaltls TCP. \<Dominio\>SIP. Se si utilizzerà la configurazione manuale per i client, questo record non è necessario.

  - Un record DNS per ogni URL semplice configurato, di cui ci sono in genere quattro: Meet, dialin, LWA e Scheduler. Inoltre, c'è l'URL semplice amministratore che è un URL speciale per l'accesso al pannello di controllo di Lync Server 2013.

  - Il server in cui è in uso SQL Server deve essere unito al dominio e raggiungibile dal computer a cui viene eseguita la pubblicazione di generatore di topologia.

La tabella segue le architetture di riferimento presentate nella sezione pianificazione. Per informazioni dettagliate, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) nella documentazione relativa alla pianificazione.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Record DNS necessari per il pool Front-End

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
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (bilanciamento del carico DNS). Richiede un record DNS per l'indirizzo IP di ogni server front-end all'interno del pool, eseguendo il mapping al nome di dominio completo del pool.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (Virtual IP (VIP) di bilanciamento del carico hardware).</p></td>
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
<td><p>Pool01 (VIP) per il traffico Web da client a server.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01 back end server che utilizza SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Obbligatorio per Lync Phone Edition o accesso automatico dei client senza record SRV DNS e per la corrispondenza di domini rigidi. Non obbligatorio in tutti i casi.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Presuppone un secondo dominio SIP. Obbligatorio per Lync Phone Edition, accesso automatico dei client senza record SRV DNS e per la corrispondenza di domini rigidi. Non obbligatorio in tutti i casi.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL semplice per i servizi di conferenza telefonica con accesso esterno pubblicati internamente-Front End Server (o Director, se installato) risponde a semplici query URL.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL semplice per le conferenze pubblicate internamente-Front End Server (o Director, se installato) risponde a semplici query URL.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>Record facoltativo, URL semplice per il pannello di controllo di Lync Server 2013 pubblicato internamente-Front-End Server (o direttore, se installato) risponde a semplici query URL. È consigliabile solo nome host (nessun nome di dominio).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = indirizzo IP virtuale per il bilanciamento del carico hardware



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Record SRV DNS per il pool Front-End


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
<th>Mapping a/commenti</th>
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
<td><p>Origine del protocollo Network Time Protocol (NTP) necessaria per i dispositivi in cui è in esecuzione Lync Phone Edition. Internamente, questo deve puntare al controller di dominio. Se il controller di dominio non è definito, tenterà di usare il server NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

