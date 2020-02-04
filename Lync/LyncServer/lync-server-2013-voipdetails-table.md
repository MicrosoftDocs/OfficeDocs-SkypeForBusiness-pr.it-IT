---
title: 'Lync Server 2013: Tabella VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Tabella VoipDetails in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Ogni record rappresenta una chiamata di 1 2-Party in cui almeno un utente è un utente VoIP.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Principale</p></td>
<td><p>Ora della richiesta della sessione. Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p><strong>PhoneId</strong> del chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> . Se non è NULL e <strong>FromGatewayId</strong> non è null, il chiamante era un utente PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p><strong>PhoneId</strong> del destinatario della chiamata. Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> . Se non è NULL e <strong>ToGatewayId</strong> non è null, il destinatario della chiamata è un utente PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Server di mediazione da cui proviene la chiamata. Per altre informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Il server di mediazione chiamato sta andando. Per altre informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Gateway da cui proviene la chiamata. Per altre informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Gateway che la chiamata sta per. Per altre informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI dell'utente che ha scollegato la chiamata, se l'utente ha un URI. Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>ID del telefono che ha scollegato la chiamata è stata disconnessa da un telefono. Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

