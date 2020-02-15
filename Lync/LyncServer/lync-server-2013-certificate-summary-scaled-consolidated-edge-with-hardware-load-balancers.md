---
title: Riepilogo dei certificati-server perimetrale consolidato in scala con i dispositivi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8efe04d7cb59cc8e8c1d719c9db4ba0e30e75f50
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Riepilogo dei certificati-perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Microsoft Lync Server 2013 utilizza i certificati per l'autenticazione reciproca di altri server e la crittografia dei dati da server a server e server al client. Per i certificati è necessaria la corrispondenza dei nomi dei record DNS (Domain Name System) associati ai server con il nome soggetto (SN) e il nome alternativo del soggetto (SAN) sul certificato. Per un'associazione corretta dei server, dei record DNS e delle voci dei certificati, è necessario scegliere con attenzione i nomi di dominio completi dei server tenendo conto dei record DNS e delle voci SN e SAN registrati sul certificato.

Il certificato assegnato alle interfacce esterne del server perimetrale è richiesto da un'autorità di certificazione (CA) pubblica. Le CA pubbliche che hanno dimostrato successo nella fornitura di certificati ai fini delle comunicazioni unificate sono elencate nell'articolo seguente: [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395). Quando si richiede il certificato, è possibile utilizzare la richiesta di certificato generata dalla distribuzione guidata di Lync Server o creare la richiesta manualmente o tramite un processo fornito dall'autorità di certificazione pubblica. Quando si assegna il certificato, il certificato viene assegnato all'interfaccia del servizio Access Edge, all'interfaccia del servizio Web Conferencing Edge e al servizio di autenticazione audio/video. Il servizio di autenticazione audio/video non deve essere confuso con il servizio A/V Edge, che non utilizza un certificato per crittografare i flussi audio e video. L'interfaccia del server perimetrale interno può utilizzare un certificato da un'autorità di certificazione interna (all'organizzazione) o da un certificato di un'autorità di certificazione pubblica. Il certificato dell'interfaccia interna usa solo il nome soggetto e non richiede né usa voci SAN.

<div>


> [!NOTE]
> Nella tabella seguente viene illustrata una seconda voce SIP (sip.fabrikam.com) nell'elenco dei nomi alternativi soggetto come riferimento. Per ogni dominio SIP presente nell'organizzazione, è necessario che nell'elenco dei nomi alternativi soggetto dei certificati sia aggiunto un FQDN corrispondente.



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>Certificati necessari per Server perimetrale consolidato in scala con bilanciamento del carico hardware


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
<th>Nome soggetto</th>
<th>Ordine/voci nomi alternativi del soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server perimetrale consolidato singolo (perimetro esterno)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Il certificato deve essere rilasciato da una CA pubblica e deve presentare gli EKU server e client se si deve distribuire connettività per messaggistica immediata pubblica con AOL. Inoltre, per i server perimetrali in scala, la chiave privata del certificato deve essere esportabile e il certificato e la chiave privata sono stati copiati in ogni server perimetrale. il certificato viene assegnato alle interfacce perimetrali esterne per:</p>
<ul>
<li><p>Servizio Access Edge</p></li>
<li><p>Servizio Web Conferencing Edge</p></li>
<li><p>Servizio A/V Edge</p></li>
</ul>
<p>Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</p></td>
</tr>
<tr class="even">
<td><p>Server perimetrale consolidato singolo (perimetro interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Nessun SAN richiesto</p></td>
<td><p>Il certificato può essere rilasciato da una CA pubblica o privata e deve contenere l'EKU server. Il certificato viene assegnato all'interfaccia del server perimetrale interno.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Riepilogo dei certificati - Connettività per messaggistica istantanea pubblica


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
<th>Nome soggetto</th>
<th>Ordine/voci nomi alternativi del soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servizio esterno/Access Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Il certificato deve essere rilasciato da una CA pubblica e deve presentare gli EKU server e client se si deve distribuire connettività per messaggistica immediata pubblica con AOL. Il certificato viene assegnato alle interfacce perimetrali esterne per:</p>
<ul>
<li><p>Servizio Access Edge</p></li>
<li><p>Servizio Web Conferencing Edge</p></li>
<li><p>Servizio A/V Edge</p></li>
</ul>
<p>Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo dei certificati per il protocollo XMPP


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
<th>Nome soggetto</th>
<th>Ordine/voci nomi alternativi del soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Assegnare al servizio Access Edge Server perimetrale o pool Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>Le prime tre voci di SAN sono le normali voci di SAN per un server perimetrale completo. La voce contoso.com è necessaria per la federazione con il partner XMPP a livello del dominio radice. Questa voce consentirà l'uso di XMPP per tutti i domini con suffisso *.contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

