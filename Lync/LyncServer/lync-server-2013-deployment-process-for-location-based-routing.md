---
title: 'Lync Server 2013: Processo di distribuzione per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Processo di distribuzione per il routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Questo argomento offre una panoramica del processo relativo alla configurazione del routing basato sulla posizione. È necessario distribuire Lync Server Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare il routing basato sulla posizione. I componenti necessari per il routing basato sulla posizione sono già installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="location-based-routing-deployment-process"></a>Processo di distribuzione del routing basato sulla posizione

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Distribuzione di VoIP aziendale</p></td>
<td><ul>
<li><p>Configurare Trunks</p></li>
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
<li><p>Associa le subnet con i siti di rete</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Informazioni sulle aree geografiche, i siti e le subnet di rete<br />
Creare o modificare un'area di rete<br />
Creare o modificare un sito di rete<br />
Associare una subnet a un sito di rete</p></td>
</tr>
<tr class="even">
<td><p>Configurare il routing basato sulla posizione</p></td>
<td><ul>
<li><p>Creare criteri di routing vocale</p></li>
<li><p>Definire una configurazione trunk separata per tronco</p></li>
<li><p>Modificare i criteri vocali</p></li>
<li><p>Abilitare la configurazione del routing basata sulla posizione</p></li>
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

La distribuzione seguente viene usata per illustrare ulteriormente i meccanismi abilitati dal routing basato sulla posizione.

