---
title: 'Lync Server 2013: riepilogo delle porte-individuazione automatica'
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
ms.openlocfilehash: 635f8fca3b267fa2366b66b990ec0621f58f58e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Riepilogo delle porte-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-05_

Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, quando viene pubblicato `lyncdiscover.<domain>` in `lyncdiscoverinternal.<domain>` DNS utilizzando i record host e e, può essere utilizzato dai client per individuare le funzionalità di Lync Server. Per consentire ai dispositivi mobili che eseguono Lync mobile di utilizzare l'individuazione automatica, è possibile che sia necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi server Director e front end che esegue il servizio di individuazione automatica. Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

La decisione sull'eventuale utilizzo degli elenchi di nomi alternativi del soggetto nei proxy inversi è basata sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:

  - **Pubblicati sulla porta 80**   per i dispositivi mobili, non sono necessarie modifiche ai certificati se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80. Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un server Director o front end su porta 8080 internamente.

  - **Pubblicati sulla porta 443**   l'elenco dei nomi alternativi del soggetto sui certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni `lyncdiscover.<sipdomain>` deve contenere una voce per ogni dominio SIP all'interno dell'organizzazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Per le nuove installazioni o gli aggiornamenti da Lync Server 2010 in cui è stata distribuita la funzionalità di mobilità, è stata utilizzata la porta 80 per l'individuazione automatica del servizio per dispositivi mobili o i certificati riemessi con il nome soggetto e i nomi alternativi del soggetto corretti. Esaminare i certificati nel server Director e front end per confermare il percorso scelto.

    
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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Listener proxy inverso</p></td>
<td><p>Optional Reindirizzamento a HTTPS se l'utente immette http://&lt;publishedSiteFQDN.&gt; Necessario anche se si utilizza Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Listener proxy inverso</p></td>
<td><p>Download della Rubrica, servizio query Web della Rubrica, individuazione automatica, aggiornamenti dei client, contenuto delle riunioni, aggiornamenti dei dispositivi, espansione di gruppi, Office Web Apps per le conferenze, conferenze telefoniche con accesso esterno e riunioni.</p></td>
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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</p></td>
<td><p>Obbligatorio se si utilizza il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni. Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso, in modo che il pool di servizi Web possa distinguerlo dal traffico della rete interna.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>Front End Server, pool Front End, Director, pool di Director, Office Web Apps per le conferenze</p></td>
<td><p>Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso, in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

