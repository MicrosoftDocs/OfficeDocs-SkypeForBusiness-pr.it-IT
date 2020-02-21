---
title: 'Lync Server 2013: riepilogo delle porte-proxy inverso'
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
ms.openlocfilehash: 6259614da322e79f69db40441125b28c95e379c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo delle porte-proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-15_

Per il proxy inverso sono previsti requisiti minimi per il firewall, la porta e il protocollo.

  - I requisiti del firewall esterno sono HTTPS/TCP/443 e il protocollo HTTP/TCP/80 facoltativo. HTTPS viene utilizzato per le comunicazioni protette SSL e TLS tramite il proxy inverso. HTTP viene utilizzato se si sceglie di consentire l'accesso al servizio di individuazione automatica quando si modificano i certificati potrebbe risultare difficile o non giustificato il costo.

  - I client prevedono di contattare il server Office Web Apps su HTTPS. Il server Office Web Apps prevede la comunicazione da client interni su HTTPS/TCP/443. La configurazione consigliata consiste nel consentire HTTPS/TCP/443 dal proxy inverso al server Office Web Apps.

  - La porta 8080 viene utilizzata per instradare il traffico dall'interfaccia interna del proxy inverso al front end server, all'IP virtuale del pool Front End (VIP) o al VIP del pool di Director o Director facoltativo. La porta TCP 8080 è obbligatoria per i dispositivi mobili che eseguono Lync per individuare il servizio di individuazione automatica in situazioni in cui la modifica del certificato della regola di pubblicazione dei servizi Web esterni è indesiderata (ad esempio, se si dispone di un numero elevato di domini SIP). Se si sceglie di acquisire nuovi certificati con le voci SAN necessarie, la porta TCP 8080 non è necessaria ed è facoltativa.

  - La porta 4443 viene utilizzata per il traffico dall'interfaccia interna del proxy inverso al front end server, all'IP virtuale del pool Front End (VIP) o al VIP del pool di Director o Director facoltativo
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Non confondere l'4443 su TCP dal proxy inverso alla distribuzione interna per la porta 4443 su traffico TCP dal server Standard Edition o dal pool Front end che gestisce il ruolo dell'archivio di gestione centrale.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Informazioni dettagliate sulle porte e sui protocolli

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
<td><p>Optional Reindirizzamento a HTTPS se l'utente immette http://&lt;publishedSiteFQDN.&gt;</p>
<p>Necessario anche se si utilizza Office Web Apps per le conferenze e il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</p></td>
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
<td><p>Front End Server, pool Front End, Director, pool di Director</p></td>
<td><p>Obbligatorio se si utilizza il servizio di individuazione automatica per i dispositivi mobili che eseguono Lync in situazioni in cui l'organizzazione non desidera modificare il certificato della regola di pubblicazione dei servizi Web esterni.</p>
<p>Il traffico inviato alla porta 80 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 8080 dall'interfaccia interna del proxy inverso, in modo che il pool di servizi Web possa distinguerlo dal traffico della rete interna.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>Front End Server, pool Front End, Director, pool di Director</p></td>
<td><p>Il traffico inviato alla porta 443 nell'interfaccia esterna del proxy inverso viene reindirizzato a un pool sulla porta 4443 dall'interfaccia interna del proxy inverso, in modo che i servizi Web del pool possano distinguerlo dal traffico Web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
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

