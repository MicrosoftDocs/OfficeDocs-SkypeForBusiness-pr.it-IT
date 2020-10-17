---
title: 'Lync Server 2013: trasferimenti di chiamate di routing e di chiamata consultiva Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513813"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Location-Based trasferimenti di chiamate di routing e consultivi in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-31_

Oltre a applicare il routing Location-Based alle riunioni di Lync, l'applicazione Location-Based routing Conferencing applica Location-Based limitazioni del routing per i trasferimenti di chiamata consultiva che vengono esportati negli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Lync). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente di Lync). Utente A posiziona la chiamata con l'utente PSTN in attesa e chiama l'utente B. User B che accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento delle chiamate consultive**

![Percorso basato sulla posizione per il diagramma delle conferenze](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Percorso basato sulla posizione per il diagramma delle conferenze")

Quando un utente abilitato per il routing Location-Based avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Lync A e l'altra tra l'utente Lync A e l'utente di Lync B. il comportamento seguente viene applicato dall'applicazione di conferenza di routing Location-Based:

  - Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Lync B (ovvero destinazione di trasferimento), il trasferimento di chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione della parte trasferita che si trova nello stesso sito di rete del trunk SIP che esegue il routing della chiamata attiva all'endpoint PSTN.

  - Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova l'entità trasferita (utente di Lync B) oppure che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva all'endpoint PSTN (ovvero l'obiettivo di trasferimento di chiamata) verrà bloccato.

Nella tabella seguente viene descritto in che modo Location-Based le restrizioni di routing vengono applicate dall'applicazione di conferenza di routing Location-Based per i trasferimenti di chiamata consultiva. Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, il trunk SIP a cui è connesso il sistema PBX può essere assegnato a un sito di rete. Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Sito di rete di una parte di chiamata trasferita</p></td>
<td><p>Sito di rete di destinazione trasferimento di chiamata</p></td>
<td><p>Comportamento</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Utente di Lync in diversi siti di rete (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Utente di Lync in un sito di rete sconosciuto</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Utente di Lync federato</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PSTN</p></td>
<td><p>Endpoint PBX nello stesso sito (ad esempio, sito 1)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Endpoint PBX in siti diversi (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo non sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PBX nello stesso sito (ad esempio, sito 1)</p></td>
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
<td><p>Utente di Lync in diversi siti di rete (ad esempio, sito 2)</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="even">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utente di Lync in un sito di rete sconosciuto</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint PBX in qualsiasi sito</p></td>
<td><p>Utente di Lync federato</p></td>
<td><p>Il trasferimento consultivo sarà consentito</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

