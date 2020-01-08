---
title: 'Lync Server 2013: trasferimenti di routing e di chiamata consultiva basati sulla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Trasferimenti di routing e chiamate consultive basati sulla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-31_

Oltre a applicare il routing basato sulla posizione alle riunioni Lync, l'applicazione per le conferenze di routing basata sulla posizione impone restrizioni di routing basate sulla posizione per i trasferimenti di chiamate consultive in uscita agli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Lync). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente di Lync). L'utente A inserisce la chiamata con l'utente PSTN in attesa e chiama l'utente B. l'utente B accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento chiamate consultive**

Routing ![basato sul percorso per il diagramma di conferenza](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "basato sulla posizione del routing per i servizi di conferenza")

Quando un utente abilitato per il routing basato sulla posizione avvia un trasferimento di chiamata consultiva di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Lync A e l'altra tra l'utente di Lync e l'utente di Lync B. il comportamento seguente viene applicato dall'applicazione di conferenza di routing basata sulla posizione:

  - Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Lync B (vale a dire destinazione di trasferimento), il trasferimento della chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione dell'entità trasferita che si trova nello stesso sito di rete del trunk SIP che sta instradando la chiamata attiva all'endpoint PSTN.

  - Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova l'entità trasferita (utente di Lync B) o che l'entità trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva alla PSTN endpoint (ad esempio destinazione trasferimento chiamate) verrà bloccato.

La tabella seguente descrive il modo in cui le restrizioni di routing basate sulla posizione vengono applicate dall'applicazione di conferenza di routing basata sulla posizione per i trasferimenti di chiamate consultive. Anche se gli endpoint PBX non sono associati direttamente a un sito di rete, il trunk SIP a cui è connesso il PBX può essere assegnato a un sito di rete. Di conseguenza, l'endpoint PBX può essere associato indirettamente a un sito di rete.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Sito di rete della festa trasferita dalla chiamata</p></td>
<td><p>Sito di rete della destinazione del trasferimento delle chiamate</p></td>
<td><p>Comportamento</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Utenti di Lync in siti di rete diversi (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Utenti di Lync in un sito di rete sconosciuto</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Utenti Lync federati</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Endpoint PBX nello stesso sito (ad esempio il sito 1)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Endpoint PBX in siti diversi (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PBX nello stesso sito (ad esempio il sito 1)</p></td>
<td><p>Endpoint PSTN</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PBX in un sito diverso (ad esempio, sito 2)</p></td>
<td><p>Endpoint PSTN</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utenti di Lync in siti di rete diversi (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utenti di Lync in un sito di rete sconosciuto</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utenti Lync federati</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

