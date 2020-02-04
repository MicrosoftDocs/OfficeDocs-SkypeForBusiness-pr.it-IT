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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-15_

I certificati necessari per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server verranno in genere soddisfatti dai certificati configurati, richiesti e assegnati al server perimetrale.

I requisiti di certificato per l'abilitazione e la creazione di comunicazioni con i partner del protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono l'aggiunta di voci per i domini XMPP. Il record incluso nel certificato come nome alternativo soggetto (SAN) sarà il dominio che può partecipare alle comunicazioni XMPP. Il dominio può essere il dominio a livello di radice (ad esempio contoso.com) se si vuole abilitare XMPP per l'intero dominio oppure i domini figlio selezionati, ad esempio corp.contoso.com, finance.contoso.com, se si Abilita XMPP per un sottoinsieme di utenti.

Per configurare i certificati per la connettività pubblica per la messaggistica istantanea, tenere presente che non sono presenti elementi diversi da altri tipi federativi SIP o da certificati standard del server Edge, ad eccezione del fatto che America Online (AOL) richiede un certificato o i certificati (in il caso di un pool di bordi) per contenere anche l'EKU client. L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.

Per verificare di avere soddisfatto i requisiti di certificato corretti per la distribuzione di Edge Server, esaminare gli argomenti elencati nella sezione **vedere anche**.

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
<th>Nome oggetto</th>
<th>Nomi alternativi oggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Esterno/bordo di accesso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi XMPP contoso.com


<p>sip.fabrikam.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Per supportare lo spazio dei nomi XMPP fabrikam.com

</td>
<td><p>Il certificato deve provenire da una CA pubblica e deve avere il server EKU e il client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL. Il certificato viene assegnato alle interfacce di Edge Server esterne per:</p>
<ul>
<li><p>Access Edge Services</p></li>
<li><p>Web Conferencing Edge service</p></li>
<li><p>A/V Edge service</p></li>
</ul>



> [!NOTE]
> Tecnicamente, un certificato non viene assegnato al bordo A/V. La sicurezza delle comunicazioni e dell'autenticazione è gestita tramite il servizio di autenticazione di MRA (Media Relay Authentication Service). MRA usa il certificato assegnato all'interfaccia interna del server perimetrale.


<p>Tieni presente che i SANs vengono aggiunti automaticamente al certificato in base alle tue definizioni in Generatore di topologie. Si aggiungono le voci SAN in base alle esigenze per altri domini SIP e altre voci che è necessario supportare. Il nome del soggetto viene replicato nella SAN e deve essere presente per il corretto funzionamento.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

