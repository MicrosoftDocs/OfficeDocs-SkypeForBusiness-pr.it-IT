---
title: 'Lync Server 2013: Riepilogo dei certificati - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Riepilogo dei certificati - singolo server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

I requisiti di certificato per un singolo amministratore sono costituiti da un certificato predefinito con un nome soggetto e un oggetto alternativo per i servizi che il Director può ricevere. È inoltre disponibile un certificato OAuth per gli scopi di autenticazione server-server.

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
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
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

