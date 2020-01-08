---
title: 'Lync Server 2013: regole di traduzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Regole di traduzione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Lync Server 2013 Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). In Microsoft Lync Server 2010 le regole di traduzione sono supportate solo per i numeri denominati. Novità di Microsoft Lync Server 2013 sono supportate anche regole di traduzione per i numeri di chiamata. Il *peer trunk* , ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP, può richiedere che i numeri siano in formato di chiamata locale. Per tradurre i numeri dal formato E. 164 a un formato di chiamata locale, è possibile definire una o più regole di traduzione per modificare l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.

Eseguendo la conversione della route in uscita sul server, è possibile ridurre i requisiti di configurazione per ogni singolo peer trunk per tradurre i numeri di telefono in un formato di chiamata locale. Quando si pianificano i gateway e il numero di gateway da associare a un cluster di Mediation Server specifico, potrebbe essere utile raggruppare i peer trunk con requisiti di selezione locali simili. In questo articolo è possibile ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.

<div>


> [!IMPORTANT]  
> L'associazione di una o più regole di traduzione con una configurazione trunk VoIP aziendale dovrebbe essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk, perché le due regole potrebbero essere in conflitto.



</div>

<div>

## <a name="example-translation-rules"></a>Esempio di regole di traduzione

Gli esempi seguenti di regole di traduzione mostrano come sviluppare regole nel server per tradurre i numeri dal formato E. 164 a un formato locale per il peer trunk.

Per informazioni dettagliate su come implementare le regole di traduzione, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.


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
<th>Modello di corrispondenza</th>
<th>Conversione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamata a lunga distanza convenzionale negli Stati Uniti</p>
<p>(Elimina il ' +')</p></td>
<td><p>+ 1</p></td>
<td><p>Esattamente 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+ 14255551010 diventa 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Chiamate interurbane internazionali degli Stati Uniti</p>
<p>(Strip out ' +' e Add 011)</p></td>
<td><p>+</p></td>
<td><p>Almeno 11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+ 441235551010 diventa 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

