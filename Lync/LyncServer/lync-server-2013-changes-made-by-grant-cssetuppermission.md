---
title: 'Lync Server 2013: modifiche apportate da Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-20_

Per delegare la configurazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, che consente ai membri del gruppo RTCUniversalServerAdmins in tale OU di installare Lync Server 2013 nell'elemento specificato dominio senza essere membri del gruppo Domain Admins.

Il cmdlet **Grant-CsSetupPermission** concede le autorizzazioni di gruppo RTCUniversalServerAdmins per un'unità organizzativa, come specificato nella tabella seguente:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Autorizzazioni concesse agli oggetti nell'unità organizzativa

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Le autorizzazioni si applicano a:</th>
<th>Le autorizzazioni concesse sono:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Leggere servicePrincipalName</p></li>
<li><p>Scrivere servicePrincipalName</p></li>
<li><p>Elimina albero</p></li>
<li><p>Replica delle modifiche della directory</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti serviceConnectionPoint discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Autorizzazioni di lettura</p></li>
<li><p>Autorizzazioni di scrittura</p></li>
<li><p>Creare un bambino</p></li>
<li><p>Eliminare il bambino</p></li>
<li><p>Contenuto dell'elenco</p></li>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-Server discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-WebComponents discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-MCU discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-MediationServer discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-ApplicationServer discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-ConnectionPoint discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà Write</p></li>
<li><p>Proprietà Read</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti computer discendenti</p></td>
<td><p>Accesso speciale per serviceConnectionPoint:</p>
<ul>
<li><p>Creare oggetti figlio</p></li>
<li><p>Eliminare oggetti figlio</p></li>
<li><p>Elimina albero</p></li>
</ul>
<p>Accesso speciale per informazioni pubbliche:</p>
<ul>
<li><p>Proprietà Read</p></li>
</ul>
<p>Accesso speciale per il nome host DNS:</p>
<ul>
<li><p>Proprietà Read</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

