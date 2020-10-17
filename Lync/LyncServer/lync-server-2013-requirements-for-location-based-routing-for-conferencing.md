---
title: 'Lync Server 2013: requisiti per il routing Location-Based per le conferenze'
description: 'Lync Server 2013: requisiti per il routing Location-Based per le conferenze.'
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
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542522"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisiti per il routing Location-Based per le conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-19_

Di seguito sono riportati i requisiti necessari per l'installazione e la configurazione dell'applicazione di conferenza di routing Location-Based:

  - L'aggiornamento cumulativo 2 di Lync Server 2013 deve essere distribuito in tutti i server o pool della topologia.

<div>


> [!NOTE]  
> Se un server o un pool Lync nella topologia non dispone di un aggiornamento cumulativo 2 o superiore di Lync Server 2013 installato, non è possibile garantire l'applicazione del routing Location-Based delle riunioni di Lync.



</div>

  - Lync Server 2013 Location-Based routing è un requisito indispensabile per Location-Based applicazione per le conferenze di routing. Per ulteriori informazioni sulla configurazione di Lync Server 2013 Location-Based routing, vedere [Configuring Location-Based routing](lync-server-2013-configuring-location-based-routing.md).

  - I requisiti di Location-Based applicazione di routing Conferencing sono gli stessi dei requisiti per il routing di Lync Server 2013 Location-Based. Per ulteriori informazioni, vedere [Planning for Location-Based routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Server supportati

L'applicazione per le conferenze di routing Location-Based richiede che l'aggiornamento cumulativo 2 di Lync Server 2013 sia distribuito in tutti i pool di Front-End e nei server Standard Edition nella topologia. Se Lync Server 2013 Cumulative Update 2 non è installato in alcuni server Lync nella topologia, Location-Based restrizioni di routing non possono essere applicate completamente alle riunioni di Lync e ai trasferimenti di chiamata consultiva.

La tabella seguente identifica la combinazione di ruoli del server e versioni che supportano il routing Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versione del pool di Front-End</p></td>
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

I client Lync che supportano Location-Based il routing di riunioni di Lync sono gli stessi client che supportano Lync Server 2013 Location-Based routing. Per ulteriori informazioni, fare riferimento al [supporto per client e server per il Routing Location-Based](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisiti di Mediation Server per i trasferimenti di chiamata consultiva

L'applicazione di routing per le conferenze di Location-Based richiede la distribuzione di Mediation Server autonomi per applicare Location-Based limitazioni del routing per i trasferimenti di chiamata consultiva.

Per applicare Location-Based routing dei trasferimenti di chiamata consultiva, è necessario che il Mediation Server sia associato a un solo peer Mediation Server (ad esempio PBX, gateway SIP e così via) nelle aree di rete in cui è necessario Location-Based il routing. Se sono distribuiti altri peer di Mediation Server nella stessa area di rete, è necessario che il peer Mediation Server sia associato a un Mediation Server diverso. Questo requisito è dettagliato come indicato di seguito:

  - Singolo Mediation Server per più peer di Mediation Server quando un trasferimento di chiamata consultivo viene instradato a un peer di Mediation Server tramite un Mediation Server configurato con più trunk SIP su più peer (ad esempio, PBX e gateway), il trasferimento delle chiamate consultive è bloccato per impedire il bypass a pedaggio PSTN se il trasferimento delle chiamate consultive è consentito tramite alcuni trunk SIP ma non consentito tramite altri trunk SIP.
    
    Ad esempio, nel caso di un singolo Mediation Server per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non è consentita anche se non si trova in un eventuale bypass a pedaggio PSTN.

  - Mediation Server distinti per peer di Mediation Server
    
    Quando un trasferimento consultivo è destinato a un peer di Mediation Server, il trasferimento consultivo verrà valutato rispetto al peer di Mediation Server singolo gestito dal Mediation Server. La chiamata non è consentita o consentita in base alle sue potenzialità di incorrere in un bypass a pedaggio PSTN indipendentemente da tutti gli altri peer del server di Mediation nel sito in cui sono serviti da server Mediation distinti.
    
    Ad esempio, nel caso di un Mediation Server separato per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.
    
      - Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata sarà consentita perché non si trova in un eventuale bypass a pedaggio PSTN.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funzionalità non supportate dall'applicazione di routing per le conferenze di Location-Based

Le funzionalità seguenti non sono supportate dall'applicazione di Location-Based di routing per i servizi di conferenza:

  - Servizi di conferenza telefonica con accesso esterno. Non è possibile applicare il routing Location-Based per le conferenze telefoniche con accesso esterno. Qualsiasi richiesta di accesso esterno a una determinata conferenza non verrà limitata da Location-Based routing anche se l'organizzatore di conferenze è un utente di Lync abilitato per il routing Location-Based.

  - È consigliabile non eseguire il provisioning dei numeri di accesso per le conferenze nelle aree in cui devono essere applicate le restrizioni di routing Location-Based.

</div>

</div>

<span> </span>

</div>

</div>

</div>

