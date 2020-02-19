---
title: 'Lync Server 2013: checklist di distribuzione per il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22eb8185c88340269856b2244c130a05d1fd0325
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Checklist di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-08_

Per una pianificazione efficace del servizio Controllo di ammissione di chiamata è necessario prendere in considerazione quanto segue:

  - Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata

  - Informazioni necessarie per il servizio Controllo di ammissione di chiamata e decisioni che devono essere prese prima di iniziare la distribuzione

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata

Prima di distribuire il controllo di ammissione di chiamata, è necessario che siano già stati distribuiti i server interni di Lync Server 2013, tra cui un pool Front end o un server Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Informazioni necessarie per il servizio Controllo di ammissione di chiamata

Nella tabella seguente sono riepilogate le informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informazioni</th>
<th>Riepilogo delle informazioni necessarie</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Funzionalità di Lync Server necessarie per l'organizzazione</p></td>
<td><ul>
<li><p>Funzionalità da supportare nell'organizzazione</p></li>
<li><p>Funzionalità da abilitare per i singoli utenti</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologie e componenti da distribuire</p></td>
<td><ul>
<li><p>I componenti correlati a CAC vengono installati automaticamente come parte di Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisiti di sistema</p></td>
<td><ul>
<li><p>Requisiti hardware</p></li>
<li><p>Requisiti software</p></li>
<li><p>Requisiti di collocazione</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Requisiti dell'infrastruttura</p></td>
<td><ul>
<li><p>Per il Controllo di ammissione di chiamata non esistono requisiti dell'infrastruttura specifici</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisiti dell'infrastruttura per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisiti dell'interfaccia di rete</p></td>
<td><ul>
<li><p>Informazioni sull'interfaccia interna ed esterna</p></li>
<li><p>Informazioni sul routing (incluse le informazioni sul Blog di <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>NextHop nel canale di risposta dei clienti del team di Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Strategia di distribuzione</p></td>
<td><ul>
<li><p>Sequenza di distribuzione</p></li>
<li><p>Gruppo di lavoro o dominio</p></li>
<li><p>Sicurezza</p></li>
<li><p>Monitoraggio e controllo</p></li>
<li><p>Considerazioni sull'hardware</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Processo di distribuzione</p></td>
<td><ul>
<li><p>Prerequisiti</p></li>
<li><p>Informazioni necessarie</p></li>
<li><p>Processo e procedure</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Configurare il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

