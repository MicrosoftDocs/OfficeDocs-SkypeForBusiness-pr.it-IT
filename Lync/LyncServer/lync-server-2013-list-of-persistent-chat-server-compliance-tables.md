---
title: 'Lync Server 2013: elenco delle tabelle di conformità del server Chat persistente'
description: 'Lync Server 2013: elenco delle tabelle di conformità del server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550072"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Elenco delle tabelle di conformità del server chat persistente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></p></td>
<td><p>Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.</p>
<p>In questa tabella sono inclusi gli eventi relativi a chat persistente, ad esempio i messaggi di chat e i download di file. Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.</p>
<p>I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">ComplianceFanout in Lync Server 2013</a></p></td>
<td><p>Include i server che hanno elaborato un evento di conformità. È strettamente associata alla tabella ComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></p></td>
<td><p>Include i partecipanti correnti per servizio chat e per server. Viene mantenuto in base agli eventi di conformità di join e parti ricevuti dal servizio chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></p></td>
<td><p>Contiene informazioni relative allo stato di conformità a livello di pool.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

