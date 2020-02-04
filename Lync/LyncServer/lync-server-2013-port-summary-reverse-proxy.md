---
title: 'Lync Server 2013: Riepilogo delle porte - proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo delle porte - proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-15_

Il proxy inverso ha requisiti minimi per il firewall e la porta/protocollo.

  - I requisiti del firewall esterno sono HTTPS/TCP/443 e l'opzione HTTP/TCP/80 facoltativa. HTTPS viene usato per le comunicazioni sicure SSL e TLS tramite il proxy inverso. HTTP viene usato se si sceglie di consentire l'accesso al servizio di individuazione automatica quando si modificano i certificati potrebbe risultare difficile o non giustificato il costo.

  - I client si aspettano di contattare il server Office Web Apps in HTTPS. Il server Office Web Apps prevede la comunicazione da client interni in HTTPS/TCP/443. La configurazione consigliata consiste nel consentire HTTPS/TCP/443 dal proxy inverso al server Office Web Apps.

  - La porta 8080 viene usata per indirizzare il traffico dall'interfaccia interna del proxy inverso al server front-end, all'IP virtuale del pool Front-End (VIP) o al VIP del pool di Director o Director facoltativi. La porta TCP 8080 è necessaria per i dispositivi mobili che utilizzano Lync per individuare il servizio di individuazione automatica in situazioni in cui la modifica del certificato della regola di pubblicazione del servizio Web esterno è indesiderata (ad esempio, se si ha un numero elevato di domini SIP). Se si sceglie di acquisire nuovi certificati con le voci SAN necessarie, la porta TCP 8080 non è necessaria ed è facoltativa.

  - La porta 4443 viene usata per il traffico dall'interfaccia interna del proxy inverso al server front-end, all'IP virtuale del pool Front End (VIP) o al pool di Director o Director facoltativo VIP
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Non confondere 4443 su TCP dal proxy inverso alla distribuzione interna per la porta 4443 tramite il traffico TCP dal server Standard Edition o dal pool Front-end che gestisce il ruolo di Central Management store.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Dettagli sulla porta e sul protocollo

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
<td><p>Opzionale Reindirizzamento a HTTPS se l'utente immette http://&lt;publishedSiteFQDN.&gt;</p>
<p>Obbligatorio anche se si usa Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che esegue Lync in situazioni in cui l'organizzazione non vuole modificare il certificato della regola di pubblicazione del servizio Web esterno.</p></td>
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
<td><p>Server front-end, pool Front-End, Director, pool di Director</p></td>
<td><p>Obbligatorio se si usa il servizio di individuazione automatica per i dispositivi mobili che esegue Lync in situazioni in cui l'organizzazione non vuole modificare il certificato della regola di pubblicazione del servizio Web esterno.</p>
<p>Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaccia proxy inverso interno</p></td>
<td><p>Server front-end, pool Front-End, Director, pool di Director</p></td>
<td><p>Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interfaccia proxy inverso interno</p></td>
<td><p>Office Web Apps per le conferenze</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

