---
title: 'Lync Server 2013: Riepilogo dei certificati - proxy inverso'
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
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo dei certificati - proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-14_

I requisiti di certificato per il proxy inverso sono molto più semplici di quelli per gli Edge Server. Il diagramma di flusso fornito presenta i requisiti necessari. La tabella associata presenta il nome del soggetto del certificato tipico e i nomi alternativi oggetto in relazione agli scenari che sono stati esaminati nelle discussioni su Edge Server. Per altre informazioni sugli scenari di Edge Server, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagramma di flusso certificati per proxy inverso**

![Diagramma di flusso Certificati per Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramma di flusso Certificati per Edge Server")

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
<th>Nome oggetto</th>
<th>Nome alternativo oggetto (SAN)/Order</th>
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
<td><p>Il certificato deve essere emesso da un'autorità di certificazione pubblica e con il server EKU. I servizi includono servizio Rubrica, espansione gruppi di distribuzione Office Web Apps per le conferenze e regole di pubblicazione di Lync per dispositivi IP. Il nome alternativo soggetto include:</p>
<ul>
<li><p>FQDN dei servizi Web esterni per Front End Server o pool Front-End</p></li>
<li><p>FQDN dei servizi Web esterni per il pool di Director o Director</p></li>
<li><p>Chiamate in conferenza</p></li>
<li><p>Regola di pubblicazione delle riunioni online</p></li>
<li><p>Office Web Apps per le conferenze</p></li>
<li><p>Lyncdiscover (individuazione automatica)</p></li>
</ul>
<p>Il carattere jolly facoltativo sostituisce sia la riunione che la chiamata SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

