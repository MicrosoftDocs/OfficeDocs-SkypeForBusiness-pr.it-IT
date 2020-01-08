---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-08_

Per pianificare efficacemente il controllo di ammissione alle chiamate (CAC), è necessario tenere presente quanto segue:

  - Prerequisiti per la distribuzione di CAC.

  - Informazioni necessarie per le decisioni di configurazione e CAC che è necessario apportare prima della distribuzione.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Prerequisiti di distribuzione per il controllo di ammissione di chiamata

Prima di distribuire il controllo di ammissione di chiamata, è necessario che siano già stati distribuiti i server interni di Lync Server 2013, incluso un pool Front-end o un server Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Requisiti di informazioni per il controllo dell'ammissione alle chiamate

Nella tabella seguente vengono riepilogate le informazioni necessarie per la distribuzione del controllo di ammissione alle chiamate.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Requisiti di informazioni per la distribuzione del controllo di ammissione alle chiamate

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
<td><p>Funzionalità di Lync Server richieste dall'organizzazione</p></td>
<td><ul>
<li><p>Funzionalità supportate dall'organizzazione</p></li>
<li><p>Funzionalità da abilitare per singoli utenti</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologie e componenti da distribuire</p></td>
<td><ul>
<li><p>I componenti correlati a CAC vengono automaticamente installati come parte di Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
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
<td><p>Requisiti per l'infrastruttura</p></td>
<td><ul>
<li><p>Non sono necessari requisiti specifici per l'infrastruttura per CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisiti dell'infrastruttura per il controllo di ammissione di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisiti di interfaccia di rete</p></td>
<td><ul>
<li><p>Informazioni sulle interfacce interne ed esterne</p></li>
<li><p>Informazioni di routing (incluse le informazioni sul Blog di <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>NextHop at, canale di risposta del cliente del team di Microsoft Lync Server)</p></li>
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
<li><p>Requisiti per le informazioni</p></li>
<li><p>Processi e procedure</p></li>
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

