---
title: Supporto di Lync Server 2013 per la connettività di messaggistica istantanea pubblica
description: Lync Server 2013 supporta la connettività per la messaggistica istantanea pubblica.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4a58d71eb23012da960cf4505f1a55fd08df32c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573252"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Supporto per la connettività di messaggistica istantanea pubblica

In questo articolo vengono fornite informazioni sul supporto per la connettività di messaggistica istantanea pubblica (PIC). PIC è una funzionalità di Microsoft Lync che consente alle organizzazioni di consentire agli utenti di Lync di connettersi con utenti di alcuni servizi di messaggistica istantanea pubblica tramite i client e le identità di Lync.

Gli utenti finali usufruiscono della possibilità di connettersi con clienti, partner e fornitori nelle loro condizioni. Beneficia del supporto di un singolo client di comunicazione in tempo reale, mantenendo le funzionalità di controllo, conformità e archiviazione di Lync. Lync-Skype connettività, [disponibile pubblicamente nel maggio 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), si basa sull'eredità che Lync/Office Communications Server (OCS)/Live Communications Server (LCS) ha stabilito per la prima volta con pic in Connecting to MSN/Windows Live, AOL e Yahoo.Per ulteriori informazioni sulla connettività Lync-Skype, vedere la [connettività Lync-Skype](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx). La Federazione con Windows Live, AOL e Yahoo è su un percorso verso la fine della vita.Questa pagina documenta lo stato di ogni servizio.

Per utilizzare PIC, ai clienti è stato richiesto di attivare il servizio per ogni provider di servizi di messaggistica istantanea pubblica. I requisiti e i dettagli su come eseguire questa operazione dipendono dal provider di servizi di messaggistica istantanea e dal programma di gestione delle licenze sottostante del cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft ha portato Windows Live Messenger e Skype insieme. Nel 2013 aprile, gli utenti di Messenger sono stati migrati su Skype al momento dell'accesso. I clienti Lync che si basano sulla federazione con Messenger continueranno a essere in grado di comunicare con i contatti di Messenger, anche dopo l'aggiornamento a Skype da tali contatti. Non vi è nulla che gli amministratori di Lync o gli utenti finali di Lync devono eseguire per mantenere la continuità del servizio e la gestione di questa funzionalità all'interno di Lync rimane invariata per le comunicazioni con Messenger. 

Quando gli utenti di Messenger eseguono l'accesso a Skype usando i propri account Microsoft (ad esempio, le stesse credenziali utilizzate per Messenger), tutti i contatti di Messenger, compresi i contatti di Lync federati, li seguono in Skype. La condivisione della presenza e la messaggistica istantanea tra Skype e Lync per questi contatti sono disponibili. 

Lync-Skype connettività: l'aggiunta dei contatti, la condivisione della presenza, la messaggistica istantanea e le chiamate audio tra gli utenti di Lync e Skype sono disponibili anche per tutti i clienti di Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! e AOL Instant Messenger

Federazione con Yahoo\! e AOL sono entrambi su un percorso verso la fine del tempo per i clienti di Lync (e Office Communications Server). La capacità di Microsoft di fornire ognuno di questi servizi è stata subordinata al supporto da Yahoo\! e AOL e gli accordi sottostanti sono in calo. Sia per Yahoo\! e AOL, il servizio continuerà fino al 2014 giugno.

  - **Yahoo** -Service continuerà fino al 2014 giugno e i clienti continuano a dover essere concessi in licenza con la licenza di sottoscrizione utente di Microsoft Lync Public IM Connectivity ("PIC USL").Al 1 ° settembre 2012, il PIC USL, non è più disponibile per l'acquisto per i contratti nuovi o di rinnovo.I clienti con licenze acquistate prima di questa data saranno in grado di continuare a eseguire la Federazione con Yahoo\! fino alla data di chiusura del servizio o alla scadenza della licenza.Leggere [l'annuncio](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) nel Blog del team di Lync.I clienti che dispongono di licenze PIC su contratti che si estendono oltre il 30 giugno 2014 riceveranno un credito in proporzione all'ammontare dei pagamenti relativi al periodo di tempo successivo al 30 giugno 2014.

  - **AOL** -il 30 giugno 2014, il servizio di connettività di messaggistica istantanea di Lync ("pic") non sarà più disponibile.Per limitare la disgregazione del cliente al termine del servizio, è stato interrotto il provisioning di ulteriori domini dei clienti. Fino al 30 giugno 2014, i clienti non devono fare nulla per continuare a supportare le comunicazioni federate con AIM. Oltre a questa data (o per i clienti che desiderano eseguire il provisioning di ulteriori domini nel frattempo), un servizio sostitutivo è disponibile direttamente da AOL. Per ulteriori informazioni sul nuovo servizio di AOL, vedere [establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)    (apre una nuova pagina in AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Riepilogo del provider di messaggistica istantanea pubblica

Nella tabella seguente viene fornito un riepilogo dei provider di servizi di messaggistica istantanea pubblica, le funzionalità di federazione con Lync e i requisiti di licenza.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Provider di servizi di messaggistica istantanea pubblica</th>
<th>Funzionalità federate</th>
<th>Requisiti relativi alle licenze</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Messaggistica istantanea, presenza, audio</p></td>
<td><p>Licenze di accesso client di Lync Server, Lync Online, piano 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Messaggistica istantanea, presenza, audio/video</p></td>
<td><p>Licenze di accesso client di Lync Server (supportate fino a quando WLM è nel mercato)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Messaggistica istantanea, presenza</p></td>
<td><p>Licenze di accesso client di Lync Server; supportato fino al 2014 giugno per i clienti esistenti.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Messaggistica istantanea, presenza</p></td>
<td><p>Richiede ulteriore licenza di sottoscrizione per l'utente di connettività per messaggistica istantanea pubblica di Microsoft Lync ("PIC USL") oltre alle licenze di accesso client di Lync Server. Al listino prezzi di settembre 2012, il PIC USL non è più disponibile per l'acquisto. I clienti con licenze attive sono in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio del 30 giugno 2014.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

