---
title: Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59adcaf94c3c4364c6bb62ce2b8cbcc5639af6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

I requisiti dei certificati per un server Director con un dispositivo di bilanciamento del carico hardware utilizzeranno un certificato predefinito con un nome soggetto e nomi alternativi soggetto per i servizi che il pool di server Director può ricevere. Viene richiesto un certificato per ogni Director del pool. Inoltre, esiste un certificato rilasciato dal token OAuth installato in ogni server per scopi di autenticazione da server a server.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Certificati per un server Director in scala che utilizza un servizio di bilanciamento hardware

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
<th>Nomi alternativi soggetto (SAN)</th>
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
<p>(Facoltativamente) *.contoso.com</p></td>
<td><p>I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</p>
<p>Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</p>
<p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Nessuna voce</p></td>
<td>


> [!IMPORTANT]
> Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.


<p>Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

