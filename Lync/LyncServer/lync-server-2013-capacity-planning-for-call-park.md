---
title: 'Lync Server 2013: pianificazione della capacità per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512833"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Pianificazione della capacità per il parcheggio di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-13_

<div id="sectionSection0" class="section">

Nella tabella seguente viene descritto il modello utente del parcheggio di chiamata che è possibile utilizzare come base per i requisiti di pianificazione della capacità.

<div>


> [!IMPORTANT]  
> Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi parcheggio di chiamata in entrambi i pool.



</div>

### <a name="call-park-user-model"></a>Modello utente del parcheggio di chiamata

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrica</th>
<th>Per pool Front End (con 8 Front End Server)</th>
<th>Per server Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Frequenza di parcheggio</p></td>
<td><p>8 al minuto</p></td>
<td><p>1 al minuto</p></td>
</tr>
<tr class="even">
<td><p>Frequenza di recupero delle chiamate parcheggiate</p></td>
<td><p>8 al minuto</p></td>
<td><p>1 al minuto</p></td>
</tr>
<tr class="odd">
<td><p>Durata media del parcheggio</p></td>
<td><p>60 secondi</p></td>
<td><p>60 secondi</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

