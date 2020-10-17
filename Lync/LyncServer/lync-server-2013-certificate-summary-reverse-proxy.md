---
title: 'Lync Server 2013: riepilogo del certificato-proxy inverso'
description: 'Lync Server 2013: riepilogo del certificato-proxy inverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572302"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo del certificato-proxy inverso in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-14_

I requisiti dei certificati per il proxy inverso sono molto più semplici rispetto ai server perimetrali. Il diagramma di flusso descrive i requisiti necessari. La tabella di accompagnamento presenta il nome soggetto e i nomi alternativi del soggetto del certificato tipici in relazione agli scenari che sono stati esaminati nelle discussioni sui server perimetrali. Per ulteriori informazioni sugli scenari del server perimetrale, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagramma di flusso dei certificati per proxy inverso**

![Diagramma di flusso dei certificati per i server perimetrali](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramma di flusso dei certificati per i server perimetrali")

### <a name="reverse-proxy-external-interface"></a>Proxy inverso: interfaccia esterna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome soggetto</th>
<th>Ordine/nome alternativo soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxy inverso</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facoltativo):*. contoso.com</p></td>
<td><p>Il certificato deve essere emesso da una CA pubblica e con utilizzo chiavi avanzato del server. I servizi includono il servizio Rubrica, l'espansione del gruppo di distribuzione Office Web Apps per le conferenze e le regole di pubblicazione del dispositivo IP di Lync. Il nome alternativo del soggetto include:</p>
<ul>
<li><p>FQDN dei servizi Web esterni per Front End Server o pool Front End</p></li>
<li><p>FQDN dei servizi Web esterni per il pool di server Director o Director</p></li>
<li><p>Conferenza telefonica con accesso esterno</p></li>
<li><p>Regola di pubblicazione per riunioni online</p></li>
<li><p>Office Web Apps per le conferenze</p></li>
<li><p>Lyncdiscover (individuazione automatica)</p></li>
</ul>
<p>Il carattere jolly facoltativo sostituisce il nome alternativo del soggetto meet e dialin</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

