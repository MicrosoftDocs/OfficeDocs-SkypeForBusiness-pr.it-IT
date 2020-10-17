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
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514483"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="21c51-102">Processo di distribuzione per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21c51-102">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21c51-103">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="21c51-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="21c51-104">In questa sezione viene descritta la sequenza di passaggi necessari per distribuire la funzionalità di mobilità di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21c51-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="21c51-105">Processo di distribuzione della mobilità</span><span class="sxs-lookup"><span data-stu-id="21c51-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21c51-106">Fase</span><span class="sxs-lookup"><span data-stu-id="21c51-106">Phase</span></span></th>
<th><span data-ttu-id="21c51-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="21c51-107">Steps</span></span></th>
<th><span data-ttu-id="21c51-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="21c51-108">Permissions</span></span></th>
<th><span data-ttu-id="21c51-109">Documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="21c51-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21c51-110">Creare record DNS (Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="21c51-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="21c51-111">Creare un record CNAME DNS interno o A (host, se IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="21c51-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="21c51-112">Creare un record CNAME esterno DNS o A (host, se IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="21c51-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="21c51-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="21c51-113">Domain Admins</span></span></p>
<p><span data-ttu-id="21c51-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="21c51-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="21c51-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c51-116">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="21c51-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="21c51-117">Aggiungere voci di nomi alternativi soggetto ai certificati seguenti per supportare connessioni sicure per gli utenti mobili:</span><span class="sxs-lookup"><span data-stu-id="21c51-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="21c51-118">Certificato del server Director</span><span class="sxs-lookup"><span data-stu-id="21c51-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="21c51-119">Certificato del pool Front End</span><span class="sxs-lookup"><span data-stu-id="21c51-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="21c51-120">Certificato del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="21c51-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="21c51-121">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="21c51-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="21c51-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c51-123">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="21c51-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="21c51-124">Assegnare certificati aggiornati con i nomi alternativi soggetto al listener SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="21c51-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="21c51-125">Riconfigurare la regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="21c51-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="21c51-126">Assicurarsi che esista una regola di pubblicazione Web per l'URL dei servizi Web Lync Server 2013 esterno nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="21c51-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="21c51-127">Oppure</span><span class="sxs-lookup"><span data-stu-id="21c51-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="21c51-128">Se si sceglie di utilizzare HTTP per la richiesta di individuazione automatica iniziale e non si aggiornano gli elenchi dei nomi alternativi del soggetto nei certificati, configurare una nuova regola di pubblicazione Web o riconfigurare una regola di pubblicazione esistente per la porta 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="21c51-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="21c51-129">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="21c51-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="21c51-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c51-131">Testare la distribuzione di dispositivi mobili per Lync 2010 mobile tramite il servizio per dispositivi mobili MCX</span><span class="sxs-lookup"><span data-stu-id="21c51-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="21c51-132">Eseguire <strong>Test-CsMcxP2PIM</strong> per testare l'invio di un messaggio istantaneo da una persona a un'altra.</span><span class="sxs-lookup"><span data-stu-id="21c51-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="21c51-133">Per un elenco completo delle opzioni, vedere la documentazione relativa ai cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</span><span class="sxs-lookup"><span data-stu-id="21c51-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="21c51-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="21c51-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="21c51-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione di dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c51-136">Testare la distribuzione di dispositivi mobili per i client di Lync 2013 mobile utilizzando i componenti Web di UCWA</span><span class="sxs-lookup"><span data-stu-id="21c51-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="21c51-137">Utilizzare il cmdlet <strong>test-CsUcwaConference</strong> per testare e verificare che gli utenti di test predefiniti o una coppia di utenti effettivi possano utilizzare UCWA per creare e partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="21c51-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="21c51-138">Per un elenco completo delle opzioni, vedere la documentazione relativa ai cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> .</span><span class="sxs-lookup"><span data-stu-id="21c51-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="21c51-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="21c51-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="21c51-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione di dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c51-141">Configurare il sistema per le notifiche push</span><span class="sxs-lookup"><span data-stu-id="21c51-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="21c51-142">Per i server perimetrali di Lync Server 2013, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="21c51-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="21c51-143">Per i server perimetrali di Lync Server 2010, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="21c51-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="21c51-144">Per i server perimetrali di Office Communications Server 2007 R2, aggiungere un partner federato.</span><span class="sxs-lookup"><span data-stu-id="21c51-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="21c51-145">Se si desidera supportare le notifiche Push tramite una rete Wi-Fi, configurare una regola del firewall in uscita per la porta TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="21c51-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="21c51-146">Utilizzare il cmdlet <strong>Set-CsPushNotificationConfiguration</strong> per abilitare le notifiche push al servizio APNS (Apple Push Notification Service ) e MPNS (Microsoft Push Notification Service).</span><span class="sxs-lookup"><span data-stu-id="21c51-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="21c51-147">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="21c51-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="21c51-148">Utilizzare il cmdlet <strong>Test-CsFederatedPartner</strong> per testare la configurazione di federazione e il cmdlet <strong>Test-CsMCXPushNotification</strong> per il testing delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="21c51-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="21c51-149">Le notifiche push vengono utilizzate per i client mobili di Lync 2010 nei dispositivi Apple e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="21c51-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="21c51-150">La notifica push è obbligatoria per i client di Lync 2013 per dispositivi mobili solo su Windows Phone</span><span class="sxs-lookup"><span data-stu-id="21c51-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="21c51-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="21c51-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="21c51-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configurazione delle notifiche push in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c51-153">Configurare i criteri per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="21c51-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="21c51-154">Utilizzare il cmdlet <strong>Set-CsMobilityPolicy</strong> per consentire o impedire:</span><span class="sxs-lookup"><span data-stu-id="21c51-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="21c51-155">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="21c51-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="21c51-156">Abilitazione dell'audio IP e del video IP</span><span class="sxs-lookup"><span data-stu-id="21c51-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="21c51-157">Richiedi WiFi per IP audio e/o IP video</span><span class="sxs-lookup"><span data-stu-id="21c51-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="21c51-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="21c51-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="21c51-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configurazione di criteri per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21c51-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

