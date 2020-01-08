---
title: 'Lync Server 2013: Autorizzazioni di distribuzione per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Autorizzazioni di distribuzione per SQL Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Microsoft SQL Server 2012 offre requisiti specifici per l'installazione e la distribuzione di Lync Server 2013. Dato che Windows e SQL Server ne definiscono la sicurezza in modo diverso, l'accesso come amministratore nel dominio Active Directory non concede in modo implicito le autorizzazioni per SQL Server. È inoltre necessario essere membri dell'entità sysadmin nel server basato su SQL Server che si sta configurando.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Autorizzazioni necessarie per l'installazione di database e Lync Server

Le opzioni seguenti illustrano in dettaglio tre autorizzazioni e associazioni di appartenenza ai gruppi per l'installazione di file di Lync Server 2013 e database di SQL Server. Scegliere lo scenario che soddisfa meglio i requisiti dell'organizzazione.

### <a name="permissions-and-group-membership-associations"></a>Autorizzazioni e associazioni di appartenenza ai gruppi

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo di SQL Server o Lync Server 2013</th>
<th>Autorizzazioni di SQL Server e appartenenza a gruppi tipiche del ruolo</th>
<th>Autorizzazioni di Lync Server 2013 e appartenenza ai gruppi in tipico ruolo</th>
<th>Risultato delle autorizzazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amministratore di Lync Server 2013</p></td>
<td><p>Deve essere concessa l'appartenenza al gruppo di sicurezza di SQL Server sysadmin e al membro del gruppo Administrators locale di SQL Server</p></td>
<td><p>Deve essere un membro del gruppo RTCUniversalServerAdmins</p></td>
<td><p>L'amministratore di Lync Server 2013 dispone delle autorizzazioni appropriate per installare i database di Lync Server 2013 e SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Amministratore di SQL Server</p></td>
<td><p>Membro del gruppo sysadmin di SQL Server (o equivalente) e membro del gruppo Administrators locale di SQL Server</p></td>
<td><p>Deve essere un membro del gruppo RTCUniversalServerReadOnly</p></td>
<td><p>L'amministratore di SQL Server dispone delle autorizzazioni appropriate per installare i database di Lync Server 2013 e SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Entrambi gli amministratori che condividono le funzioni di installazione</p></td>
<td><p>L'amministratore di SQL Server è membro del gruppo sysadmin (o equivalente) e membro del gruppo Administrators locale di SQL Server</p></td>
<td><p>Lync Server 2013 Administrator è membro di RTCUniversalServerAdmins</p></td>
<td><p>L'amministratore di Lync Server 2013 può installare Lync Server 2013, ma non può installare i database. L'amministratore di SQL Server usa Lync Server Management Shell e i cmdlet di Windows PowerShell forniti dall'amministratore di Lync Server 2013 per installare i database. Il Lync Server 2013 Management Shell usato dall'amministratore di SQL Server è installato nel server front-end. In questo articolo viene eliminata l'esigenza di installare gli strumenti di amministrazione di Lync Server 2013 nel server basato su SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

