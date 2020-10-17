---
title: 'Lync Server 2013: riepilogo del certificato-singolo amministratore'
description: 'Lync Server 2013: riepilogo del certificato-singolo server Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572162"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Riepilogo del certificato-singolo amministratore in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

I requisiti dei certificati per un singolo server Director sono costituiti da un certificato predefinito che ha un nome soggetto e nomi alternativi del soggetto per i servizi che il Director può ricevere. È inoltre presente un certificato token OAuth ai fini dell'autenticazione da server a server.

### <a name="certificates-for-director"></a>Certificati per il Director

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
<td><p>Predefiniti</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facoltativamente) *.contoso.com</p></td>
<td><p>I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</p>
<p>Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale. I client interni non utilizzeranno il server Director.</p>
<p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Nessuna voce</p></td>
<td><div>

> [!IMPORTANT]  
> Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.


</div>
<p>Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

