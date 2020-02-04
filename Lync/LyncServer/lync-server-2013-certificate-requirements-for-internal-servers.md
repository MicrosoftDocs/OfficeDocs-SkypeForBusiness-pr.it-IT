---
title: 'Lync Server 2013: Requisiti dei certificati per i server interni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisiti dei certificati per i server interni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-02-17_

I server interni che esegue Lync Server e che richiedono certificati includono server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director. La tabella seguente mostra i requisiti dei certificati per questi server. È possibile usare la configurazione guidata certificati di Lync Server per richiedere questi certificati.

<div>


> [!TIP]  
> I certificati con caratteri jolly sono supportati per i nomi alternativi dell'oggetto associati agli URL semplici nel pool Front-End, nel server front fine o nel Director. Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto di certificati jolly in Lync Server 2013</A>.



</div>

Anche se è consigliata un'autorità di certificazione (CA) interna per i server interni, è anche possibile usare una CA pubblica. Per un elenco delle autorità di certificazione pubbliche che includono certificati che soddisfano requisiti specifici per i certificati di Unified Communications (UC) e che hanno collaborato con Microsoft per verificare che funzionino con la procedura guidata certificato di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificati per le comunicazioni unificate [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)per Exchange Server e per Communications Server".

La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato dalle altre applicazioni e prodotti. Per la versione di 2013, Lync Server 2013 e altri prodotti di Microsoft Server, inclusi Exchange 2013 e SharePoint Server, supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione operativa.

Per le connessioni da client che utilizzano il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non Richiedi) certificati firmati con la funzione hash crittografico SHA-256. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.

Le tabelle seguenti mostrano i requisiti dei certificati per il ruolo del server per i pool Front end e i server Standard Edition. Tutti questi sono certificati server Web standard, chiave privata, non esportabile.

Tieni presente che l'utilizzo della chiave avanzata del server viene configurato automaticamente quando usi la procedura guidata certificati per richiedere certificati.

<div>


> [!NOTE]  
> Ogni nome descrittivo del certificato deve essere univoco nell'archivio di computer.



</div>

<div>


> [!NOTE]  
> Se nel DNS è stato configurato sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo soggetto del certificato.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificati per server Standard Edition

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificato</th>
<th>Nome soggetto/nome comune</th>
<th>Nome alternativo soggetto</th>
<th>Esempio</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>Nome di dominio completo (FQDN) del pool</p></td>
<td><p>FQDN del pool e il nome di dominio completo del server</p>
<p>Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</p>
<p>Se questo pool è il server di accesso automatico per i client e la corrispondenza Strict Domain Name System (DNS) è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</p></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com</p>
<p>Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
<td><p>Nel server Standard Edition il nome di dominio completo del server è uguale al nome di dominio completo del pool.</p>
<p>La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</p>
<p>Puoi anche usare questo certificato per l'autenticazione da server a server.</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>Nome di dominio completo del server</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web interno (che corrisponde al nome di dominio completo del server)</p></li>
<li><p>Soddisfare URL semplici</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>URL semplice amministratore</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>Uso di un certificato con caratteri jolly:</p>
<p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Non è possibile eseguire l'override del FQDN Web interno in Generatore di topologie.</p>
<p>Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci URL semplici.</p></td>
</tr>
<tr class="odd">
<td><p>Web esterno</p></td>
<td><p>Nome di dominio completo del server</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>Soddisfare URL semplici per ogni dominio SIP</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>Uso di un certificato con caratteri jolly:</p>
<p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci URL semplici.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificati per il server front-end in un pool Front-End

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificato</th>
<th>Nome soggetto/nome comune</th>
<th>Nome alternativo soggetto</th>
<th>Esempio</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>Nome di dominio completo del pool</p></td>
<td><p>FQDN del pool e del nome di dominio completo del server.</p>
<p>Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</p>
<p>Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</p></td>
<td><p>SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</p>
<p>Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
<td><p>La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</p>
<p>Puoi anche usare questo certificato per l'autenticazione da server a server.</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>Nome di dominio completo del pool</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web interno (che non corrisponde al nome di dominio completo del server)</p></li>
<li><p>Nome di dominio completo del server</p></li>
<li><p>FQDN del pool di Lync</p></li>
<li><p>Soddisfare URL semplici</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>URL semplice amministratore</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>Uso di un certificato con caratteri jolly:</p>
<p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci URL semplici.</p></td>
</tr>
<tr class="odd">
<td><p>Web esterno</p></td>
<td><p>Nome di dominio completo del pool</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>URL semplice amministratore</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>Uso di un certificato con caratteri jolly:</p>
<p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci URL semplici.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificati per Director

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificato</th>
<th>Nome soggetto/nome comune</th>
<th>Nome alternativo soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>Nome di dominio completo del pool di Director</p></td>
<td><p>Nome di dominio completo del Director, FQDN del pool di Director</p>
<p>Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Se questo pool di Director è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>Nome di dominio completo del server</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web interno (che corrisponde al nome di dominio completo del server)</p></li>
<li><p>Nome di dominio completo del server</p></li>
<li><p>FQDN del pool di Lync</p></li>
<li><p>Soddisfare URL semplici</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>URL semplice amministratore</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = *. contoso. com</p></td>
</tr>
<tr class="odd">
<td><p>Web esterno</p></td>
<td><p>Nome di dominio completo del server</p></td>
<td><p>Ognuna delle opzioni seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice con accesso esterno</p></li>
<li><p>URL semplice amministratore</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>Il nome FQDN Web esterno del Director deve essere diverso dal pool Front-end o dal server front-end.</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Se si dispone di un pool di Mediation Server autonomo, i server di mediazione in ognuno di essi richiedono i certificati elencati nella tabella seguente. Se si colloca Mediation Server con i server front-end, i certificati elencati nella tabella "certificati per il server front-end in pool Front-End" in questo argomento sono sufficienti.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificati per Mediation Server autonomo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificato</th>
<th>Nome soggetto/nome comune</th>
<th>Nome alternativo soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>Nome di dominio completo del pool</p></td>
<td><p>Nome di dominio completo del pool</p>
<p>FQDN del server dei membri del pool</p></td>
<td><p>SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificati per Survivable Branch Appliance

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificato</th>
<th>Nome soggetto/nome comune</th>
<th>Nome alternativo soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefinita</p></td>
<td><p>Nome di dominio completo dell'accessorio</p></td>
<td><p>SIP. &lt;SipDomain&gt; (serve una voce per ogni dominio SIP)</p></td>
<td><p>SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vedere anche


[Supporto dei certificati con caratteri jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

