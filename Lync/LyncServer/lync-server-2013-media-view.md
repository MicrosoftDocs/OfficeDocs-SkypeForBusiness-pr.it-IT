---
title: 'Lync Server 2013: visualizzazione multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Visualizzazione multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La visualizzazione multimediale non deve essere usata per calcolare la durata del supporto per una sessione. Questa visualizzazione contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio del supporto, perché il supporto viene avviato solo dopo l'accettazione della sessione.



</div>

La visualizzazione multimediale contiene tutte le colonne della [Visualizzazione SessionDetails in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in aggiunta a quelle elencate di seguito.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Contenuti multimediali</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di elemento multimediale. Per altre informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora in cui è stata inviata una richiesta multimediale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora di fine della sessione.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

