---
title: 'Lync Server 2013: requisiti dei certificati per i server interni'
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
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="a254a-102">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a254a-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a254a-103">_**Ultimo argomento modificato:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="a254a-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="a254a-104">I server interni che eseguono Lync Server e che richiedono i certificati includono il server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="a254a-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="a254a-105">Nella tabella seguente sono riportati i requisiti dei certificati per tali server.</span><span class="sxs-lookup"><span data-stu-id="a254a-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="a254a-106">È possibile utilizzare la configurazione guidata certificati di Lync Server per richiedere questi certificati.</span><span class="sxs-lookup"><span data-stu-id="a254a-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a254a-107">I certificati con caratteri jolly sono supportati per i nomi alternativi del soggetto associati agli URL semplici del pool Front End, Front End Server o Director.</span><span class="sxs-lookup"><span data-stu-id="a254a-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="a254a-108">Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto per i certificati con caratteri jolly in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a254a-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a254a-109">Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="a254a-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="a254a-110">Per un elenco delle CA pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati per comunicazioni unificate e che hanno collaborato con Microsoft per assicurarsi che funzionino con la configurazione guidata certificati di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificato per le comunicazioni unificate per Exchange Server [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)e per Communications Server" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a254a-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="a254a-111">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato da altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="a254a-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="a254a-112">Per la versione 2013, Lync Server 2013 e altri prodotti server Microsoft, tra cui Exchange 2013 e SharePoint Server, supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="a254a-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="a254a-113">Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a254a-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="a254a-114">Per le connessioni dai client che eseguono il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non Richiedi) i certificati firmati utilizzando la funzione hash di crittografia SHA-256.</span><span class="sxs-lookup"><span data-stu-id="a254a-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="a254a-115">Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.</span><span class="sxs-lookup"><span data-stu-id="a254a-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="a254a-p106">Nelle tabelle seguenti sono indicati i requisiti dei certificati in base al ruolo del server per i pool Front End e i server Standard Edition. Sono tutti certificati del server Web standard con chiave privata non esportabili.</span><span class="sxs-lookup"><span data-stu-id="a254a-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="a254a-118">Si noti che l'utilizzo chiavi avanzato nel server viene configurato automaticamente quando si utilizza la Configurazione guidata certificati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="a254a-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a254a-119">Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.</span><span class="sxs-lookup"><span data-stu-id="a254a-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a254a-120">Se nel DNS sono stati configurati sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo del soggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="a254a-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="a254a-121">Certificati per il server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a254a-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="a254a-122">Certificato</span><span class="sxs-lookup"><span data-stu-id="a254a-122">Certificate</span></span></th>
<th><span data-ttu-id="a254a-123">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="a254a-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="a254a-124">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="a254a-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="a254a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a254a-125">Example</span></span></th>
<th><span data-ttu-id="a254a-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="a254a-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a254a-127">Predefinita</span><span class="sxs-lookup"><span data-stu-id="a254a-127">Default</span></span></p></td>
<td><p><span data-ttu-id="a254a-128">Nome di dominio completo (FQDN) del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-129">FQDN del pool e del nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="a254a-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="a254a-130">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="a254a-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="a254a-131">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="a254a-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="a254a-132">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-133">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a254a-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-134">Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="a254a-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="a254a-135">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="a254a-136">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="a254a-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a254a-137">Interno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="a254a-138">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="a254a-139">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-140">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="a254a-141">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="a254a-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="a254a-142">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-143">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="a254a-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-144">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-145">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-146">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="a254a-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="a254a-147">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-148">Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a254a-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="a254a-149">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="a254a-150">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="a254a-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a254a-151">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="a254a-152">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="a254a-153">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-154">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="a254a-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-155">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-156">Rispettare gli URL semplici per dominio SIP</span><span class="sxs-lookup"><span data-stu-id="a254a-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="a254a-157">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-158">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-159">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="a254a-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="a254a-160">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-161">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="a254a-162">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="a254a-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="a254a-163">Certificati per il Front End Server in un pool Front End</span><span class="sxs-lookup"><span data-stu-id="a254a-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="a254a-164">Certificato</span><span class="sxs-lookup"><span data-stu-id="a254a-164">Certificate</span></span></th>
<th><span data-ttu-id="a254a-165">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="a254a-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="a254a-166">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="a254a-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="a254a-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="a254a-167">Example</span></span></th>
<th><span data-ttu-id="a254a-168">Commenti</span><span class="sxs-lookup"><span data-stu-id="a254a-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a254a-169">Predefinita</span><span class="sxs-lookup"><span data-stu-id="a254a-169">Default</span></span></p></td>
<td><p><span data-ttu-id="a254a-170">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-171">FQDN del pool e FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="a254a-172">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="a254a-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="a254a-173">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="a254a-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="a254a-174">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-175">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a254a-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-176">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="a254a-177">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="a254a-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a254a-178">Interno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="a254a-179">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-180">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-181">FQDN Web interno (che non corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="a254a-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="a254a-182">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-183">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="a254a-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-184">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="a254a-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="a254a-185">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-186">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="a254a-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-187">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-189">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="a254a-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="a254a-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-191">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="a254a-192">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="a254a-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a254a-193">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="a254a-194">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-195">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-196">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="a254a-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-197">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-198">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="a254a-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-199">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-201">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="a254a-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="a254a-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a254a-203">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="a254a-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="a254a-204">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="a254a-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="a254a-205">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="a254a-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a254a-206">Certificato</span><span class="sxs-lookup"><span data-stu-id="a254a-206">Certificate</span></span></th>
<th><span data-ttu-id="a254a-207">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="a254a-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="a254a-208">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="a254a-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="a254a-209">Esempio</span><span class="sxs-lookup"><span data-stu-id="a254a-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a254a-210">Predefinita</span><span class="sxs-lookup"><span data-stu-id="a254a-210">Default</span></span></p></td>
<td><p><span data-ttu-id="a254a-211">FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="a254a-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-212">FQDN del Director, FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="a254a-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="a254a-213">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="a254a-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="a254a-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-215">Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a254a-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a254a-216">Interno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="a254a-217">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="a254a-218">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-219">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="a254a-220">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-221">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="a254a-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-222">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="a254a-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="a254a-223">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-224">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="a254a-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-225">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a254a-228">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="a254a-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="a254a-229">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="a254a-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="a254a-230">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a254a-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a254a-231">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="a254a-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="a254a-232">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="a254a-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-233">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="a254a-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="a254a-234">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="a254a-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a254a-235">Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.</span><span class="sxs-lookup"><span data-stu-id="a254a-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="a254a-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a254a-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a254a-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a254a-p107">Se è presente un pool Mediation Server autonomo, ognuno dei Mediation Server in esso contenuti richiederà i certificati riportati nella tabella seguente. Se si colloca un Mediation Server nei Front End Server, saranno sufficienti i certificati riportati nella tabella "Certificati per il Front End Server in un pool Front End" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a254a-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="a254a-240">Certificati per il Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="a254a-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a254a-241">Certificato</span><span class="sxs-lookup"><span data-stu-id="a254a-241">Certificate</span></span></th>
<th><span data-ttu-id="a254a-242">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="a254a-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="a254a-243">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="a254a-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="a254a-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="a254a-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a254a-245">Predefinita</span><span class="sxs-lookup"><span data-stu-id="a254a-245">Default</span></span></p></td>
<td><p><span data-ttu-id="a254a-246">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="a254a-247">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="a254a-248">FQDN del server membro del pool</span><span class="sxs-lookup"><span data-stu-id="a254a-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="a254a-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="a254a-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="a254a-250">Certificati per il Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="a254a-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a254a-251">Certificato</span><span class="sxs-lookup"><span data-stu-id="a254a-251">Certificate</span></span></th>
<th><span data-ttu-id="a254a-252">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="a254a-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="a254a-253">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="a254a-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="a254a-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="a254a-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a254a-255">Predefinita</span><span class="sxs-lookup"><span data-stu-id="a254a-255">Default</span></span></p></td>
<td><p><span data-ttu-id="a254a-256">FQDN del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a254a-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="a254a-257">SIP. &lt;SipDomain&gt; (è necessaria una voce per ogni dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="a254a-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="a254a-258">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="a254a-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a254a-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a254a-259">See Also</span></span>


[<span data-ttu-id="a254a-260">Supporto per i certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a254a-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

