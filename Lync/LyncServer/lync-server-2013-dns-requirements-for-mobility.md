---
title: 'Lync Server 2013: requisiti DNS per la mobilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisiti DNS per la mobilità con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-13_

Quando si distribuisce la funzionalità di mobilità di Lync Server 2013, è possibile usare i nuovi URL disponibili con il servizio di individuazione automatica di Microsoft Lync Server 2013 oppure usare gli URL dei servizi Web esistenti. Se usi gli URL esistenti, gli utenti devono immettere manualmente gli URL nelle impostazioni del dispositivo mobile. Questa opzione viene in genere usata per la risoluzione dei problemi. Quando si usano i nuovi URL, i client mobili possono scoprire automaticamente le risorse di Lync Server 2013. Quando si supporta l'individuazione automatica, è necessario aggiungere nuovi record DNS (Domain Name System). In questa sezione vengono descritti i record DNS necessari per l'individuazione automatica.

Per supportare l'individuazione automatica, è necessario creare i record DNS seguenti per ogni dominio SIP:

  - Record DNS interno per il supporto degli utenti mobili che si connettono dall'interno della rete dell'organizzazione

  - Record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet

L'URL di individuazione automatica interno non deve essere indirizzabile all'esterno della rete. L'URL di individuazione automatica esterna non deve essere indirizzabile dall'interno della rete. Tuttavia, se non è possibile soddisfare questo requisito per l'URL esterno, il client mobile non dovrebbe essere influenzato dal punto di vista.

I record DNS possono essere record CNAME o A (host).

**Record DNS interni**

È necessario creare uno dei record DNS interni seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di record</th>
<th>Nome host o definizione SRV</th>
<th>Risolve in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;SipDomain&gt;</p></td>
<td><p>Servizi Web interni nome di dominio completo (FQDN) per il pool di Director, se è presente o per il pool Front-end se non si dispone di un amministratore</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscoverinternal. &lt;SipDomain&gt;</p></td>
<td><p>Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si usa un servizio di bilanciamento del carico del pool di Director, se si ha uno o del pool di front-end se non si ha un amministratore</p></td>
</tr>
</tbody>
</table>


**Record DNS esterni**

È necessario creare uno dei record DNS esterni seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di record</th>
<th>Nome host</th>
<th>Risolve in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>FQDN dei servizi Web esterni per il pool di Director, se si ha uno o per il pool di front-end se non si ha un amministratore</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>Lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>Indirizzo IP esterno o pubblico (indirizzo VIP se si usa un bilanciamento del carico) del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls. _tcp. &lt;SipDomain&gt;</p>
<p>Risolve il record host (A o AAAA) per il servizio Access Edge</p></td>
<td><p>Per supportare il servizio di notifica push e il servizio notifica push Apple, è possibile creare un record SRV per ogni dominio SIP che include i client Microsoft Lync mobile.</p>
<div>

> [!IMPORTANT]  
> Questo requisito si applica solo ai client di Microsoft Lync Mobile su dispositivi mobili Apple o Microsoft based. I dispositivi dispositivi e Nokia Symbian non usano la notifica push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, nota anche come individuazione automatica, il traffico passa attraverso il proxy inverso. Il record SRV punta a un record che viene risolto tramite il servizio Access Edge.



</div>

</div>

<span> </span>

</div>

</div>

</div>

