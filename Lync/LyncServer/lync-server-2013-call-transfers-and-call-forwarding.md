---
title: 'Lync Server 2013: trasferimenti di chiamata e inoltro di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a78332e2fa24c4f718cb3cdb3cbc9dc93a03601d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Trasferimenti di chiamata e inoltro di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Quando viene coinvolto un endpoint PSTN, il routing in base alla posizione analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero la destinazione di trasferimento/inoltro). Il routing in base alla posizione determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.

Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un endpoint PSTN e l'utente di Lync trasferisce la chiamata a un altro utente di Lync. A seconda della posizione del sito di rete dell'endpoint del cessionario, il routing in base alla posizione influisce sul routing del trasferimento delle chiamate o su Inoltra.

### <a name="initiating-call-transfer-or-forward"></a>Avvio del trasferimento delle chiamate o dell'inoltro

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utente che avvia il trasferimento di chiamata/inoltra</th>
<th>L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra</th>
<th>L'endpoint di destinazione si trova in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra</th>
<th>L'endpoint di destinazione è in sito di rete sconosciuto o sito di rete non abilitato per il routing in base alla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente di Lync</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito</p></td>
<td><p>Non è consentito l'inoltro di chiamata o il trasferimento</p></td>
<td><p>Non è consentito l'inoltro di chiamata o il trasferimento</p></td>
</tr>
</tbody>
</table>

  

Ad esempio, un utente di Lync in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente Lync che si trova nello stesso sito di rete. In questo caso, il trasferimento di chiamata è consentito.

Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un altro utente Lync e uno degli utenti trasferisce la chiamata a un endpoint PSTN. A seconda della posizione dell'utente in cui viene trasferita la chiamata, la tabella descrive in che modo il routing basato sulla posizione influenza la chiamata.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Trasferimento di chiamata o inoltra all'endpoint PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione endpoint trasferimento/inoltro di chiamata</th>
<th>Utenti di Lync nello stesso sito di rete</th>
<th>Utenti di Lync in siti di rete diversi</th>
<th>Uno o entrambi gli utenti Lync nel sito di rete o sito di rete sconosciuto non sono abilitati per il routing in base alla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</p></td>
<td><p>Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</p></td>
<td><p>Chiamata inoltrata o trasferimento consentita dal criterio vocale dell'utente trasferito solo tramite trunk non abilitato per il routing in base alla posizione</p></td>
</tr>
</tbody>
</table>

  
Ad esempio, un utente di Lync in una chiamata con un altro utente Lync che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento di chiamata è consentito.

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing in base alla posizione in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

