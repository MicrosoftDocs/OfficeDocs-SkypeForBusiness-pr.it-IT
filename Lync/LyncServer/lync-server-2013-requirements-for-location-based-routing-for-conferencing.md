---
title: 'Lync Server 2013: requisiti per il routing in base alla posizione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisiti per il routing in base alla posizione per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-19_

Di seguito sono riportati i requisiti necessari per l'installazione e la configurazione dell'applicazione per le conferenze di routing basata sulla posizione:

  - L'aggiornamento cumulativo 2 di Lync Server 2013 deve essere distribuito in tutti i server o pool della topologia.

<div>


> [!NOTE]  
> Se un server o un pool di Lync nella topologia non dispone di un aggiornamento cumulativo 2 o superiore di Lync Server 2013 installato, non è possibile garantire l'applicazione del routing basato sulla posizione delle riunioni di Lync.



</div>

  - Il routing in base alla posizione di Lync Server 2013 è prerequisito per l'applicazione di conferenza di routing basata sulla posizione. Per ulteriori informazioni sulla configurazione del routing in base alla posizione di Lync Server 2013, fare riferimento a [configurazione del routing in base alla posizione](lync-server-2013-configuring-location-based-routing.md).

  - I requisiti dell'applicazione per le conferenze di routing in base alla posizione sono gli stessi dei requisiti per il routing in base alla posizione di Lync Server 2013. Per ulteriori informazioni, fare riferimento alla [pianificazione del routing in base alla posizione](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Server supportati

L'applicazione per le conferenze di routing basata sul percorso richiede che Lync Server 2013 Cumulative Update 2 sia distribuito in tutti i pool Front-end e server Standard Edition nella topologia. Se Lync Server 2013 Cumulative Update 2 non è installato in alcuni server Lync nella topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni di Lync e ai trasferimenti di chiamata consultiva.

La tabella seguente identifica la combinazione dei ruoli del server e delle versioni che supportano il routing basato sulla posizione.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versione pool Front-End</p></td>
<td><p>Versione Mediation Server</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 aggiornamento cumulativo 2</p></td>
<td><p>Lync Server 2013 aggiornamento cumulativo 2</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 aggiornamento cumulativo 2</p></td>
<td><p>Lync Server 2013 aggiornamento cumulativo 1</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 aggiornamento cumulativo 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 aggiornamento cumulativo 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 aggiornamento cumulativo 1</p></td>
<td><p>Qualsiasi</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Qualsiasi</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Qualsiasi</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Client supportati

I client Lync che supportano il routing in base alla posizione delle riunioni di Lync sono gli stessi client che supportano il routing in base alla posizione di Lync Server 2013. Per ulteriori informazioni, fare riferimento al [supporto per client e server per il routing in base alla posizione](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisiti di Mediation Server per i trasferimenti di chiamata consultiva

L'applicazione per le conferenze di routing in base alla posizione richiede la distribuzione di Mediation Server autonomi per applicare restrizioni di routing basate sul percorso nei trasferimenti di chiamata consultiva.

Per applicare il routing in base alla posizione dei trasferimenti di chiamata consultiva, è necessario che il Mediation Server sia associato a un solo peer Mediation Server (ad esempio PBX, gateway SIP e così via) nelle aree di rete in cui è necessario il routing basato sulla posizione. Se sono distribuiti altri peer di Mediation Server nella stessa area di rete, è necessario che il peer Mediation Server sia associato a un Mediation Server diverso. Questo requisito è dettagliato come indicato di seguito:

  - Singolo Mediation Server per più peer di Mediation Server quando un trasferimento di chiamata consultivo viene instradato a un peer di Mediation Server tramite un Mediation Server configurato con più trunk SIP su più peer (ad esempio, PBX e gateway), la consultazione il trasferimento di chiamata è bloccato per impedire il bypass a pedaggio PSTN se il trasferimento delle chiamate consultive è consentito tramite alcuni trunk SIP ma non consentito tramite altri trunk SIP.
    
    Ad esempio, nel caso di un singolo Mediation Server per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non è consentita anche se non si trova in un potenziale Tol PSTN l bypassare.

  - Mediation Server distinti per peer di Mediation Server
    
    Quando un trasferimento consultivo è destinato a un peer di Mediation Server, il trasferimento consultivo verrà valutato rispetto al peer di Mediation Server singolo gestito dal Mediation Server. La chiamata non è consentita o consentita in base alle sue potenzialità di incorrere in un bypass a pedaggio PSTN indipendentemente da tutti gli altri peer del server di Mediation nel sito in cui sono serviti da server Mediation distinti.
    
    Ad esempio, nel caso di un Mediation Server separato per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata sarà consentita perché non si trova in un eventuale bypass a pedaggio PSTN. conoscenza.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funzionalità non supportate dall'applicazione per le conferenze di routing in base alla posizione

Le funzionalità seguenti non sono supportate dall'applicazione per le conferenze di routing in base alla posizione:

  - Servizi di conferenza telefonica con accesso esterno. Impossibile applicare il routing in base alla posizione per le conferenze telefoniche con accesso esterno. Qualsiasi richiesta di accesso esterno a una determinata conferenza non verrà limitata dal routing basato sulla posizione anche se l'organizzatore di conferenze è un utente di Lync abilitato per il routing in base alla posizione.

  - È consigliabile non eseguire il provisioning dei numeri di accesso per le conferenze nelle aree in cui devono essere applicate restrizioni di routing basate sul percorso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

