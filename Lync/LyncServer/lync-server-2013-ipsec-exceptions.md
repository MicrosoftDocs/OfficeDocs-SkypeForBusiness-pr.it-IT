---
title: Eccezioni IPsec di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Eccezioni IPsec in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-27_

Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare tale protocollo per l'intervallo delle porte utilizzate per l'invio del traffico audio, video e panorama video. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.

Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate.

### <a name="recommended-ipsec-exceptions"></a>Eccezioni IPsec consigliate

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome regola</th>
<th>IP origine</th>
<th>IP destinazione</th>
<th>Protocol</th>
<th>Porta origine</th>
<th>Porta destinazione</th>
<th>Requisito di autenticazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge Server in ingresso interno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>A/V Edge Server interno</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server in ingresso esterno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>A/V Edge Server esterno</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>A/V Edge Server interno in uscita</p></td>
<td><p>A/V Edge Server interno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP &amp; UDP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server esterno in uscita</p></td>
<td><p>A/V Edge Server esterno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>Mediation Server in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Mediation</p>
<p>Server (s)</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server in uscita</p></td>
<td><p>Mediation</p>
<p>Server (s)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>Operatore Conferenza in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Front End Server con Operatore Conferenza</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>Operatore Conferenza in uscita</p></td>
<td><p>Front End Server con Operatore Conferenza</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>A/V Conferencing Server in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Front End Server</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>A/V Conferencing in uscita</p></td>
<td><p>Front End Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>Exchange in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Messaggistica unificata di Exchange</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>Server di condivisione applicazioni in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Server di condivisione applicazioni</p></td>
<td><p>TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>Server di condivisione applicazioni in uscita</p></td>
<td><p>Server di condivisione applicazioni</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="even">
<td><p>Exchange in uscita</p></td>
<td><p>Messaggistica unificata di Exchange</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP</p></td>
<td><p>Intervallo porte multimediali specificato</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non autenticare</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

