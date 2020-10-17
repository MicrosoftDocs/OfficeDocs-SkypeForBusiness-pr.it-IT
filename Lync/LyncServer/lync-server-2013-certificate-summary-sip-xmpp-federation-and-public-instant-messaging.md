---
title: Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517873"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-15_

I certificati necessari per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server vengono in genere soddisfatti dai certificati che vengono configurati, richiesti e assegnati al server perimetrale.

I requisiti dei certificati per l'abilitazione e la creazione di comunicazioni con i partner di protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono l'aggiunta di voci per i domini XMPP. Il record incluso nel certificato come nome alternativo del soggetto (SAN) corrisponderà al dominio che può partecipare alle comunicazioni XMPP. Il dominio può essere a livello della radice (ad esempio, contoso.com) se si desidera abilitare XMPP per l'intero dominio oppure può corrispondere a domini figlio selezionati (ad esempio, corp.contoso.com, finance.contoso.com) se si desidera abilitare XMPP per un sottoinsieme di utenti.

Per configurare i certificati per la connettività per la messaggistica istantanea pubblica, tenere presente che non vi sono elementi diversi da altri tipi di federazione SIP o persino certificati del server perimetrale standard, tranne per il fatto che America Online (AOL) richiede il certificato o i certificati (nel caso di un pool di server perimetrali) per contenere anche l'EKU del client. L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.

Per verificare di aver soddisfatto i requisiti di certificato corretti per la distribuzione del server perimetrale, esaminare gli argomenti elencati nella sezione **vedere anche**.

<div>



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
<th>Nomi alternativi soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetro esterno/Access Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi XMPP di contoso.com


<p>sip.fabrikam.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi SIP di fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi XMPP di fabrikam.com

</td>
<td><p>Il certificato deve provenire da un'autorità di certificazione pubblica e deve disporre del server EKU e del client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL. Il certificato viene assegnato alle interfacce del server perimetrale esterno per:</p>
<ul>
<li><p>Servizio Access Edge</p></li>
<li><p>Servizio Web Conferencing Edge</p></li>
<li><p>Servizio A/V Edge</p></li>
</ul>



> [!NOTE]
> Tecnicamente, un certificato non viene assegnato all'a/V Edge. La comunicazione e l'autenticazione sicure sono gestite tramite il servizio di autenticazione Media Relay (MRAS). MRAS utilizza il certificato assegnato all'interfaccia interna del server perimetrale.


<p>Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Riepilogo dei certificati-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Riepilogo dei certificati-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Riepilogo dei certificati-perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

