---
title: 'Lync Server 2013: Requisiti dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisiti dei certificati per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-24_

Se si distribuisce la caratteristica mobilità e si supporta l'individuazione automatica per i client mobili, è necessario includere alcune voci alternative per i nomi dei soggetti in certificati per supportare connessioni sicure dai client mobili.

È necessario includere voci di nome alternative per l'individuazione automatica nei certificati seguenti:

  - Pool di Director

  - Pool Front End

  - Proxy inverso

In questa sezione vengono illustrate le voci di nome alternative oggetto necessarie per i certificati per l'individuazione automatica.

<div>


> [!NOTE]  
> La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici usati dal proxy inverso può essere costosa. Se si hanno molti domini SIP, rendendo l'aggiunta di nomi alternativi oggetto molto costosi, è possibile configurare il proxy inverso per l'uso di HTTP per la richiesta di servizio di individuazione automatica iniziale, invece di usare HTTPS (la configurazione predefinita). Per informazioni dettagliate, vedere <A href="lync-server-2013-technical-requirements-for-mobility.md">requisiti tecnici per la mobilità in Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisiti dei certificati del pool di Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica interno</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In alternativa, è possibile usare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisiti del certificato del pool Front-End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica interno</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In alternativa, è possibile usare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisiti dei certificati reverse proxy (public CA)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Questa SAN viene assegnata al certificato assegnato al listener SSL nel proxy inverso.



</div>

<div>


> [!NOTE]  
> Il listener del proxy inverso avrà nomi alternativi soggetti per gli URL dei servizi Web esterni, ad esempio SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com, se è stato distribuito il Director facoltativo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

