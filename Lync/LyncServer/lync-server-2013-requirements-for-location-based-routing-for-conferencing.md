---
title: 'Lync Server 2013: requisiti per il routing basato sulla posizione per i servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisiti per il routing basato sulla posizione per i servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-19_

Di seguito sono riportati i requisiti necessari per l'installazione e la configurazione dell'applicazione di conferenza di routing basata sulla posizione:

  - L'aggiornamento cumulativo 2 di Lync Server 2013 deve essere distribuito in tutti i server o i pool della topologia.

<div>


> [!NOTE]  
> Se un server o un pool di Lync nella topologia non ha installato Lync Server 2013 aggiornamento cumulativo 2 o versione successiva, non è possibile garantire l'applicazione del routing basato sulla posizione delle riunioni Lync.



</div>

  - Il routing basato sulla posizione di Lync Server 2013 è un requisito predefinito per l'applicazione di conferenza di routing basata sulla posizione. Per altre informazioni sulla configurazione del routing basato sulla posizione di Lync Server 2013, vedere [configurazione del routing basato sulla posizione](lync-server-2013-configuring-location-based-routing.md).

  - I requisiti dell'applicazione per i servizi di conferenza di routing basati sulla posizione corrispondono ai requisiti per il routing basato sulla posizione di Lync Server 2013. Per altre informazioni, vedere [pianificazione per il routing basato sulla posizione](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Server supportati

L'applicazione per i servizi di conferenza di routing basata sulla posizione richiede che l'aggiornamento cumulativo 2 di Lync Server 2013 sia distribuito in tutti i pool Front-end e nei server Standard Edition della topologia. Se l'aggiornamento cumulativo 2 di Lync Server 2013 non è installato in alcuni server Lync della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni di Lync e ai trasferimenti delle chiamate consultive.

La tabella seguente identifica la combinazione di ruoli server e versioni che supportano il routing basato sulla posizione.


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
<td><p>Supportati</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamento cumulativo 2 di Lync Server 2013</p></td>
<td><p>Aggiornamento cumulativo 2 di Lync Server 2013</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamento cumulativo 2 di Lync Server 2013</p></td>
<td><p>Aggiornamento cumulativo 1 di Lync Server 2013</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamento cumulativo 2 di Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamento cumulativo 2 di Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamento cumulativo 1 di Lync Server 2013</p></td>
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

I client Lync che supportano il routing basato sulla posizione delle riunioni Lync sono gli stessi client che supportano il routing basato sulla posizione di Lync Server 2013. Per altre informazioni, fare riferimento al [supporto client e server per il routing basato sulla posizione](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisiti di Mediation Server per i trasferimenti di chiamate consultive

L'applicazione per i servizi di conferenza di routing basata sulla posizione richiede la distribuzione di server di mediazione autonomi per applicare restrizioni di routing basate sul percorso per i trasferimenti di chiamate consultive.

Per applicare il routing basato sulla posizione dei trasferimenti delle chiamate consultive, il Mediation Server deve essere associato a un solo peer di Mediation Server (ad esempio PBX, gateway SIP e così via) nelle aree di rete in cui è necessario un routing basato sulla posizione. Se altri peer di Mediation Server vengono distribuiti nella stessa area di rete, il peer di Mediation Server deve essere associato a un Mediation Server diverso. Questo requisito è dettagliato come segue:

  - Singolo Mediation Server per più peer di Mediation Server quando un trasferimento di una chiamata consultiva viene indirizzato a un peer di Mediation Server tramite un Mediation Server configurato con più trunk SIP in più peer (ad esempio, PBX e gateway), le consultazioni il trasferimento delle chiamate è bloccato per evitare l'esclusione del pedaggio PSTN se il trasferimento delle chiamate consultive è consentito tramite alcuni trunk SIP ma non è consentito tramite altri trunk SIP.
    
    Ad esempio, nel caso di un singolo Mediation Server che assiste un peer del gateway PSTN Mediation Server e un peer di Mediation Server PBX, verrà osservato il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire l'esclusione del pedaggio PSTN.
    
      - Quando un utente di Lync di un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non è consentita, anche se non si trova in un potenziale Tol PSTN l bypassando.

  - Separare i server di mediazione per peer di Mediation Server
    
    Quando un trasferimento consultivo è destinato a un peer di Mediation Server, il trasferimento consultivo verrà valutato in base al peer di mediazione server singolo gestito dal Mediation Server. La chiamata non è consentita o consentita in base alle sue potenzialità di incorrere in un telepedaggio PSTN indipendentemente da tutti gli altri peer del server di mediazioni nel sito mentre vengono serviti da server di mediazione distinti.
    
    Ad esempio, nel caso di un server di mediazione separato che assiste un peer di mediazione del gateway PSTN e un peer di Mediation Server PBX, verrà osservato il comportamento seguente:
    
      - Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire l'esclusione del pedaggio PSTN.
    
      - Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata sarà consentita perché non viene incorrere in un eventuale bypass a pedaggio PSTN Ing.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funzionalità non supportate dall'applicazione per i servizi di conferenza di routing basato sulla posizione

Le funzionalità seguenti non sono supportate dall'applicazione di conferenza di routing basata sulla posizione:

  - Servizi di conferenza telefonica con accesso esterno. Il routing basato sulla posizione non può essere applicato per i servizi di conferenza telefonica con accesso esterno. Qualsiasi richiesta di accesso esterno a una conferenza specificata non verrà limitata dal routing basato sulla posizione, anche se l'organizzatore di conferenze è un utente di Lync abilitato per il routing basato sulla posizione.

  - È consigliabile non eseguire il provisioning di numeri di accesso alle conferenze nelle aree in cui devono essere applicate restrizioni di routing basate sulla posizione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

