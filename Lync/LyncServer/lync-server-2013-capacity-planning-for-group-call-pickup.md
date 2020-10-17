---
title: 'Lync Server 2013: pianificazione della capacità per il ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512813"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Pianificazione della capacità per il ritiro delle chiamate di gruppo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-12_

<div id="sectionSection0" class="section">

Nella tabella seguente viene descritto il modello utente di prelievo delle chiamate di gruppo che è possibile utilizzare come base per i requisiti di pianificazione della capacità.

<div>


> [!IMPORTANT]  
> Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi del parcheggio di chiamata, incluso il prelievo delle chiamate di gruppo, in entrambi i pool.



</div>

### <a name="group-call-pickup-user-model"></a>Modello utente di prelievo delle chiamate di gruppo

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
<td><p>Numero consigliato di utenti per gruppo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Numero consigliato di gruppi</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Numero massimo di utenti per pool abilitato per il prelievo delle chiamate di gruppo</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Velocità massima delle chiamate in arrivo per il numero totale di utenti abilitati per il prelievo delle chiamate di gruppo per pool al minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Velocità massima delle chiamate recuperate dagli utenti con il prelievo di chiamata di gruppo per pool al minuto</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Per i pool Front end con meno di otto Front End Server, calcolare le metriche linearmente. Ad esempio, se il pool Front End ha un front end server, calcolare il carico massimo come 1/8 dei valori riportati nella tabella.</P>
> <LI>
> <P>È possibile aumentare o diminuire il numero consigliato di utenti per gruppo e numero di gruppi finché non si supera il numero massimo di utenti per pool. Ad esempio, il server Standard Edition può avere 120 gruppi con 25 utenti per gruppo, perché il numero di utenti abilitati per il prelievo delle chiamate di gruppo è ancora all'interno del massimo modello utente (ovvero 120 gruppi per 25 utenti è 3.000 utenti abilitati per il ritiro delle chiamate di gruppo).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

