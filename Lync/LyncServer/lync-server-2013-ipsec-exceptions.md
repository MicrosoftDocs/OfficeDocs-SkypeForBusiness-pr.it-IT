---
title: Eccezioni IPsec di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Eccezioni IPsec in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-27_

Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (Vedi IETF RFC 4301-4309), IPsec deve essere disabilitato tramite l'intervallo di porte usate per il recapito di audio, video e video panoramico. La raccomandazione è motivata dalla necessità di evitare qualsiasi ritardo nell'allocazione delle porte multimediali a causa della negoziazione IPsec.

La tabella seguente illustra le impostazioni di eccezione IPsec consigliate.

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
<th>IP di origine</th>
<th>IP di destinazione</th>
<th>Protocollo</th>
<th>Porta di origine</th>
<th>Porta di destinazione</th>
<th>Requisito di autenticazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge Server Internal in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>A/V Edge Server interno</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server esterno in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>A/V Edge Server esterno</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>A/V Edge Server in uscita interna</p></td>
<td><p>A/V Edge Server interno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP &amp; UDP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server in uscita esterna</p></td>
<td><p>A/V Edge Server esterno</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>Mediation Server in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Pubblicitari</p>
<p>Server (s)</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server in uscita</p></td>
<td><p>Pubblicitari</p>
<p>Server (s)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>Operatore di conferenza in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Server front-end con l'operatore di conferenza</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>Operatore di conferenza in uscita</p></td>
<td><p>Server front-end con l'operatore di conferenza</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>A/V Conferencing in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Server front-end</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>A/V Conferencing in uscita</p></td>
<td><p>Server front-end</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>Exchange in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Messaggistica unificata di Exchange</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>Server di condivisione applicazioni in ingresso</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Server di condivisione applicazioni</p></td>
<td><p>TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>Server di condivisione applicazioni in uscita</p></td>
<td><p>Server di condivisione applicazioni</p></td>
<td><p>Qualsiasi</p></td>
<td><p>TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="even">
<td><p>Exchange in uscita</p></td>
<td><p>Messaggistica unificata di Exchange</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Qualsiasi</p></td>
<td><p>UDP</p></td>
<td><p>Intervallo di porte multimediali specificato</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Non eseguire l'autenticazione</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

