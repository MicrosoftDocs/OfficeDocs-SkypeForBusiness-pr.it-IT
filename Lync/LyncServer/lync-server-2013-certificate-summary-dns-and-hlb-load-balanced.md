---
title: 'Lync Server 2013: Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cd6d86844629544b54670eb07c3433d19f99f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

I requisiti di certificato per un amministratore con bilanciamento del carico DNS e un servizio di bilanciamento del carico hardware utilizzeranno un certificato predefinito con un nome soggetto e un oggetto alternativo per i servizi che il Director può ricevere. Viene richiesto un certificato per ogni amministratore del pool. È importante ricordare che il bilanciamento del carico hardware è il bilanciamento del carico solo del traffico proveniente dal proxy inverso. È inoltre disponibile un certificato OAuth per gli scopi di autenticazione server-server installati in ogni server.

### <a name="certificates-for-director"></a>Certificati per Director

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
<th>Nome soggetto (SN)</th>
<th>Nomi alternativi oggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facoltativamente) *. contoso.com</p></td>
<td><p>I certificati Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</p>
<p>Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dall'Edge Server. I client interni non useranno il Director.</p>
<p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Nessuna voce</p></td>
<td><div>

> [!IMPORTANT]  
> Tieni presente che la lunghezza della chiave minima è 1024, ma potresti ricevere un avviso che indica che la lunghezza della chiave minima consigliata è 2048 bit.


</div>
<p>Il certificato OAuthTokenIssuer è un certificato a scopo unico per l'autenticazione dei server in un ambiente su larga scala e può essere richiesto da una CA interna o da una CA pubblica. Il certificato è obbligatorio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

