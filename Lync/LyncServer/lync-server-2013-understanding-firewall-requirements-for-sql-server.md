---
title: 'Lync Server 2013: informazioni sui requisiti del firewall per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba04284106bcd1b0cbf17d214d8ad0b1a1ff9024
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Per una distribuzione di Standard Edition, le eccezioni del firewall vengono create automaticamente durante l'installazione di Lync Server 2013. Per le distribuzioni di Enterprise Edition, tuttavia, è necessario configurare manualmente le eccezioni del firewall sul server back-end di SQL Server. Il protocollo TCP/IP consente un solo utilizzo di una determinata porta per un determinato indirizzo IP. Per il server basato su SQL Server, è pertanto possibile assegnare all'istanza di database predefinita la porta TCP predefinita 1433. Per qualsiasi altra istanza, sarà necessario utilizzare Gestione configurazione SQL Server per assegnare porte univoche e inutilizzate. In questo argomento vengono trattati i temi seguenti:

  - Requisiti per un'eccezione del firewall nei casi in cui viene utilizzata l'istanza predefinita

  - Requisiti per un'eccezione del firewall per il servizio SQL Server Browser

  - Requisiti per le porte di attesa statiche nei casi in cui vengono utilizzate istanze denominate

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Requisiti per un'eccezione del firewall nei casi in cui viene utilizzata l'istanza predefinita

Se si utilizza l'istanza predefinita di SQL Server per qualsiasi database durante la distribuzione di Lync Server 2013, vengono utilizzati i requisiti di regola del firewall riportati di seguito per garantire la comunicazione dal pool Front end all'istanza predefinita di SQL Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol</th>
<th>Porta</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>In ingresso-SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisiti per un'eccezione del firewall per il servizio SQL Server Browser

Il servizio SQL Server Browser individuerà le istanze di database e comunicherà la porta configurata per l'istanza (denominata o predefinita).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol</th>
<th>Porta</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisiti per le porte di attesa statiche nei casi in cui vengono utilizzate istanze denominate

Quando si utilizzano le istanze denominate nella configurazione di SQL Server per i database che supportano Lync Server 2013, è necessario configurare le porte statiche mediante Gestione configurazione SQL Server. Dopo l'assegnazione delle porte statiche a ogni istanza denominata, creare eccezioni per ogni porta statica nel firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol</th>
<th>Porta</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Definita in modo statico</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentazione di SQL Server

La documentazione di Microsoft SQL Server 2012 fornisce informazioni dettagliate su come configurare l'accesso del firewall per i database. Per informazioni dettagliate su Microsoft SQL Server 2012, vedere la sezione relativa alla configurazione di Windows Firewall per consentire l' [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)accesso a SQL Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

