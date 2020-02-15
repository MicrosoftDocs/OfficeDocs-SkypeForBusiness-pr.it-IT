---
title: 'Lync Server 2013: requisiti dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisiti dei certificati per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-24_

Se si distribuisce la funzionalità di mobilità e si supporta l'individuazione automatica per i client mobili, è necessario includere determinate voci di nomi alternativi soggetto nei certificati per supportare le connessioni sicure dai client mobili.

È necessario includere voci di nomi alternativi soggetto per l'individuazione automatica nei certificati seguenti:

  - Pool Director

  - Pool Front End

  - Proxy inverso

In questa sezione vengono descritte le voci di nomi alternativi soggetto richieste nei certificati per l'individuazione automatica.

<div>


> [!NOTE]  
> La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici utilizzati dal proxy inverso può essere un compito oneroso. Se esistono molti domini SIP, nel qual caso l'aggiunta di nomi alternativi soggetto è particolarmente onerosa, è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, anziché HTTPS come da configurazione predefinita. Per informazioni dettagliate, vedere <A href="lync-server-2013-technical-requirements-for-mobility.md">requisiti tecnici per i dispositivi mobili in Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisiti relativi ai certificati per il pool di server Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interno del servizio di individuazione automatica</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In alternativa, è possibile utilizzare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisiti relativi ai certificati per il pool Front End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interno del servizio di individuazione automatica</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In alternativa, è possibile utilizzare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisiti relativi ai certificati del proxy inverso (CA pubblica)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Questo nome alternativo del soggetto viene assegnato al certificato assegnato al listener SSL nel proxy inverso.



</div>

<div>


> [!NOTE]  
> Il listener del proxy inverso avrà nomi alternativi del soggetto per gli URL dei servizi Web esterni (ad esempio, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se è stato distribuito il server Director facoltativo).



</div>

</div>

<span> </span>

</div>

</div>

</div>

