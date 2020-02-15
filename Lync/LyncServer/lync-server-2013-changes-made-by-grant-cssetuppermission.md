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
ms.openlocfilehash: 23547ebc7faf594ee3ea72ef7d0c094846ac94b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Per delegare l'installazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specifica, consentendo ai membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa di installare Lync Server 2013 nell'oggetto dominio senza essere membri del gruppo Domain Admins.

Il cmdlet **Grant-CsSetupPermission** concede al gruppo RTCUniversalServerAdmins le autorizzazioni per un'unità organizzativa, come specificato nella tabella seguente:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Autorizzazioni concesse a oggetti nell'unità organizzativa

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Le autorizzazioni si applicano a:</th>
<th>Autorizzazioni concesse:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Leggi servicePrincipalName</p></li>
<li><p>Scrivi in servicePrincipalName</p></li>
<li><p>Elimina albero</p></li>
<li><p>Replica modifiche directory</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti serviceConnectionPoint discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Autorizzazioni di lettura</p></li>
<li><p>Autorizzazioni di scrittura</p></li>
<li><p>Crea elemento figlio</p></li>
<li><p>Elimina elemento figlio</p></li>
<li><p>Elenca contenuto</p></li>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-Server discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-WebComponents discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-MCU discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-MediationServer discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti msRTCSIP-ApplicationServer discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Oggetti msRTCSIP-ConnectionPoint discendenti</p></td>
<td><p>Accesso speciale:</p>
<ul>
<li><p>Proprietà di scrittura</p></li>
<li><p>Proprietà di lettura</p></li>
<li><p>Elimina albero</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Oggetti Computer discendenti</p></td>
<td><p>Accesso speciale per serviceConnectionPoint:</p>
<ul>
<li><p>Crea oggetti figli</p></li>
<li><p>Elimina oggetti figli</p></li>
<li><p>Elimina albero</p></li>
</ul>
<p>Accesso speciale per informazioni pubbliche:</p>
<ul>
<li><p>Proprietà di lettura</p></li>
</ul>
<p>Accesso speciale per il nome host DNS:</p>
<ul>
<li><p>Proprietà di lettura</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

