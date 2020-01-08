---
title: 'Lync Server 2013: Informazioni sui requisiti del firewall per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Per una distribuzione Standard Edition, le eccezioni del firewall vengono create automaticamente durante l'installazione di Lync Server 2013. Per le distribuzioni di Enterprise Edition, tuttavia, è necessario configurare manualmente le eccezioni del firewall nel server back-end di SQL Server. Il protocollo TCP/IP consente di usare una determinata porta per un indirizzo IP specifico. Questo significa che per il server basato su SQL Server è possibile assegnare l'istanza di database predefinita la porta TCP predefinita 1433. Per qualsiasi altra istanza sarà necessario usare Gestione configurazione SQL Server per assegnare porte univoche e inutilizzate. Questo argomento illustra:

  - Requisiti per un'eccezione del firewall quando si usa l'istanza predefinita

  - Requisiti per un'eccezione del firewall per il servizio SQL Server browser

  - Requisiti per le porte di ascolto statiche quando si usano istanze denominate

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Requisiti per un'eccezione del firewall quando si usa l'istanza predefinita

Se si usa l'istanza predefinita di SQL Server per qualsiasi database durante la distribuzione di Lync Server 2013, vengono usati i requisiti di regola del firewall seguenti per garantire la comunicazione dal pool Front-end all'istanza predefinita di SQL Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo</th>
<th>Porta</th>
<th>Direzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>In ingresso a SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisiti per un'eccezione del firewall per il servizio SQL Server browser

Il servizio SQL Server browser individuerà le istanze di database e comunicherà la porta che l'istanza (denominata o predefinita) è configurata per l'uso.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo</th>
<th>Porta</th>
<th>Direzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>In ingresso</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisiti per le porte di ascolto statiche quando si usano istanze denominate

Quando si usano istanze denominate nella configurazione di SQL Server per i database che supportano Lync Server 2013, è possibile configurare le porte statiche tramite Gestione configurazione SQL Server. Dopo aver assegnato le porte statiche a ogni istanza denominata, è possibile creare eccezioni per ogni porta statica nel firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo</th>
<th>Porta</th>
<th>Direzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Staticamente definiti</p></td>
<td><p>In ingresso</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentazione di SQL Server

La documentazione di Microsoft SQL Server 2012 fornisce indicazioni dettagliate su come configurare l'accesso tramite firewall per i database. Per informazioni dettagliate su Microsoft SQL Server 2012, vedere la pagina relativa alla configurazione di Windows Firewall per consentire l' [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)accesso a SQL Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

