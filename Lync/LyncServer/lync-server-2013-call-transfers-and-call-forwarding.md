---
title: 'Lync Server 2013: Trasferimento e inoltro di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Trasferimento e inoltro di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Quando si tratta di un endpoint PSTN, il routing basato sulla posizione analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero destinazione di trasferimento/inoltro). Il routing basato sulla posizione determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.

La tabella seguente illustra lo scenario di un utente di Lync in una chiamata con un endpoint PSTN e l'utente di Lync trasferisce la chiamata a un altro utente di Lync. A seconda della posizione del sito di rete dell'endpoint del cessionario, il routing basato sulla posizione influenza il routing del trasferimento delle chiamate o inoltra.

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
<th>Utente che avvia il trasferimento/inoltro delle chiamate</th>
<th>L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra</th>
<th>L'endpoint di destinazione è in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra</th>
<th>Endpoint di destinazione in un sito di rete o un sito di rete sconosciuto non abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti di Lync</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito</p></td>
<td><p>La chiamata inoltra o transfer non è consentita</p></td>
<td><p>La chiamata inoltra o transfer non è consentita</p></td>
</tr>
</tbody>
</table>

  

Ad esempio, un utente di Lync in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente di Lync che si trova nello stesso sito di rete. In questo caso, il trasferimento della chiamata è consentito.

La tabella seguente illustra lo scenario di un utente di Lync in una chiamata con un altro utente di Lync e uno degli utenti trasferisce la chiamata a un endpoint PSTN. A seconda della posizione dell'utente a cui viene trasferita la chiamata, la tabella descrive in che modo il routing basato sulla posizione influenza la chiamata.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Trasferimento delle chiamate o inoltro all'endpoint PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione dell'endpoint trasferimento/inoltro chiamate</th>
<th>Utenti di Lync nello stesso sito di rete</th>
<th>Utenti di Lync in siti di rete diversi</th>
<th>Uno o entrambi gli utenti di Lync in un sito di rete o un sito di rete sconosciuto non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito dal criterio vocale dell'utente trasferito solo tramite Trunks non abilitato per il routing basato sulla posizione</p></td>
</tr>
</tbody>
</table>

  
Ad esempio, un utente di Lync in una chiamata con un altro utente Lync che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento delle chiamate è consentita.

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing in base alla posizione in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

