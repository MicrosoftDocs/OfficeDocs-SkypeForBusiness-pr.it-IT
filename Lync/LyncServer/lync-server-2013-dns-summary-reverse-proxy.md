---
title: 'Lync Server 2013: Riepilogo di DNS - proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Riepilogo di DNS - proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-22_

Si configurano due schede di rete nel proxy inverso, come indicato di seguito:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisiti della scheda di rete proxy inverso

  - Esempio di **scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con 172.25.33.40 assegnati.
    
    Nessun gateway predefinito è definito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del proxy inverso a tutte le reti che contengono i server del pool Front-End di Lync Server, ad esempio da 172.25.33.0 a 192.168.10.0.

  - Esempio di **scheda di rete 2 (interfaccia esterna)**
    
    Alla scheda di rete viene assegnato un minimo di un indirizzo IP pubblico.
    
    Il gateway viene definito in punti al router o al firewall integrato nel perimetro esterno. (10.45.16.1 negli esempi di scenario)

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
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Listener assegnato per le risorse pubblicate esternamente</p></td>
<td><p>Servizi Web esterni dalla distribuzione interna. È possibile definire e creare record aggiuntivi per tutti i pool e i singoli server per qualsiasi dominio SIP che utilizzerà questo proxy inverso e ha definito servizi Web esterni.</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Listener assegnato per le risorse pubblicate esternamente</p></td>
<td><p>Servizi Web esterni per i pool di direttori o di Director nella distribuzione. Puoi definire il numero di amministratori che ci sono direttori distinti, di cui possono essere associati ad altri domini SIP.</p>
<div>

> [!IMPORTANT]  
> La definizione dei record DNS per la pubblicazione dei direttori non è un pool di front end o la decisione del direttore. Se si usano gli amministratori, è necessario definire e pubblicare sia il Director che i servizi Web esterni del pool Front-end. I tipi di traffico specifici (per l'autenticazione e altri usi) verranno inviati prima al Director, se sono definiti nella topologia.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Listener assegnato per le risorse pubblicate esternamente</p></td>
<td><p>Servizi di conferenza telefonica con accesso esterno pubblicati esternamente</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Listener assegnato per le risorse pubblicate esternamente</p></td>
<td><p>Conferenze pubblicate esternamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Listener assegnato per Office Web Apps Server</p></td>
<td><p>Server Office Web Apps distribuito internamente o nel perimetro e pubblicato per l'accesso client esterno</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Listener assegnato per le risorse pubblicate esternamente</p></td>
<td><p>Lync scopre il record esterno per l'individuazione automatica pubblicata esternamente e include mobilità, Microsoft Lync Web App e Scheduler Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

