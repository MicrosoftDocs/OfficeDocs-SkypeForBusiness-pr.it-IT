---
title: 'Lync Server 2013: regole di conversione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 088657d530224288a9ffabbfa1644d0fea6796e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Regole di conversione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Lync Server 2013 Enterprise Voice richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa). In Microsoft Lync Server 2010, le regole di conversione sono supportate solo per i numeri denominati. Nuovo in Microsoft Lync Server 2013, le regole di conversione sono supportate anche per i numeri di chiamata. Il *trunk peer* ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere l'utilizzo del formato di composizione locale per i numeri. Per convertire i numeri dal formato E.164 a quello locale, è possibile definire una o più regole di conversione per modificare l'URI richiesta prima di eseguirne il routing al trunk peer. È possibile, ad esempio, scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.

Eseguendo la conversione delle route in uscita sul server, è possibile ridurre i requisiti di configurazione per ogni singolo peer trunk per tradurre i numeri di telefono in un formato di composizione locale. Quando si pianificano i gateway e il numero di gateway da associare a un cluster di Mediation Server specifico, potrebbe essere utile raggruppare i peer trunk con requisiti di composizione locali simili. In questo modo è possibile ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverle.

<div>


> [!IMPORTANT]  
> L'associazione di una o più regole di conversione a una configurazione trunk VoIP aziendale deve essere utilizzata come alternativa alla configurazione delle regole di conversione nel peer trunk. Non associare regole di conversione a una configurazione trunk VoIP aziendale se sono state configurate regole di conversione nel peer trunk, perché le due regole potrebbero essere in conflitto.



</div>

<div>

## <a name="example-translation-rules"></a>Esempi di regole di traduzione

Gli esempi di regole di traduzione seguenti indicano come sviluppare regole nel server per convertire numeri dal formato E.164 a un formato locale per il trunk peer.

Per informazioni dettagliate sull'implementazione delle regole di conversione, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Cifre iniziali</th>
<th>Lunghezza</th>
<th>Cifre da rimuovere</th>
<th>Cifre da aggiungere</th>
<th>Formato corrispondente</th>
<th>Translation</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Composizione convenzionale di interurbane negli Stati Uniti</p>
<p>(rimuovere il '+')</p></td>
<td><p>+ 1</p></td>
<td><p>Esattamente 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 diventa 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Composizione di interurbane internazionali negli Stati Uniti</p>
<p>(rimuovere il '+' e aggiungere 011)</p></td>
<td><p>+</p></td>
<td><p>Almeno 11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+441235551010 diventa 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

