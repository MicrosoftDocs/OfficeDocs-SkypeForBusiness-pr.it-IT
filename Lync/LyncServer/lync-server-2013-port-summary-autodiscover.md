---
title: 'Lync Server 2013: riepilogo della porta-individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Riepilogo della porta-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-05_

Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, se pubblicato in `lyncdiscover.<domain>` DNS `lyncdiscoverinternal.<domain>` con i record host, può essere usato dai client per individuare le caratteristiche di Lync Server. Per consentire ai dispositivi mobili che usano Lync mobile di usare l'individuazione automatica, potrebbe essere prima necessario modificare gli elenchi di nomi alternativi del soggetto del certificato in qualsiasi Director e front end server che gestisce il servizio di individuazione automatica. Può essere inoltre necessario modificare gli elenchi di nomi alternativi oggetto nei certificati usati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

La decisione relativa all'uso di elenchi di nomi alternativi oggetto nei proxy inversi si basa sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:

  - **Pubblicate sulla porta 80**   per i dispositivi mobili non sono necessarie modifiche ai certificati se la query iniziale per il servizio di individuazione automatica si verifica sulla porta 80. Il motivo è che i dispositivi mobili che utilizzano Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un amministratore o a un server front-end sulla porta 8080 internamente.

  - **Pubblicato in porta 443**   l'elenco dei nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve `lyncdiscover.<sipdomain>` contenere una voce per ogni dominio SIP all'interno dell'organizzazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Per le nuove installazioni o gli aggiornamenti da Lync Server 2010 in cui è stata distribuita la mobilità, è stata usata la porta 80 per l'individuazione automatica del servizio di mobilità oppure i certificati ristampati con il nome dell'oggetto e i nomi alternativi oggetto in posizione. Esaminare i certificati del Director e del front end server per confermare il percorso scelto.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Dettagli del firewall per il server proxy inverso: interfaccia esterna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo/TCP o UDP/porta</th>
<th>Indirizzo IP di origine</th>
<th>Indirizzo IP di destinazione</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Listener proxy inverso</p></td>
<td><p>Opzionale Reindirizzamento a HTTPS se l'utente immette http://&lt;publishedSiteFQDN.&gt; Obbligatorio anche se si usa Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che esegue Lync in situazioni in cui l'organizzazione non vuole modificare il certificato della regola di pubblicazione del servizio Web esterno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Listener proxy inverso</p></td>
<td><p>Download rubrica, servizio query Web Rubrica, individuazione automatica, aggiornamenti client, contenuto riunione, aggiornamenti dispositivi, espansione di gruppo, Office Web Apps per conferenze, servizi di conferenza telefonica con accesso esterno e riunioni.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Dettagli del firewall per il server proxy inverso: interfaccia interna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo/TCP o UDP/porta</th>
<th>Indirizzo IP di origine</th>
<th>Indirizzo IP di destinazione</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interfaccia proxy inverso interno</p></td>
<td><p>Server front-end, pool Front-End, Director, pool di Director, Office Web Apps per le conferenze</p></td>
<td><p>Obbligatorio se si usa il servizio di individuazione automatica per i dispositivi mobili che esegue Lync in situazioni in cui l'organizzazione non vuole modificare il certificato della regola di pubblicazione del servizio Web esterno. Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaccia proxy inverso interno</p></td>
<td><p>Server front-end, pool Front-End, Director, pool di Director, Office Web Apps per le conferenze</p></td>
<td><p>Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

