---
title: 'Lync Server 2013: crittografia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Crittografia per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-09-14_

Microsoft Lync Server 2013 usa TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da un server all'altro richiede MTLS, indipendentemente dal fatto che il traffico sia confinato alla rete interna o attraversi il perimetro della rete interna. TLS è facoltativo ma è fortemente consigliato tra Mediation Server e media gateway. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Di conseguenza, il gateway deve essere configurato con un certificato di una CA considerata attendibile dal server Mediation.

<div>


> [!NOTE]  
> Un Advisory sulla sicurezza per SSL 3,0 è stato pubblicato in 2014. La disabilitazione di SSL 3,0 in Lync Server 2013 è un'opzione supportata. Per ulteriori informazioni sull'advisory sulla sicurezza, vedere <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Per assicurarsi che venga usato il protocollo crittografico più forte, Lync Server 2013 offrirà ai client protocolli di crittografia TLS con l'ordine seguente: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS è un aspetto critico di Lync Server 2013 e quindi è necessario per mantenere un ambiente supportato.</td>
</tr>
</tbody>
</table>


</div>

I requisiti per il traffico da client a client variano a seconda che il traffico attraversi il firewall aziendale interno. Il traffico strettamente interno può usare TLS, in questo caso il messaggio istantaneo è crittografato o TCP, in questo caso non lo è.

La tabella seguente riepiloga i requisiti di protocollo per ogni tipo di traffico.

### <a name="traffic-protection"></a>Protezione del traffico

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipologia di traffico</th>
<th>Protetto da</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Da server a server</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Da client a server</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Messaggistica istantanea e presenza</p></td>
<td><p>TLS (se configurato per TLS)</p></td>
</tr>
<tr class="even">
<td><p>Audio e video e condivisione desktop di file multimediali</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Condivisione desktop (segnalazione)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Conferenza Web</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Download contenuto della riunione, download rubrica, espansione gruppo di distribuzione</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Crittografia file multimediali

Il traffico di file multimediali viene crittografato tramite Secure RTP (SRTP), un profilo di Real-Time Transport Protocol (RTP) che offre riservatezza, autenticazione e protezione dagli attacchi di riproduzione al traffico RTP. Inoltre, i file multimediali che scorrono in entrambe le direzioni tra il Mediation Server e il suo hop successivo interno sono crittografati anche tramite SRTP. Il flusso multimediale in entrambe le direzioni tra il Mediation Server e un gateway multimediale non viene crittografato per impostazione predefinita. Il Mediation Server può supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e lo spazio di archiviazione di un certificato.

<div>


> [!NOTE]  
> Audio/video (A/V) è supportato con la nuova versione di Windows Live Messenger. Se stai implementando una Federazione A/V con Windows Live Messenger, devi anche modificare il livello di crittografia del server Lync. Per impostazione predefinita, il livello di crittografia è obbligatorio. È necessario modificare questa impostazione in supportato tramite Lync Server Management Shell. Per altre informazioni, vedere <A href="lync-server-2013-deploying-external-user-access.md">distribuzione dell'accesso degli utenti esterni in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Il traffico multimediale audio e video non viene crittografato tra i client Microsoft Lync 2013 e Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 e Microsoft Exchange Server 2013 funzionano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'uso degli algoritmi FIPS 140-2 per la crittografia di sistema. Per implementare il supporto FIPS, è necessario configurare ogni server in cui è in esecuzione Lync Server 2013 per supportarlo. Per informazioni dettagliate sull'uso degli algoritmi conformi allo standard FIPS e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge base sugli effetti dell'abilitazione della "crittografia del sistema: usare gli algoritmi conformi agli standard FIPS per la crittografia, l'hashing e la firma" in Windows XP e [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows at. Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere Exchange 2010 SP1 e supporto degli algoritmi conformi a [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)FIPS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

