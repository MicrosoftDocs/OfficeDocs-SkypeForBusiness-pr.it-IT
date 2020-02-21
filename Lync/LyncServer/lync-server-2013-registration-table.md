---
title: 'Lync Server 2013: tabella di registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a64bde9cabcae282be83b671115a5cda4e5580e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Tabella di registrazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

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
<td><p>datetime</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Data e ora della richiesta di sessione. Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Numero ID per identificare la sessione. Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID utente. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>GUID per identificare un endpoint di registrazione. L'evento di registrazione dallo stesso computer dello stesso utente in genere avrà lo stesso ID endpoint. Computer diversi hanno un ID endpoint diverso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>ID utilizzato per distinguere le registrazioni che interessano lo stesso utente e lo stesso endpoint.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Versione client dell'utente corrente. Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID del server di registrazione utilizzato per la registrazione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID del pool in cui è stata acquisita la sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Server perimetrale attraverso il quale passa la registrazione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Po'</p></td>
<td></td>
<td><p>Se l'utente è connesso o meno dall'interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Se il servizio utente è disponibile o meno.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Se registrare o meno nella funzione di registrazione principale.</p></td>
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
<td><p>datetime</p></td>
<td></td>
<td><p>Data/ora di registrazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Data/ora di annullamento della registrazione.</p></td>
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
<td><p>ID diagnostica della richiesta di registrazione. Indica il tipo di informazioni diagnostiche.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Dispositivo da cui proviene la richiesta di registrazione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Stranieri</p></td>
<td><p>Motivo dell'annullamento della registrazione, ad esempio 'user initiated' (avviato dall'utente), 'registration expired' (registrazione scaduta), 'client fail' (problema del client) e così via. Per ulteriori informazioni, vedere la <a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Indirizzo IP dell'endpoint con cui l'utente è registrato. Può essere un indirizzo IPv4 o IPv6.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

