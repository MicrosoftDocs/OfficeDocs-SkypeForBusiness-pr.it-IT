---
title: 'Lync Server 2013: Configurazione di una route di failover'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Configurazione di una route di failover in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

L'esempio seguente mostra il modo in cui un amministratore può definire una route di failover da usare se Dallas-GW1 è in calo per la manutenzione o altrimenti non è disponibile. Le tabelle seguenti illustrano la modifica della configurazione necessaria.

### <a name="table-1-user-policy"></a>Tabella 1. Criteri utente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Criteri utente</th>
<th>Uso del telefono</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri di chiamata predefiniti</p></td>
<td><p>Locale</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Criteri locali Redmond</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Criteri di chiamata Dallas</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>Tabella 2. Indirizza

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome Route</th>
<th>Schema numerico</th>
<th>Uso del telefono</th>
<th>Tronco</th>
<th>Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Route locale Redmond</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d{7}) $</p></td>
<td><p>Locale</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Rosso-GW1</p>
<p>Rosso-GW2</p></td>
</tr>
<tr class="even">
<td><p>Route locale di Dallas</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d{7}) $</p></td>
<td><p>Locale</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Route universale</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Rosso-GW1</p>
<p>Rosso-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Route utenti Dallas</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


Nella tabella 1 viene aggiunto un uso telefonico di GlobalPSTNHopoff dopo l'uso del telefono DallasUsers nei criteri di chiamata di Dallas. In questo modo, le chiamate con i criteri di chiamata di Dallas possono usare le route configurate per l'utilizzo di GlobalPSTNHopoff Phone se non è disponibile una route per l'utilizzo del telefono DallasUsers.

</div>

<span> </span>

</div>

</div>

</div>

