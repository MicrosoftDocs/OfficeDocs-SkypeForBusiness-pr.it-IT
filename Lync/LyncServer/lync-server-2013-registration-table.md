---
title: 'Lync Server 2013: Tabella Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Tabella Registration in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Ogni record rappresenta un evento di registrazione utente.


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
<td><p>Primaria, straniera</p></td>
<td><p>Ora della richiesta della sessione. Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>ID utente. Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>GUID per identificare un endpoint di registrazione. In genere, l'evento Register dello stesso computer dello stesso utente avrà lo stesso ID endpoint. I computer diversi hanno un ID endpoint diverso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>ID usato per distinguere le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Versione client dell'utente corrente. Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>ID del server registrar usato per la registrazione. Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>ID del pool in cui è stata acquisita la sessione. Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Edge Server che la registrazione sta attraversando. Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Po'</p></td>
<td></td>
<td><p>Se l'utente ha eseguito l'accesso da Internal o not.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Se il UserService è disponibile o meno.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Se eseguire la registrazione al registrar principale o meno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se l'utente è registrato o meno con un Survivable Branch Appliance.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateTime</p></td>
<td></td>
<td><p>Ora di registrazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>DateTime</p></td>
<td></td>
<td><p>Tempo di annullamento della registrazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Codice di risposta della richiesta di registrazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID di diagnostica della richiesta di registrazione. Indica il tipo di informazioni di diagnostica.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Il dispositivo da cui proviene la richiesta di registro. Per altre informazioni, vedere la <a href="lync-server-2013-devices-table.md">tabella dispositivi in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Esterna</p></td>
<td><p>Il motivo dell'annullamento della registrazione, ad esempio "utente avviato", "Registrazione scaduta", "errore client" e altro ancora. Per altre informazioni, vedere la <a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Indirizzo IP dell'endpoint con cui è stato registrato l'utente. Può trattarsi di un indirizzo IPv4 o di un indirizzo IPv6.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

