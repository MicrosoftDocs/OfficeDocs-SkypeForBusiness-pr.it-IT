---
title: 'Lync Server 2013: modifiche apportate dalla preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Modifiche apportate dalla preparazione del dominio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2010-10-18_

Nella tabella seguente sono elencate le voci di controllo di accesso (ACE) create dalla preparazione del dominio nella radice del dominio. Tutte le voci ACE vengono ereditate se non diversamente specificato.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Voci ACE aggiunte alla radice del dominio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-gruppo</th>
<th>RTCUniversal-ServerReadOnly-gruppo</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-servizi</th>
<th>Utenti autenticati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contenitore di lettura (non ereditato)</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leggere l'utente di PropertySet user-account-Restrictions</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Leggere l'utente PropertySet Personal-Information</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leggere l'utente PropertySet generale-informazioni</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Leggere l'utente PropertySet Public-Information</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leggi utente PropertySet RTCUserSearchProperty-set</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
</tr>
<tr class="odd">
<td><p>Leggere l'utente PropertySet RTCPropertySet</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Scrivere gli indirizzi proxy della proprietà utente</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Scrivere l'utente PropertySet RTCUserSearchProperty-set</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Scrivere l'utente PropertySet RTCPropertySet</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Leggere PropertySet DS-replica-Get-modifiche di tutti gli oggetti di Active Directory</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente sono elencate le voci ACE create dalla preparazione del dominio nei tre contenitori predefiniti: utenti, computer e controller di dominio. Tutte le voci ACE vengono ereditate se non diversamente specificato.

### <a name="aces-added-to-built-in-containers"></a>Voci ACE aggiunte ai contenitori predefiniti

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-gruppo</th>
<th>RTCUniversal-ServerReadOnly-gruppo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contenitore di lettura (non ereditato)</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p><strong>Sì</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

