---
title: 'Lync Server 2013: pianificazione della capacità per il ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Pianificazione della capacità per il ritiro delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-12_

<div id="sectionSection0" class="section">

La tabella seguente descrive il modello di utente di prelievo delle chiamate di gruppo che puoi usare come base per i requisiti di pianificazione della capacità.

<div>


> [!IMPORTANT]  
> Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park. Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park, incluso il ritiro delle chiamate di gruppo, in entrambi i pool.



</div>

### <a name="group-call-pickup-user-model"></a>Modello utente di raccolta chiamate di gruppo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrica</th>
<th>Per pool Front-End (con 8 server front-end)</th>
<th>Per server Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Numero di utenti consigliati per gruppo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Numero consigliato di gruppi</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Numero massimo di utenti per pool abilitato per il ritiro delle chiamate di gruppo</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Tasso massimo delle chiamate in arrivo per il totale degli utenti abilitati per il ritiro delle chiamate di gruppo per pool al minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Tasso massimo delle chiamate recuperate dagli utenti con il ritiro delle chiamate di gruppo per pool al minuto</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Per i pool Front-end con meno di otto server front-end, calcolare le metriche linearmente. Ad esempio, se il pool Front-End ha un server front-end, calcolare il carico massimo come 1/8 dei valori visualizzati nella tabella.</P>
> <LI>
> <P>È possibile aumentare o ridurre il numero di utenti consigliati per ogni gruppo e numero di gruppi purché non venga superato il numero massimo di utenti per pool. Ad esempio, il server Standard Edition può avere gruppi di 120 con 25 utenti per gruppo, perché il numero di utenti abilitati per il ritiro delle chiamate di gruppo è ancora all'interno del massimo del modello utente (ovvero 120 gruppi per 25 utenti è consentito agli utenti di 3.000 per il ritiro delle chiamate di gruppo).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