![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Chiamate PSTN in arrivo

Un amministratore può abilitare il trunk definito per instradare le chiamate al "gateway del sito 1" per il routing basato sulla posizione e associare il "gateway del sito 1" al sito 1. Una volta abilitata, le chiamate instradate tramite "gateway sito 1" verranno indirizzate solo agli utenti che si trovano nel sito 1. Tutte le chiamate instradate tramite il trunk "sito 1 gateway" destinato agli utenti in un sito diverso, ad esempio il sito 2, verranno bloccate per evitare il bypass PSTN.

Tutte le chiamate PSTN in arrivo tramite "sito 1 gateway" possono essere instradate solo agli endpoint presenti nel sito 1. Ad esempio, quando "Lync User 1" passa al sito 2, tutte le chiamate PSTN in arrivo tramite "sito 1 gateway" non verranno indirizzate agli endpoint "Lync User 1" presenti nel sito 2. La stessa regola di routing si applica se "Lync User 1" si sposta in un sito di rete sconosciuto in cui non è possibile determinare la posizione dell'utente.

La tabella seguente illustra l'esperienza utente di "Lync User 1" in questo contesto.


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
<th>Endpoint degli utenti di Lync 1 situati nel sito di rete 1</th>
<th>Endpoint degli utenti di Lync 1 situati nel sito di rete 2</th>
<th>Endpoint di Lync User 1 situati nel sito di rete sconosciuto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate PSTN in ingresso per l'utente Lync 1</p></td>
<td><p>Le chiamate vengono instradate agli endpoint in questa posizione</p></td>
<td><p>Le chiamate non vengono instradate agli endpoint in questa posizione</p></td>
<td><p>Le chiamate non vengono instradate agli endpoint in questa posizione</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Chiamate PSTN in uscita

Si fa riferimento a route vocali sia nei criteri vocali assegnati direttamente agli utenti, sia nei criteri di routing vocale assegnati ai siti di rete. Entrambi i criteri contengono riferimenti alle route, che possono essere usati per instradare una chiamata in modo diverso. Un amministratore può ad esempio definire un criterio di routing vocale per tutti gli utenti che si trovano nel sito di rete 1 per instradare tutte le chiamate in uscita tramite il gateway "sito 1", mentre il criterio vocale di alcuni utenti definisce una route per tutte le chiamate in uscita tramite il "sito 2 gateway". Mentre questi utenti si trovano nel sito di rete 1, le chiamate in uscita verranno instradate tramite il "gateway del sito 1".

Quando un utente si trova in un sito di rete configurato per il routing basato sulla posizione, la route dei criteri di routing vocale del sito di rete sostituisce la route dei criteri vocali dell'utente. Questa regola è particolarmente utile per gli utenti che si trasferiscono temporaneamente in un sito diverso. In questo caso specifico un utente userà sempre un gateway locale nella propria posizione; Se "Lync User 3" si trova in "sito 2", tutte le sue chiamate in uscita verranno instradate tramite "gateway del sito 2", ma se si reca nel sito 1, tutte le chiamate in uscita inserite mentre è al sito 1 verranno instradate attraverso "sito 1 gateway".

La tabella seguente illustra l'esperienza utente di Lync User 1 che effettua una chiamata in uscita dai siti di rete seguenti.


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
<th>Sito di rete sconosciuto o non abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorizzazione delle chiamate in uscita</p></td>
<td><p>Criterio vocale di Lync User 1</p></td>
<td><p>Criterio vocale di Lync User 1</p></td>
<td><p>Criterio vocale di Lync User 1</p></td>
</tr>
<tr class="even">
<td><p>Routing delle chiamate in uscita</p></td>
<td><p>Criteri di routing vocale del sito 1</p></td>
<td><p>Criteri di routing vocale del sito 2</p></td>
<td><p>Criteri vocali dell'utente e solo per i sistemi non abilitati per il routing basato sulla posizione</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Trasferimento e inoltro delle chiamate

Quando le chiamate vengono trasferite o inoltrate, il routing delle chiamate è influenzato dal routing basato sulla posizione.

Nella tabella seguente viene illustrato l'utente di Lync 1 che trasferisce o inoltra una chiamata PSTN a un altro utente Lync.


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
<th>Utente di Lync 2</th>
<th>Utente di Lync 4</th>
<th>L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente Lync 1</p></td>
<td><p>Inoltro di chiamata o trasferimento consentito</p></td>
<td><p>La chiamata inoltra o transfer non è consentita</p></td>
<td><p>La chiamata inoltra o transfer non è consentita</p></td>
</tr>
</tbody>
</table>

  
Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sulla modalità di instradamento della chiamata in base alla posizione dell'utente di Lync trasferito (Lync User 2, Lync User 4 e così via) in un endpoint PSTN


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpoint in cui viene trasferita o inoltrata la chiamata a</th>
<th>Utente di Lync 2</th>
<th>Utente di Lync 4</th>
<th>L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>La chiamata inoltra o transfer viene instradato attraverso i criteri di routing vocale del sito 1 e l'uscita tramite gateway del sito 1</p></td>
<td><p>La chiamata inoltra o transfer viene instradato attraverso i criteri di routing vocale del sito 2 e l'uscita tramite gateway del sito 2</p></td>
<td><p>Inoltro di chiamata o trasferimento viene instradato tramite il criterio vocale dell'utente di Lync e l'uscita tramite un gateway non abilitato per il routing basato sulla posizione (se disponibile)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Squillo simultaneo

Una volta configurato il routing basato sulla posizione nella topologia di esempio, vengono applicate le interazioni seguenti.

La tabella seguente illustra se il routing basato sulla posizione consente la chiamata simultanea per diversi utenti di Lync (ad esempio, Lync User 2, Lync User 4 e così via).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione chiamata PSTN in arrivo</th>
<th>Utente di Lync 2</th>
<th>Utente di Lync 4</th>
<th>L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente Lync 1</p></td>
<td><p>Squillo simultaneo consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
</tr>
</tbody>
</table>

  
La tabella seguente illustra se il routing basato sulla posizione consente la chiamata simultanea a un endpoint PSTN da diversi utenti di Lync, ad esempio Lync User 2, Lync User 4 e così via.


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
<th>Utente di Lync 2</th>
<th>Utente di Lync 4</th>
<th>L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync utente 1 cellulare (endpoint PSTN)</p></td>
<td><p>Chiamata instradata tramite il criterio di routing vocale di Network site 1 e l'uscita tramite gateway del sito 1</p></td>
<td><p>Chiamata instradata tramite il criterio di routing vocale di Network site 2 e l'uscita tramite gateway del sito 2</p></td>
<td><p>Chiamata instradata tramite il criterio vocale chiamante ed è in uscita tramite un gateway PSTN non abilitato per il routing basato sulla posizione</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

