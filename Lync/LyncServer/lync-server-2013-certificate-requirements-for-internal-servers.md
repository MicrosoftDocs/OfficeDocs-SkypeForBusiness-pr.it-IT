---
title: 'Lync Server 2013: requisiti dei certificati per i server interni'
description: 'Lync Server 2013: requisiti dei certificati per i server interni.'
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
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575212"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisiti dei certificati per i server interni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-02-17_

I server interni che eseguono Lync Server e che richiedono i certificati includono il server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director. Nella tabella seguente sono riportati i requisiti dei certificati per tali server. È possibile utilizzare la configurazione guidata certificati di Lync Server per richiedere questi certificati.

<div>


> [!TIP]  
> I certificati con caratteri jolly sono supportati per i nomi alternativi del soggetto associati agli URL semplici del pool Front End, Front End Server o Director. Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto per i certificati con caratteri jolly in Lync Server 2013</A>.



</div>

Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica. Per un elenco delle CA pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati per comunicazioni unificate e che hanno collaborato con Microsoft per assicurarsi che funzionino con la configurazione guidata certificati di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificato per le comunicazioni unificate per Exchange Server e per Communications Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .

La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato da altre applicazioni e prodotti. Per la versione 2013, Lync Server 2013 e altri prodotti server Microsoft, tra cui Exchange 2013 e SharePoint Server, supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server. Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

Per le connessioni dai client che eseguono il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) certificati firmati utilizzando la funzione hash di crittografia SHA-256. Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.

Nelle tabelle seguenti sono indicati i requisiti dei certificati in base al ruolo del server per i pool Front End e i server Standard Edition. Sono tutti certificati del server Web standard con chiave privata non esportabili.

Si noti che l'utilizzo chiavi avanzato nel server viene configurato automaticamente quando si utilizza la Configurazione guidata certificati per richiedere certificati.

<div>


> [!NOTE]  
> Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.



</div>

<div>


> [!NOTE]  
> Se nel DNS sono stati configurati sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo del soggetto del certificato.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificati per il server Standard Edition

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
<th>Nome alternativo del soggetto</th>
<th>Esempio</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefiniti</p></td>
<td><p>Nome di dominio completo (FQDN) del pool</p></td>
<td><p>FQDN del pool e del nome di dominio completo del server</p>
<p>Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</p>
<p>Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</p></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com</p>
<p>Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.</p>
<p>La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</p>
<p>È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>FQDN del server</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web interno, che corrisponde all'FQDN del server</p></li>
<li><p>URL semplici per le riunioni (meet)</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>URL semplice per l'accesso amministrativo (admin)</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>Nel caso di un certificato con caratteri jolly:</p>
<p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.</p>
<p>Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci di URL semplici.</p></td>
</tr>
<tr class="odd">
<td><p>Esterno Web</p></td>
<td><p>FQDN del server</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>Rispettare gli URL semplici per dominio SIP</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>Nel caso di un certificato con caratteri jolly:</p>
<p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci di URL semplici.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificati per il Front End Server in un pool Front End

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
<th>Nome alternativo del soggetto</th>
<th>Esempio</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefiniti</p></td>
<td><p>FQDN del pool</p></td>
<td><p>FQDN del pool e FQDN del server</p>
<p>Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</p>
<p>Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</p></td>
<td><p>SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</p>
<p>Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</p>
<p>È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>FQDN del pool</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web interno (che non corrisponde al nome di dominio completo del server)</p></li>
<li><p>FQDN del server</p></li>
<li><p>FQDN del pool Lync</p></li>
<li><p>URL semplici per le riunioni (meet)</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>URL semplice per l'accesso amministrativo (admin)</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>Nel caso di un certificato con caratteri jolly:</p>
<p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci di URL semplici.</p></td>
</tr>
<tr class="odd">
<td><p>Esterno Web</p></td>
<td><p>FQDN del pool</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>URL semplice per l'accesso amministrativo (admin)</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>Nel caso di un certificato con caratteri jolly:</p>
<p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</p>
<p>Le voci con caratteri jolly sono supportate per le voci di URL semplici.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificati per il Director

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
<th>Nome alternativo del soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefiniti</p></td>
<td><p>FQDN del pool di server Director</p></td>
<td><p>FQDN del Director, FQDN del pool di server Director</p>
<p>Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
<tr class="even">
<td><p>Interno Web</p></td>
<td><p>FQDN del server</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web interno, che corrisponde all'FQDN del server</p></li>
<li><p>FQDN del server</p></li>
<li><p>FQDN del pool Lync</p></li>
<li><p>URL semplici per le riunioni (meet)</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>URL semplice per l'accesso amministrativo (admin)</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = *. contoso. com</p></td>
</tr>
<tr class="odd">
<td><p>Esterno Web</p></td>
<td><p>FQDN del server</p></td>
<td><p>Ognuno dei seguenti:</p>
<ul>
<li><p>FQDN Web esterno</p></li>
<li><p>URL semplice per l'accesso esterno (dialin)</p></li>
<li><p>URL semplice per l'accesso amministrativo (admin)</p></li>
<li><p>In alternativa, una voce con caratteri jolly per gli URL semplici</p></li>
</ul></td>
<td><p>Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Se è presente un pool Mediation Server autonomo, ognuno dei Mediation Server in esso contenuti richiederà i certificati riportati nella tabella seguente. Se si colloca un Mediation Server nei Front End Server, saranno sufficienti i certificati riportati nella tabella "Certificati per il Front End Server in un pool Front End" più indietro in questo argomento.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificati per il Mediation Server autonomo

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
<th>Nome alternativo del soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefiniti</p></td>
<td><p>FQDN del pool</p></td>
<td><p>FQDN del pool</p>
<p>FQDN del server membro del pool</p></td>
<td><p>SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificati per il Survivable Branch Appliance

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
<th>Nome alternativo del soggetto</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predefiniti</p></td>
<td><p>FQDN del dispositivo</p></td>
<td><p>SIP. &lt; SipDomain &gt; (è necessaria una voce per ogni dominio SIP)</p></td>
<td><p>SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vedere anche


[Supporto per i certificati con caratteri jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

