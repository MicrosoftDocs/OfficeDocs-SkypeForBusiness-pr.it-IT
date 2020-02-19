---
title: 'Lync Server 2013: processo di distribuzione per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59b6d6854c628a7f1077c0954d84ea9d82c4f715
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Processo di distribuzione per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

In questa sezione viene descritta la sequenza di passaggi necessari per distribuire la funzionalità di mobilità di Lync Server 2013.

### <a name="mobility-deployment-process"></a>Processo di distribuzione della mobilità

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Autorizzazioni</th>
<th>Documentazione relativa alla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Creare record DNS (Domain Name System)</p></td>
<td><ul>
<li><p>Creare un record CNAME DNS interno o A (host, se IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica interno.</p></li>
<li><p>Creare un record CNAME esterno DNS o A (host, se IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica esterno.</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modificare i certificati</p></td>
<td><p>Aggiungere voci di nomi alternativi soggetto ai certificati seguenti per supportare connessioni sicure per gli utenti mobili:</p>
<ul>
<li><p>Certificato del server Director</p></li>
<li><p>Certificato del pool Front End</p></li>
<li><p>Certificato del proxy inverso</p></li>
</ul></td>
<td><p>Amministratore locale</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare il proxy inverso</p></td>
<td><ul>
<li><p>Assegnare certificati aggiornati con i nomi alternativi soggetto al listener SSL (Secure Sockets Layer).</p></li>
<li><p>Riconfigurare la regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno.</p></li>
<li><p>Assicurarsi che esista una regola di pubblicazione Web per l'URL dei servizi Web Lync Server 2013 esterno nel pool Front end.</p></li>
</ul>
<p>Oppure</p>
<ul>
<li><p>Se si sceglie di utilizzare HTTP per la richiesta di individuazione automatica iniziale e non si aggiornano gli elenchi dei nomi alternativi del soggetto nei certificati, configurare una nuova regola di pubblicazione Web o riconfigurare una regola di pubblicazione esistente per la porta 80 HTTP.</p></li>
</ul></td>
<td><p>Amministratore locale</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testare la distribuzione di dispositivi mobili per Lync 2010 mobile tramite il servizio per dispositivi mobili MCX</p></td>
<td><p>Eseguire <strong>Test-CsMcxP2PIM</strong> per testare l'invio di un messaggio istantaneo da una persona a un'altra.</p>
<p>Per un elenco completo delle opzioni, vedere la documentazione relativa ai cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione di dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testare la distribuzione di dispositivi mobili per i client di Lync 2013 mobile utilizzando i componenti Web di UCWA</p></td>
<td><p>Utilizzare il cmdlet <strong>test-CsUcwaConference</strong> per testare e verificare che gli utenti di test predefiniti o una coppia di utenti effettivi possano utilizzare UCWA per creare e partecipare a una conferenza.</p>
<p>Per un elenco completo delle opzioni, vedere la documentazione relativa ai cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione di dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare il sistema per le notifiche push</p></td>
<td><ul>
<li><p>Per i server perimetrali di Lync Server 2013, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</p></li>
<li><p>Per i server perimetrali di Lync Server 2010, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</p></li>
<li><p>Per i server perimetrali di Office Communications Server 2007 R2, aggiungere un partner federato.</p></li>
<li><p>Se si desidera supportare le notifiche Push tramite una rete Wi-Fi, configurare una regola del firewall in uscita per la porta TCP 5223.</p></li>
<li><p>Utilizzare il cmdlet <strong>Set-CsPushNotificationConfiguration</strong> per abilitare le notifiche push al servizio APNS (Apple Push Notification Service ) e MPNS (Microsoft Push Notification Service). Questa funzionalità è disabilitata per impostazione predefinita.</p></li>
<li><p>Utilizzare il cmdlet <strong>Test-CsFederatedPartner</strong> per testare la configurazione di federazione e il cmdlet <strong>Test-CsMCXPushNotification</strong> per il testing delle notifiche push.</p>
<div>

> [!NOTE]  
> Le notifiche push vengono utilizzate per i client mobili di Lync 2010 nei dispositivi Apple e Windows Phone<BR>La notifica push è obbligatoria per i client di Lync 2013 per dispositivi mobili solo su Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configurazione delle notifiche push in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare i criteri per dispositivi mobili</p></td>
<td><p>Utilizzare il cmdlet <strong>Set-CsMobilityPolicy</strong> per consentire o impedire:</p>
<ul>
<li><p>Chiamata tramite lavoro</p></li>
<li><p>Abilitazione dell'audio IP e del video IP</p></li>
<li><p>Richiedi WiFi per IP audio e/o IP video</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configurazione di criteri per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

