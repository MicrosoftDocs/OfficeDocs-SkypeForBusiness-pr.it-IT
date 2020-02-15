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
ms.openlocfilehash: 5cc25c66ce807e796cf7e510d89a5a623f98eb49
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Crittografia per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-09-14_

Microsoft Lync Server 2013 utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da server a server richiede MTLS, indipendentemente dal fatto che il traffico venga confinato alla rete interna o attraversi il perimetro della rete interna. TLS è facoltativo ma è fortemente consigliato tra il Mediation Server e il gateway multimediale. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Pertanto, il gateway deve essere configurato con un certificato proveniente da un'autorità di certificazione considerata attendibile dal Mediation Server.

<div>


> [!NOTE]  
> Una consulenza sulla sicurezza relativa a SSL 3,0 è stata pubblicata nel 2014. La disattivazione di SSL 3,0 in Lync Server 2013 è un'opzione supportata. Per ulteriori informazioni sull'advisory sulla sicurezza, vedere <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.



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
<td>Per garantire che venga utilizzato il protocollo crittografico più efficace, Lync Server 2013 offrirà i protocolli di crittografia TLS nell'ordine seguente ai client: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS è un aspetto critico di Lync Server 2013 e pertanto è necessario per mantenere un ambiente supportato.</td>
</tr>
</tbody>
</table>


</div>

I requisiti per il traffico client-client variano a seconda che tale traffico attraversi o meno il firewall aziendale interno. Nel traffico esclusivamente interno è possibile utilizzare TLS, nel qual caso i messaggi istantanei vengono crittografati, oppure TCP, nel qual caso i messaggi non vengono crittografati.

Nella tabella seguente vengono riepilogati i requisiti relativi ai protocolli per ogni tipo di traffico.

### <a name="traffic-protection"></a>Protezione del traffico

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di traffico</th>
<th>Protetto da</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Da server a server</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Client-to-server</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Messaggistica istantanea e informazioni sulla presenza</p></td>
<td><p>TLS (se configurato per TLS)</p></td>
</tr>
<tr class="even">
<td><p>Audio e video e condivisione desktop di elementi multimediali</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Condivisione desktop (segnalazione)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Download del contenuto delle riunioni, download della Rubrica, espansione dei gruppi di distribuzione</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Crittografia multimediale

Il traffico multimediale viene crittografato tramite SRTP (Secure RTP), un profilo del protocollo RTP (Real-Time Transport Protocol) che garantisce riservatezza, autenticazione e protezione da attacchi di tipo replay per il traffico RTP. Anche il contenuto multimediale trasferito in entrambe le direzioni tra il Mediation Server e l'hop successivo interno viene crittografato tramite il protocollo SRTP. Il flusso multimediale in entrambe le direzioni tra il Mediation Server e un gateway multimediale non è crittografato per impostazione predefinita. Il Mediation Server è in grado di supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e l'archiviazione di un certificato.

<div>


> [!NOTE]  
> Audio/video (A/V) è supportato con la nuova versione di Windows Live Messenger. Se si implementa la federazione A/V con Windows Live Messenger, è inoltre necessario modificare il livello di crittografia di Lync Server. Per impostazione predefinita, il livello di crittografia è Required. È necessario modificare questa impostazione in modo che sia supportata mediante Lync Server Management Shell. Per ulteriori informazioni, vedere <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Il traffico multimediale audio e video non è crittografato tra i client Microsoft Lync 2013 e Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 e Microsoft Exchange Server 2013 operano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'utilizzo degli algoritmi FIPS 140-2 per la crittografia del sistema. Per implementare il supporto FIPS, è necessario configurare ogni server su cui è in esecuzione Lync Server 2013 per supportarlo. Per informazioni dettagliate sull'utilizzo di algoritmi FIPS conformi e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge base gli effetti dell'abilitazione dell'impostazione di sicurezza "crittografia del sistema: utilizzare gli algoritmi FIPS conformi per la crittografia, l'hashing e la firma" in Windows XP e nelle [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)versioni successive di Windows all'indirizzo. Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere Exchange 2010 SP1 and Support for FIPS compliant algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).

</div>

</div>

<span> </span>

</div>

</div>

</div>

