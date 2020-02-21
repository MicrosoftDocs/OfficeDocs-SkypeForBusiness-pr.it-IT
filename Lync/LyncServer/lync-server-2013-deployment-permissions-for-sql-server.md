---
title: 'Lync Server 2013: autorizzazioni di distribuzione per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d24a60c089efef55718dd71d889caade8f24949a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Autorizzazioni di distribuzione per SQL Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Microsoft SQL Server 2012 ha requisiti specifici per l'installazione e la distribuzione di Lync Server 2013. Poiché Windows e SQL Server definiscono la propria sicurezza in modo diverso, l'accesso come amministratore nel dominio di Active Directory non concede implicitamente autorizzazioni per SQL Server. È inoltre necessario essere membri dell'entità sysadmin nel server basato su SQL Server che si sta configurando.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Autorizzazioni necessarie per l'installazione dei database e di Lync Server

Le opzioni seguenti specificano tre autorizzazioni e associazioni di appartenenza a gruppi per l'installazione di file di Lync Server 2013 e database di SQL Server. Scegliere lo scenario più adatto ai requisiti specifici dell'organizzazione.

### <a name="permissions-and-group-membership-associations"></a>Associazioni di autorizzazioni e appartenenze ai gruppi

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo SQL Server o Lync Server 2013</th>
<th>Autorizzazioni e appartenenze ai gruppi di SQL Server tipiche del ruolo</th>
<th>Autorizzazioni di Lync Server 2013 e appartenenza a gruppi tipiche del ruolo</th>
<th>Risultati delle autorizzazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amministratore di Lync Server 2013</p></td>
<td><p>Deve appartenere al gruppo di sicurezza sysadmins di SQL Server ed essere membro del gruppo Administrators locale di SQL Server</p></td>
<td><p>Deve essere un membro del gruppo RTCUniversalServerAdmins</p></td>
<td><p>L'amministratore di Lync Server 2013 dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Amministratore di SQL Server</p></td>
<td><p>Membro del gruppo sysadmins di SQL Server (o equivalente) e membro del gruppo Administrators locale di SQL Server</p></td>
<td><p>Deve essere un membro del gruppo RTCUniversalServerReadOnly</p></td>
<td><p>L'amministratore di SQL Server dispone delle autorizzazioni appropriate per installare sia Lync Server 2013 che i database di SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Entrambi gli amministratori condividono responsabilità per l'installazione</p></td>
<td><p>L'amministratore di SQL Server è membro del gruppo sysadmins (o equivalente) e membro del gruppo Administrarors locale di SQL Server</p></td>
<td><p>Lync Server 2013 Administrator è membro di RTCUniversalServerAdmins</p></td>
<td><p>L'amministratore di Lync Server 2013 può installare Lync Server 2013, ma non è in grado di installare i database. L'amministratore di SQL Server utilizza i cmdlet di Lync Server Management Shell e Windows PowerShell forniti dall'amministratore di Lync Server 2013 per installare i database. Il Lync Server 2013 Management Shell utilizzato dall'amministratore di SQL Server viene installato nel front end server. In questo modo viene eliminata la necessità di installare gli strumenti di amministrazione di Lync Server 2013 nel server basato su SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

