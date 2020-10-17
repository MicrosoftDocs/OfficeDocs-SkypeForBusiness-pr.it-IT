---
title: 'Lync Server 2013: requisiti di Internet Information Services (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0c1c9966945554af6d1d9cec02a17dd884a857
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498483"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Requisiti di Internet Information Services (IIS) in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-19_

Diversi componenti di Lync Server 2013 richiedono Internet Information Services (IIS). In questo argomento vengono descritte le caratteristiche di IIS specifiche necessarie per il supporto di Lync Server. Negli argomenti di questa sezione vengono descritti i requisiti per i componenti specifici di IIS.

Quando il ruolo server Web (IIS) è abilitato su Windows Server 2008, per impostazione predefinita vengono installati vari servizi ruolo. Nella tabella seguente vengono descritti i servizi ruolo aggiuntivi che devono essere installati quando il ruolo server Web (IIS) è abilitato su Windows Server 2008.


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
<td><p>Estendibilità .NET</p></td>
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
<td><p>Analisi della</p></td>
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
<td><p>Strumenti e script di gestione IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Compatibilità gestione IIS 6</p></td>
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
<td>Se si utilizza IIS 7,0 in un sistema operativo Windows Server 2008, il programma di installazione di Lync Server disattiva l'autenticazione in modalità kernel in IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

