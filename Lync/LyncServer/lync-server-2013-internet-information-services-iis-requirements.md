---
title: 'Lync Server 2013: Requisiti relativi a IIS (Internet Information Services)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Requisiti relativi a IIS (Internet Information Services) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-19_

Diversi componenti di Lync Server 2013 richiedono Internet Information Services (IIS). In questo argomento vengono illustrate le caratteristiche specifiche di IIS necessarie per supportare Lync Server. Gli argomenti in questa sezione descrivono i requisiti di componenti specifici per IIS.

Quando il ruolo del server Web (IIS) è abilitato in Windows Server 2008, per impostazione predefinita vengono installati vari servizi di ruolo. La tabella seguente descrive i servizi ruolo aggiuntivi che devono essere installati quando il ruolo del server Web (IIS) è abilitato in Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servizio ruolo</th>
<th>Funzionalità</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Reindirizzamento HTTP</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensibilità .NET</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensioni ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Filtri ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Strumenti di registrazione</p></td>
</tr>
<tr class="odd">
<td><p>Integrità e diagnostica</p></td>
<td><p>Traccia</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di base</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di Windows</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Script e strumenti di gestione di IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Compatibilità di gestione di IIS 6</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se si usa IIS 7,0 in un sistema operativo Windows Server 2008, il programma di installazione di Lync Server disabilita l'autenticazione in modalità kernel in IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Requisiti di IIS per pool Front End e server Standard Edition in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

