---
title: 'Lync Server 2013: requisiti DNS per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da4910594581f253db155bfceb85c0dcd78f60
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisiti DNS per i dispositivi mobili con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-13_

Quando si distribuisce la funzionalità di mobilità di Lync Server 2013, è possibile utilizzare i nuovi URL disponibili con il servizio di individuazione automatica di Microsoft Lync Server 2013 oppure è possibile utilizzare gli URL dei servizi Web esistenti. Se si utilizzano gli URL esistenti, gli utenti devono immetterli manualmente nelle impostazioni dei loro dispositivi mobili. Questa opzione viene solitamente utilizzata per la risoluzione dei problemi. Quando si utilizzano i nuovi URL, i client mobili possono individuare automaticamente le risorse di Lync Server 2013. Se si supporta l'individuazione automatica, è necessario aggiungere nuovi record DNS (Domain Name System). In questa sezione vengono descritti i record DNS necessari per l'individuazione automatica.

Per supportare l'individuazione automatica, è necessario creare i record DNS seguenti per ogni dominio SIP:

  - Un record DNS interno per supportare gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione

  - Un record esterno, o pubblico, per supportare gli utenti di dispositivi mobili che si connettono da Internet

L'URL interno di individuazione automatica interna non deve essere indirizzabile dall'esterno della rete. L'URL esterno di individuazione automatica non deve essere indirizzabile dall'interno della rete. Se tuttavia non è possibile soddisfare questo requisito per l'URL esterno, la funzionalità dei client mobili non verrà influenzata.

I record DNS possono essere di tipo CNAME o A (host).

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
<th>Viene risolto in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
<td><p>Nome di dominio completo (FQDN) dei servizi Web interni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
<td><p>Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si utilizza un servizio di bilanciamento del carico) del pool di server Director, se si dispone di uno o del pool Front end se non si dispone di un Director</p></td>
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
<th>Viene risolto in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>FQDN dei servizi Web esterni per il pool di server Director, se presente, o per il pool Front end se non si dispone di un Director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscover. &lt;SipDomain&gt;</p></td>
<td><p>Indirizzo IP esterno o pubblico (indirizzo VIP se si utilizza il bilanciamento del carico) del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls. _tcp. &lt;SipDomain&gt;</p>
<p>Consente di risolvere il record host (A o AAAA) per il servizio Access Edge</p></td>
<td><p>Per supportare il servizio di notifica push e il servizio di notifica push di Apple, è necessario creare un record SRV per ogni dominio SIP con client Microsoft Lync mobile.</p>
<div>

> [!IMPORTANT]  
> Questo requisito si applica solo ai client Microsoft Lync Mobile su dispositivi mobili Apple o Microsoft based. I dispositivi Android e Nokia Symbian non utilizzano le notifiche push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, noto anche come individuazione automatica, il traffico passa attraverso il proxy inverso. Il record SRV punta a un record che viene risolto tramite il servizio Access Edge.



</div>

</div>

<span> </span>

</div>

</div>

</div>

