---
title: 'Lync Server 2013: tabella PurgeSettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46516be447fa3099afe492e5edc4f4008ea5a079
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Tabella PurgeSettings (QoE) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

La tabella PurgeSettings contiene informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE. Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Microsoft Lync Server 2013 Management Shell eseguendo il comando seguente:

    Get-CsQoEConfiguration

Questa tabella è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Identificatore univoco per la raccolta di impostazioni di ripulitura QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database QoE. L'eliminazione verrà applicata ogni giorno al tomo specificato dall'impostazione PurgeHour. Se impostato su false (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Specifica l'età dei record QoE (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record QoE antecedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera. Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita. Il valore predefinito è 1 (1:00 AM). Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera. Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita. Il valore predefinito è 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

