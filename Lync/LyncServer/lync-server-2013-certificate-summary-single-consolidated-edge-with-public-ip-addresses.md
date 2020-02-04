---
title: Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1880856214632357a1a4190a22cd56b29dee020a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Microsoft Lync Server 2013 USA i certificati per l'autenticazione reciproca di altri server e per la crittografia dei dati da server a server e server al client. I certificati richiedono la corrispondenza di nomi dei record DNS (Domain Name System) associati ai server e il nome dell'oggetto (SN) e il nome alternativo Subject (SAN) nel certificato. Per eseguire correttamente il mapping di server, record DNS e voci di certificato, è necessario pianificare attentamente i nomi di dominio completi del server previsto come registrati in DNS e le voci SN e SAN nel certificato.

Il certificato assegnato alle interfacce esterne del server perimetrale è richiesto da un'autorità di certificazione pubblica (CA). Le CA pubbliche che hanno dimostrato successo nella fornitura di certificati ai fini delle comunicazioni unificate sono elencate nell'articolo seguente: [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) quando si richiede il certificato, è possibile usare la richiesta di certificato generata dalla distribuzione guidata di Lync Server o creare la richiesta manualmente o tramite un processo fornito dalla CA pubblica. Quando si assegna il certificato, il certificato viene assegnato all'interfaccia del servizio di Access Edge, all'interfaccia del servizio Web Conferencing Edge e al servizio di autenticazione audio/video. Il servizio di autenticazione audio/video non deve essere confuso con il servizio A/V Edge che non usa un certificato per crittografare i flussi audio e video. L'interfaccia interna del server perimetrale può usare un certificato da una CA interna (all'organizzazione) o da un certificato di una CA pubblica. Il certificato di interfaccia interno USA solo SN e non ha bisogno o usa le voci SAN.

<div>


> [!NOTE]
> La tabella seguente mostra una seconda voce SIP (sip.fabrikam.com) nell'elenco nome alternativo oggetto per riferimento. Per ogni dominio SIP nell'organizzazione, è necessario aggiungere un nome di dominio completo corrispondente elencato nell'elenco dei nomi alternativi del soggetto del certificato.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Certificati necessari per un singolo bordo consolidato con indirizzi IP pubblici


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome soggetto (SN)</th>
<th>Nomi alternativi oggetto (SAN)/Order</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Singolo bordo consolidato (bordo esterno)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Il certificato deve essere proveniente da una CA pubblica e deve avere il server EKU e il client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL. Il certificato viene assegnato alle interfacce Edge esterne per:</p>
<ul>
<li><p>Access Edge</p></li>
<li><p>Conferencing Edge</p></li>
<li><p>A/V Edge</p></li>
</ul>
<p>Tieni presente che i SANs vengono aggiunti automaticamente al certificato in base alle tue definizioni in Generatore di topologie. Si aggiungono le voci SAN in base alle esigenze per altri domini SIP e altre voci che è necessario supportare. Il nome del soggetto viene replicato nella SAN e deve essere presente per il corretto funzionamento.</p></td>
</tr>
<tr class="even">
<td><p>Singolo bordo consolidato (bordo interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Nessun SAN richiesto</p></td>
<td><p>Il certificato può essere emesso da una CA pubblica o privata e deve contenere il server EKU. Il certificato viene assegnato all'interfaccia bordo interno.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Riepilogo del certificato-connettività di messaggistica istantanea pubblica


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome oggetto</th>
<th>Nomi alternativi oggetto (SAN)/Order</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Esterno/bordo di accesso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Il certificato deve essere proveniente da una CA pubblica e deve avere il server EKU e il client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL. Il certificato viene assegnato alle interfacce Edge esterne per:</p>
<ul>
<li><p>Access Edge</p></li>
<li><p>Conferencing Edge</p></li>
<li><p>A/V Edge</p></li>
</ul>
<p>Tieni presente che i SANs vengono aggiunti automaticamente al certificato in base alle tue definizioni in Generatore di topologie. Si aggiungono le voci SAN in base alle esigenze per altri domini SIP e altre voci che è necessario supportare. Il nome del soggetto viene replicato nella SAN e deve essere presente per il corretto funzionamento.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo del certificato per il protocollo di messaggistica e presenza estensibile


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome oggetto</th>
<th>Nomi alternativi oggetto (SAN)/Order</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Assegna a servizio Edge di Access di Edge Server o pool di Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>Le prime tre voci SAN sono le normali voci di SAN per un server perimetrale completo. Contoso.com è la voce necessaria per la Federazione con il partner XMPP a livello di dominio radice. Questa voce consentirà XMPP per tutti i domini con il suffisso *. contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

