---
title: Supporto di Lync Server 2013 per la connettività di messaggistica istantanea pubblica
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
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Supporto per la connettività di messaggistica istantanea pubblica

Questo articolo fornisce informazioni sul supporto per la connettività di messaggistica istantanea pubblica (PIC). PIC è una funzionalità di Microsoft Lync che consente alle organizzazioni di consentire agli utenti di Lync di connettersi con utenti di determinati servizi di messaggistica istantanea pubblica tramite i client e le identità di Lync.

Gli utenti finali traggono vantaggio dall'essere in grado di connettersi con clienti, partner e fornitori in base alle proprie condizioni. Beneficia del supporto di un singolo client di comunicazioni in tempo reale mantenendo le funzionalità di controllo, conformità e archiviazione di Lync. La connettività Lync-Skype, [disponibile pubblicamente in maggio 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), si basa sull'eredità che Lync/Office Communications Server (OCS)/Live Communications Server (LCS) ha stabilito per la prima volta con pic per la connessione a MSN/Windows Live, AOL e Yahoo.Per altre informazioni sulla connettività Lync-Skype, vedere la [connettività Lync-Skype](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx). La Federazione con Windows Live, AOL e Yahoo si trova su un percorso verso la fine della vita.Questa pagina documenta lo stato di ogni servizio.

Per usare PIC, è necessario che i clienti attivino il servizio per ogni provider di servizi di messaggistica istantanea pubblica. I requisiti e i dettagli su come eseguire questa operazione dipendono dal provider di servizi di messaggistica istantanea e dal programma di licenze sottostante del cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft ha portato Windows Live Messenger e Skype insieme. In aprile 2013 gli utenti di Messenger venivano migrati in Skype upon Sign-in. I clienti di Lync che si affidano alla Federazione con Messenger continueranno a comunicare con i loro contatti di Messenger, anche dopo l'aggiornamento di questi contatti a Skype. Non c'è nulla che gli amministratori di Lync o gli utenti finali di Lync debbano eseguire per mantenere la continuità del servizio e la gestione di questa funzionalità in Lync rimanga la stessa per le comunicazioni con Messenger. 

Quando gli utenti di Messenger entrano in Skype usando i loro account Microsoft (ad esempio le stesse credenziali usate per Messenger) tutti i loro contatti di Messenger, inclusi i contatti di Lync federati, li seguono in Skype. È disponibile la condivisione di presenza e la messaggistica istantanea tra Skype e Lync per questi contatti. 

Lync-Skype Connectivity-l'aggiunta di contatti, la condivisione della presenza, la messaggistica istantanea e le chiamate audio tra Lync e utenti Skype-è ora disponibile anche per tutti i clienti di Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! e AOL Instant Messenger

Federazione con Yahoo\! e AOL si trovano entrambi su un percorso verso la fine del ciclo di vita per i clienti di Lync (e Office Communications Server). La capacità di Microsoft di prestare ognuno di questi servizi è stata condizionata al supporto di Yahoo\! e AOL, e gli accordi sottostanti sono tortuosi. Sia per Yahoo\! e AOL, il servizio continuerà fino al 2014 giugno.

  - **Yahoo** -Service continuerà attraverso il 2014 giugno e i clienti continueranno ad avere la licenza con la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL").A partire dal 1 ° settembre 2012, il PIC USL, non è più disponibile per l'acquisto di contratti nuovi o rinnovati.I clienti con licenze acquistate prima di questa data saranno in grado di continuare a eseguire la Federazione con Yahoo\! fino alla data di chiusura del servizio precedente o alla scadenza della licenza.Leggere [l'annuncio](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) nel Blog del team Lync.I clienti che hanno licenze PIC per accordi che si estendono oltre il 30 giugno 2014 riceveranno un credito in proporzione all'importo dei pagamenti che coprono il periodo di tempo successivo al 30 giugno 2014.

  - **AOL** -il 30 giugno 2014, il servizio connettività messaggistica istantanea di Lync ("pic") non sarà più disponibile.Per limitare la disgregazione del cliente al termine del servizio, è stato interrotto il provisioning di altri domini del cliente. Fino al 30 giugno 2014 i clienti non devono eseguire alcuna operazione per continuare a supportare le comunicazioni federate con AIM. Oltre questa data (o per i clienti che desiderano eseguire il provisioning di altri domini nel frattempo), un servizio sostitutivo è disponibile direttamente da AOL. Per altre informazioni sul nuovo servizio di AOL, vedere [creazione di una federazione diretta con AIM](http://aimenterprise.aol.com/pic.php)  (apre una nuova pagina in AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Riepilogo del provider di messaggistica istantanea pubblica

La tabella seguente contiene un riepilogo dei provider di servizi di messaggistica istantanea pubblici, le funzionalità federative con Lync e i requisiti di licenza.


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
<th>Requisiti per le licenze</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Messaggistica istantanea, presenza, audio</p></td>
<td><p>Licenze di accesso client di Lync Server, Lync Online piano 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Messaggistica istantanea, presenza, audio/video</p></td>
<td><p>Licenze di accesso client di Lync Server (supportate purché WLM sia in commercio)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Messaggistica istantanea, presenza</p></td>
<td><p>Licenze di accesso client di Lync Server; supportato tramite 2014 giugno per i clienti esistenti.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Messaggistica istantanea, presenza</p></td>
<td><p>È necessaria una licenza aggiuntiva per l'abbonamento a Microsoft Lync Public IM Connectivity ("PIC USL") oltre alle licenze di accesso client di Lync Server. A partire dal listino prezzi di settembre 2012, il PIC USL non è più disponibile per l'acquisto. I clienti con licenze attive possono continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio il 30 giugno 2014.</p></td>
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

