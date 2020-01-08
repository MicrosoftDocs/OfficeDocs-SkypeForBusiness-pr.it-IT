---
title: 'Lync Server 2013: Processo di distribuzione per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec6f1e089a9418db3d8ece1f390615226687cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Processo di distribuzione per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

Questa sezione descrive la sequenza di passaggi necessari per distribuire la funzionalità di mobilità di Lync Server 2013.

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Creare record DNS (Domain Name System)</p></td>
<td><ul>
<li><p>Creare un record DNS interno CNAME o a (host, if IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica interno.</p></li>
<li><p>Per risolvere l'URL del servizio di individuazione automatica esterna, è necessario creare un record CNAME DNS esterno o (host, se IPv6, AAAA).</p></li>
</ul></td>
<td><p>Amministratori di dominio</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modificare i certificati</p></td>
<td><p>Aggiungere voci di nome alternative oggetto ai certificati seguenti per supportare connessioni sicure per gli utenti di dispositivi mobili:</p>
<ul>
<li><p>Certificato Director</p></li>
<li><p>Certificato del pool Front-End</p></li>
<li><p>Certificato di proxy inverso</p></li>
</ul></td>
<td><p>Amministratore locale</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare il proxy inverso</p></td>
<td><ul>
<li><p>Assegnare i certificati aggiornati con i nomi alternativi oggetto al listener SSL (Secure Sockets Layer).</p></li>
<li><p>Riconfigurare la regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno.</p></li>
<li><p>Verificare che esista una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno nel pool Front-end.</p></li>
</ul>
<p>O</p>
<ul>
<li><p>Se si sceglie di usare HTTP per la richiesta di individuazione automatica iniziale e non si aggiornano gli elenchi di nomi alternativi soggetti nei certificati, configurare una nuova regola di pubblicazione Web o riconfigurare una regola di pubblicazione esistente per la porta 80 HTTP.</p></li>
</ul></td>
<td><p>Amministratore locale</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testare la distribuzione della mobilità per Lync 2010 mobile tramite il servizio di mobilità MCX</p></td>
<td><p>Eseguire <strong>Test-CsMcxP2PIM</strong> per testare l'invio di un messaggio istantaneo da una persona a un'altra.</p>
<p>Vedere la documentazione del cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> per un elenco completo di opzioni.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testare la distribuzione della mobilità per i client mobili Lync 2013 usando i componenti Web UCWA</p></td>
<td><p>Usa il cmdlet <strong>test-CsUcwaConference</strong> per testare e verificare che gli utenti di test predefiniti o una coppia di utenti effettivi possano usare UCWA per creare e partecipare a una conferenza.</p>
<p>Vedere la documentazione del cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> per un elenco completo di opzioni.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare le notifiche push</p></td>
<td><ul>
<li><p>Per Lync Server 2013 Edge Server, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</p></li>
<li><p>Per Lync Server 2010 Edge Server, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</p></li>
<li><p>Per Office Communications Server 2007 R2 Edge Server, aggiungere un partner federato.</p></li>
<li><p>Se si vuole supportare le notifiche push tramite una rete Wi-Fi, configurare una regola del firewall in uscita per la porta TCP 5223.</p></li>
<li><p>Usa il cmdlet <strong>Set-CsPushNotificationConfiguration</strong> per abilitare le notifiche push al servizio notifica push Apple (APN) e al servizio notifica push Microsoft (MPNS). Questa caratteristica è disabilitata per impostazione predefinita.</p></li>
<li><p>Usa il cmdlet <strong>Test-CsFederatedPartner</strong> per testare la configurazione della Federazione e il cmdlet <strong>Test-CsMcxPushNotification</strong> per testare le notifiche push.</p>
<div>

> [!NOTE]  
> Le notifiche push vengono usate per i client mobili Lync 2010 su dispositivi Apple e Windows Phone<BR>La notifica push è obbligatoria per i client mobili Lync 2013 solo in Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configurazione delle notifiche push in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare i criteri di mobilità</p></td>
<td><p>Utilizzare il cmdlet <strong>Set-CsMobilityPolicy</strong> per consentire o disabilitare:</p>
<ul>
<li><p>Chiamata tramite lavoro</p></li>
<li><p>Abilitare l'audio e il video IP IP</p></li>
<li><p>Richiedi Wi-Fi per IP audio e/o IP video</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configurazione dei criteri per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

