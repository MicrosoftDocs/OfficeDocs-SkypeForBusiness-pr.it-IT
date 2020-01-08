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

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="68736-102">Processo di distribuzione per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68736-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68736-103">_**Argomento Ultima modifica:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="68736-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="68736-104">Questa sezione descrive la sequenza di passaggi necessari per distribuire la funzionalità di mobilità di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68736-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="68736-105">Processo di distribuzione della mobilità</span><span class="sxs-lookup"><span data-stu-id="68736-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68736-106">Fase</span><span class="sxs-lookup"><span data-stu-id="68736-106">Phase</span></span></th>
<th><span data-ttu-id="68736-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="68736-107">Steps</span></span></th>
<th><span data-ttu-id="68736-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="68736-108">Permissions</span></span></th>
<th><span data-ttu-id="68736-109">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="68736-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68736-110">Creare record DNS (Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="68736-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="68736-111">Creare un record DNS interno CNAME o a (host, if IPv6, AAAA) per risolvere l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="68736-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="68736-112">Per risolvere l'URL del servizio di individuazione automatica esterna, è necessario creare un record CNAME DNS esterno o (host, se IPv6, AAAA).</span><span class="sxs-lookup"><span data-stu-id="68736-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="68736-113">Amministratori di dominio</span><span class="sxs-lookup"><span data-stu-id="68736-113">Domain Admins</span></span></p>
<p><span data-ttu-id="68736-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="68736-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="68736-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68736-116">Modificare i certificati</span><span class="sxs-lookup"><span data-stu-id="68736-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="68736-117">Aggiungere voci di nome alternative oggetto ai certificati seguenti per supportare connessioni sicure per gli utenti di dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="68736-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="68736-118">Certificato Director</span><span class="sxs-lookup"><span data-stu-id="68736-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="68736-119">Certificato del pool Front-End</span><span class="sxs-lookup"><span data-stu-id="68736-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="68736-120">Certificato di proxy inverso</span><span class="sxs-lookup"><span data-stu-id="68736-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="68736-121">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="68736-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="68736-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68736-123">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="68736-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="68736-124">Assegnare i certificati aggiornati con i nomi alternativi oggetto al listener SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="68736-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="68736-125">Riconfigurare la regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="68736-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="68736-126">Verificare che esista una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="68736-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="68736-127">O</span><span class="sxs-lookup"><span data-stu-id="68736-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="68736-128">Se si sceglie di usare HTTP per la richiesta di individuazione automatica iniziale e non si aggiornano gli elenchi di nomi alternativi soggetti nei certificati, configurare una nuova regola di pubblicazione Web o riconfigurare una regola di pubblicazione esistente per la porta 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="68736-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="68736-129">Amministratore locale</span><span class="sxs-lookup"><span data-stu-id="68736-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="68736-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68736-131">Testare la distribuzione della mobilità per Lync 2010 mobile tramite il servizio di mobilità MCX</span><span class="sxs-lookup"><span data-stu-id="68736-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="68736-132">Eseguire <strong>Test-CsMcxP2PIM</strong> per testare l'invio di un messaggio istantaneo da una persona a un'altra.</span><span class="sxs-lookup"><span data-stu-id="68736-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="68736-133">Vedere la documentazione del cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> per un elenco completo di opzioni.</span><span class="sxs-lookup"><span data-stu-id="68736-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="68736-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="68736-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="68736-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68736-136">Testare la distribuzione della mobilità per i client mobili Lync 2013 usando i componenti Web UCWA</span><span class="sxs-lookup"><span data-stu-id="68736-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="68736-137">Usa il cmdlet <strong>test-CsUcwaConference</strong> per testare e verificare che gli utenti di test predefiniti o una coppia di utenti effettivi possano usare UCWA per creare e partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="68736-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="68736-138">Vedere la documentazione del cmdlet di Lync Server Management Shell per <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> per un elenco completo di opzioni.</span><span class="sxs-lookup"><span data-stu-id="68736-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="68736-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="68736-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="68736-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifica della distribuzione per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68736-141">Configurare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="68736-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="68736-142">Per Lync Server 2013 Edge Server, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="68736-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="68736-143">Per Lync Server 2010 Edge Server, aggiungere un provider di hosting Lync Server online e configurare la Federazione del provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="68736-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="68736-144">Per Office Communications Server 2007 R2 Edge Server, aggiungere un partner federato.</span><span class="sxs-lookup"><span data-stu-id="68736-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="68736-145">Se si vuole supportare le notifiche push tramite una rete Wi-Fi, configurare una regola del firewall in uscita per la porta TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="68736-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="68736-146">Usa il cmdlet <strong>Set-CsPushNotificationConfiguration</strong> per abilitare le notifiche push al servizio notifica push Apple (APN) e al servizio notifica push Microsoft (MPNS).</span><span class="sxs-lookup"><span data-stu-id="68736-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="68736-147">Questa caratteristica è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="68736-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="68736-148">Usa il cmdlet <strong>Test-CsFederatedPartner</strong> per testare la configurazione della Federazione e il cmdlet <strong>Test-CsMcxPushNotification</strong> per testare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="68736-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="68736-149">Le notifiche push vengono usate per i client mobili Lync 2010 su dispositivi Apple e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="68736-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="68736-150">La notifica push è obbligatoria per i client mobili Lync 2013 solo in Windows Phone</span><span class="sxs-lookup"><span data-stu-id="68736-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="68736-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="68736-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="68736-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configurazione delle notifiche push in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68736-153">Configurare i criteri di mobilità</span><span class="sxs-lookup"><span data-stu-id="68736-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="68736-154">Utilizzare il cmdlet <strong>Set-CsMobilityPolicy</strong> per consentire o disabilitare:</span><span class="sxs-lookup"><span data-stu-id="68736-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="68736-155">Chiamata tramite lavoro</span><span class="sxs-lookup"><span data-stu-id="68736-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="68736-156">Abilitare l'audio e il video IP IP</span><span class="sxs-lookup"><span data-stu-id="68736-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="68736-157">Richiedi Wi-Fi per IP audio e/o IP video</span><span class="sxs-lookup"><span data-stu-id="68736-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="68736-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="68736-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="68736-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configurazione dei criteri per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68736-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

