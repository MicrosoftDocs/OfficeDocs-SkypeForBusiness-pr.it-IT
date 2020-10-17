---
title: 'Lync Server 2013: Riepilogo di DNS-proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532143"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo DNS-proxy inverso in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-22_

È possibile configurare due schede di rete all'interno del proxy inverso in questo modo:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisiti relativi alla scheda di rete per proxy inverso

  - Esempio di **scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.40 assegnato.
    
    Nessun gateway predefinito definito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del proxy inverso a qualsiasi rete che contiene server del pool Front End di Lync Server (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - Esempio di **scheda di rete 2 (interfaccia esterna)**
    
    A questa scheda di rete viene assegnato almeno un indirizzo IP pubblico.
    
    Il gateway viene definito in modo da puntare al router o al firewall integrato nel perimetro esterno (10.45.16.1 in questi esempi di scenario).

### <a name="dns-records-required-for-reverse-proxy"></a>Record DNS necessari per il proxy inverso

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>FQDN</th>
<th>Indirizzo IP</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A esterno</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Listener assegnato per risorse pubblicate esternamente</p></td>
<td><p>Servizi Web esterni dalla distribuzione interna. È possibile definire e creare altri record per tutti i pool e singoli server per un dominio SIP che userà questo proxy inverso e dispone di servizi Web esterni definiti.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A esterno</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Listener assegnato per risorse pubblicate esternamente</p></td>
<td><p>Servizi Web esterni per i direttori o i pool di server Director nella distribuzione. È possibile definire il numero di amministratori che sono direttori distinti, di cui possono essere associati ad altri domini SIP.</p>
<div>

> [!IMPORTANT]  
> La definizione dei record DNS per e la pubblicazione dei direttori non è una decisione del pool Front end o del Director. Se si utilizzano i Director, è necessario definire e pubblicare sia il server Director che i servizi Web esterni del pool Front end. I tipi di traffico specifici (per l'autenticazione e altri utilizzi) verranno inviati prima al server Director, se definito nella topologia.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS/A esterno</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Listener assegnato per risorse pubblicate esternamente</p></td>
<td><p>Conferenza telefonica con accesso remoto pubblicata esternamente</p></td>
</tr>
<tr class="even">
<td><p>DNS/A esterno</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Listener assegnato per risorse pubblicate esternamente</p></td>
<td><p>Conferenze pubblicate esternamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A esterno</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Listener assegnato per il server Office Web Apps</p></td>
<td><p>Server Office Web Apps distribuito internamente o nel perimetro e pubblicato per l'accesso client esterno</p></td>
</tr>
<tr class="even">
<td><p>DNS/A esterno</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Listener assegnato per risorse pubblicate esternamente</p></td>
<td><p>Record esterno di individuazione di Lync per l'individuazione automatica pubblicata esternamente e include mobilità, Microsoft Lync Web App e Scheduler Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

