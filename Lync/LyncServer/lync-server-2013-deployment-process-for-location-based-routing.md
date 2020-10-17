---
title: 'Lync Server 2013: processo di distribuzione per il routing di Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d2dfa15dce07fa66678932d8d765ec7308ba75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526923"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Processo di distribuzione per il routing Location-Based in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

In questo argomento viene fornita una panoramica del processo relativo alla configurazione del routing Location-Based. Prima di configurare Location-Based routing, è necessario distribuire Lync Server Enterprise Edition o Standard Edition con VoIP aziendale. I componenti necessari per il routing Location-Based sono già installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="location-based-routing-deployment-process"></a>Location-Based processo di distribuzione del routing

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Gruppi e ruoli obbligatori</th>
<th>Documentazione sulla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Distribuire VoIP aziendale</p></td>
<td><ul>
<li><p>Configurare trunk</p></li>
<li><p>Creare criteri vocali</p></li>
<li><p>Definire le route vocali</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Distribuzione di VoIP aziendale</p></td>
</tr>
<tr class="even">
<td><p>Verificare la distribuzione di VoIP aziendale</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurare aree di rete, siti e subnet</p></td>
<td><ul>
<li><p>Creare aree di rete</p></li>
<li><p>Creare siti di rete</p></li>
<li><p>Associa le subnet a siti di rete</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Informazioni su aree di rete, siti e subnet<br />
Creare o modificare un'area di rete<br />
Creare o modificare un sito di rete<br />
Associare una subnet a un sito di rete</p></td>
</tr>
<tr class="even">
<td><p>Configurare il routing Location-Based</p></td>
<td><ul>
<li><p>Creare criteri di routing vocale</p></li>
<li><p>Definire la configurazione trunk separata per trunk</p></li>
<li><p>Modificare i criteri vocali</p></li>
<li><p>Abilitare la configurazione del routing Location-Based</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>Distribuzione di esempio

La distribuzione seguente viene utilizzata per illustrare ulteriormente i meccanismi abilitati dal routing Location-Based.

