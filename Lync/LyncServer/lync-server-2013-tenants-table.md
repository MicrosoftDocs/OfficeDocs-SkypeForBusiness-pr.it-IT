---
title: 'Lync Server 2013: tabella Tenants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47c447d18589f8e0cd86c007df74a21287be949f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a>Tabella Tenants in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

La tabella Tenants è una tabella di supporto in cui viene archiviato un elenco dei diversi tenant. Ogni record della tabella rappresenta un tenant.

<div>


> [!NOTE]  
> Nelle distribuzioni on-premise, registrazione dettagli chiamata utilizza l'ID tenant predefinito per indicare tipi di autenticazione diversi, come connettività per messaggistica istantanea pubblica, autenticazione federata e autenticazione anonima.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Chiave/indice</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero univoco che identifica questo ID tenant.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valori consentiti:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 - Aziendale</p></li>
<li><p>00000000-0000-0000-0000-000000000001 - Federato</p></li>
<li><p>00000000-0000-0000-0000-000000000002 - Anonimo</p></li>
<li><p>00000000-0000-0000-0000-000000000003 - Connettività per la messaggistica istantanea pubblica</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