![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Chiamate PSTN in arrivo

Un amministratore può abilitare il trunk definito per instradare le chiamate al "gateway del sito 1" per Location-Based il routing e associare il "sito 1 gateway" al sito 1. Una volta abilitata, le chiamate instradate tramite "sito 1 gateway" verranno instradate solo agli utenti che si trovano nel sito 1. Tutte le chiamate instradate attraverso il trunk "site 1 gateway" destinate agli utenti in un sito diverso, ad esempio il sito 2, verranno bloccate per impedire il bypass a pedaggio PSTN.

Tutte le chiamate PSTN in ingresso tramite "site 1 gateway" potranno essere instradate solo agli endpoint situati nel sito 1. Ad esempio, quando "Lync User 1" si sposta nel sito 2, tutte le chiamate PSTN in ingresso tramite "site 1 gateway" non verranno instradate agli endpoint "Lync User 1" presenti nel sito 2. La stessa regola di routing si applica se "Lync User 1" si sposta in un sito di rete sconosciuto in cui la posizione dell'utente non può essere determinata.

Nella tabella seguente viene descritta l'esperienza utente di "Lync User 1" in questo contesto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Endpoint di Lync User 1 situati nel sito di rete 1</th>
<th>Endpoint di Lync User 1 situati nel sito di rete 2</th>
<th>Endpoint di Lync User 1 che si trovano in un sito di rete sconosciuto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate PSTN in ingresso a Lync User 1</p></td>
<td><p>Le chiamate vengono instradate agli endpoint in questo percorso</p></td>
<td><p>Le chiamate non vengono instradate agli endpoint in questo percorso</p></td>
<td><p>Le chiamate non vengono instradate agli endpoint in questo percorso</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Chiamate PSTN in uscita

Le route vocali vengono referenziate sia nei criteri vocali assegnati direttamente agli utenti, sia nei criteri di routing vocale assegnati a siti di rete. Entrambi i criteri contengono riferimenti a route, che possono essere utilizzati per instradare una chiamata in modo diverso. Ad esempio, un amministratore può definire un criterio di routing vocale per tutti gli utenti che si trovano nel sito di rete 1 per instradare tutte le chiamate in uscita attraverso il "sito 1 gateway" mentre il criterio vocale di alcuni utenti definisce una route per tutte le chiamate in uscita attraverso il "sito 2 gateway". Anche se questi utenti si trovano nel sito di rete 1, le chiamate in uscita verranno instradate attraverso il "sito 1 gateway".

Quando un utente si trova in un sito di rete configurato per il routing Location-Based, la route dei criteri di routing vocale del sito di rete sostituisce la route dei criteri vocali dell'utente. Questa regola è particolarmente utile per gli utenti che si spostano temporaneamente in un altro sito. In questo caso particolare, un utente utilizzerà sempre un gateway che è locale per la propria posizione. Se "Lync User 3" si trova in "site 2", tutte le chiamate in uscita verranno instradate tramite "site 2 gateway", ma se si sposta sul sito 1, tutte le chiamate in uscita poste mentre è nel sito 1 verranno instradate attraverso "site 1 gateway".

Nella tabella seguente viene illustrata l'esperienza utente di Lync User 1 che effettua una chiamata in uscita dai seguenti siti di rete.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sito di rete 1</th>
<th>Sito di rete 2</th>
<th>Sito di rete sconosciuto o non abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorizzazione delle chiamate in uscita</p></td>
<td><p>Criteri vocali di Lync User 1</p></td>
<td><p>Criteri vocali di Lync User 1</p></td>
<td><p>Criteri vocali di Lync User 1</p></td>
</tr>
<tr class="even">
<td><p>Routing delle chiamate in uscita</p></td>
<td><p>Criterio di routing vocale del sito 1</p></td>
<td><p>Criterio di routing vocale del sito 2</p></td>
<td><p>Criteri vocali dell'utente e solo per i sistemi non abilitati per il routing Location-Based</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Trasferimenti e inoltri di chiamata

Quando le chiamate vengono trasferite o inoltrate, il routing delle chiamate è influenzato dal routing Location-Based.

Nella tabella seguente viene illustrato Lync User 1 che consente di trasferire o inoltrare una chiamata PSTN a un altro utente di Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utente che avvia il trasferimento delle chiamate o inoltra</th>
<th>Lync User 2</th>
<th>Lync User 4</th>
<th>Utente di Lync nel sito di rete non abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync utente 1</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito</p></td>
<td><p>Non è consentito l'inoltro di chiamata o il trasferimento</p></td>
<td><p>Non è consentito l'inoltro di chiamata o il trasferimento</p></td>
</tr>
</tbody>
</table>

  
Nella tabella seguente viene illustrato il modo in cui Location-Based routing influisce sulla modalità di instradamento della chiamata in base alla posizione dell'utente Lync trasferito (Lync User 2, Lync User 4 e così via) a un endpoint PSTN.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpoint in cui la chiamata viene trasferita o inoltrata a</th>
<th>Lync User 2</th>
<th>Lync User 4</th>
<th>Utente di Lync nel sito di rete non abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>La chiamata inoltra o il trasferimento viene instradato attraverso i criteri di routing vocale del sito 1 e l'uscita tramite il gateway del sito 1</p></td>
<td><p>La chiamata inoltra o il trasferimento viene instradato attraverso i criteri di routing vocale del sito 2 e l'uscita tramite il gateway del sito 2</p></td>
<td><p>La chiamata inoltra o il trasferimento viene instradato attraverso il criterio vocale di Lync User e l'uscita tramite un gateway non abilitato per il routing basato sulla posizione (se disponibile)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Squillo simultaneo

Una volta configurata la distribuzione in base alla posizione nella topologia di esempio, vengono applicate le interazioni seguenti.

Nella tabella seguente viene illustrato se Location-Based routing consente lo squillo simultaneo per gli utenti di Lync diversi (ad esempio, Lync User 2, Lync User 4 e così via).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione chiamata PSTN in ingresso</th>
<th>Lync User 2</th>
<th>Lync User 4</th>
<th>Utente di Lync nel sito di rete non abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync utente 1</p></td>
<td><p>Squillo simultaneo consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
</tr>
</tbody>
</table>

  
Nella tabella seguente viene illustrato se Location-Based routing consente lo squillo simultaneo a un endpoint PSTN da diversi utenti di Lync (ad esempio, Lync User 2, Lync User 4 e così via).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione anello simultaneo</th>
<th>Lync User 2</th>
<th>Lync User 4</th>
<th>Utente di Lync nel sito di rete non abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Telefono cellulare Lync User 1 (endpoint PSTN)</p></td>
<td><p>Chiamata instradata tramite il criterio di routing vocale di Network site 1 e l'uscita tramite il gateway del sito 1</p></td>
<td><p>Chiamata instradata tramite il criterio di routing vocale di Network site 2 e l'uscita tramite il gateway del sito 2</p></td>
<td><p>La chiamata viene instradata tramite il criterio vocale chiamante e l'uscita tramite un gateway PSTN non è abilitata per il routing Location-Based</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing Location-Based in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

