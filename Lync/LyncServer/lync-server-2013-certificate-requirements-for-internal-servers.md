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
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526243"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="0080e-102">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0080e-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0080e-103">_**Ultimo argomento modificato:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="0080e-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="0080e-104">I server interni che eseguono Lync Server e che richiedono i certificati includono il server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="0080e-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="0080e-105">Nella tabella seguente sono riportati i requisiti dei certificati per tali server.</span><span class="sxs-lookup"><span data-stu-id="0080e-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="0080e-106">È possibile utilizzare la configurazione guidata certificati di Lync Server per richiedere questi certificati.</span><span class="sxs-lookup"><span data-stu-id="0080e-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0080e-107">I certificati con caratteri jolly sono supportati per i nomi alternativi del soggetto associati agli URL semplici del pool Front End, Front End Server o Director.</span><span class="sxs-lookup"><span data-stu-id="0080e-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="0080e-108">Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto per i certificati con caratteri jolly in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0080e-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0080e-109">Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="0080e-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="0080e-110">Per un elenco delle CA pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati per comunicazioni unificate e che hanno collaborato con Microsoft per assicurarsi che funzionino con la configurazione guidata certificati di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificato per le comunicazioni unificate per Exchange Server e per Communications Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="0080e-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="0080e-111">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato da altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="0080e-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="0080e-112">Per la versione 2013, Lync Server 2013 e altri prodotti server Microsoft, tra cui Exchange 2013 e SharePoint Server, supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="0080e-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="0080e-113">Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0080e-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="0080e-114">Per le connessioni dai client che eseguono il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) certificati firmati utilizzando la funzione hash di crittografia SHA-256.</span><span class="sxs-lookup"><span data-stu-id="0080e-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="0080e-115">Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.</span><span class="sxs-lookup"><span data-stu-id="0080e-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="0080e-p106">Nelle tabelle seguenti sono indicati i requisiti dei certificati in base al ruolo del server per i pool Front End e i server Standard Edition. Sono tutti certificati del server Web standard con chiave privata non esportabili.</span><span class="sxs-lookup"><span data-stu-id="0080e-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="0080e-118">Si noti che l'utilizzo chiavi avanzato nel server viene configurato automaticamente quando si utilizza la Configurazione guidata certificati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="0080e-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0080e-119">Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.</span><span class="sxs-lookup"><span data-stu-id="0080e-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0080e-120">Se nel DNS sono stati configurati sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo del soggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="0080e-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="0080e-121">Certificati per il server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0080e-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="0080e-122">Certificato</span><span class="sxs-lookup"><span data-stu-id="0080e-122">Certificate</span></span></th>
<th><span data-ttu-id="0080e-123">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="0080e-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="0080e-124">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="0080e-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="0080e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="0080e-125">Example</span></span></th>
<th><span data-ttu-id="0080e-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="0080e-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0080e-127">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="0080e-127">Default</span></span></p></td>
<td><p><span data-ttu-id="0080e-128">Nome di dominio completo (FQDN) del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-129">FQDN del pool e del nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="0080e-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="0080e-130">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="0080e-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="0080e-131">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="0080e-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="0080e-132">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-133">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0080e-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-134">Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="0080e-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="0080e-135">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="0080e-136">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="0080e-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0080e-137">Interno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="0080e-138">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="0080e-139">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-140">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="0080e-141">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="0080e-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="0080e-142">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-143">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="0080e-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-144">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-145">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-146">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="0080e-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="0080e-147">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-148">Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="0080e-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="0080e-149">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="0080e-150">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="0080e-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0080e-151">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="0080e-152">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="0080e-153">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-154">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="0080e-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-155">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-156">Rispettare gli URL semplici per dominio SIP</span><span class="sxs-lookup"><span data-stu-id="0080e-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="0080e-157">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-158">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-159">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="0080e-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="0080e-160">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-161">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="0080e-162">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="0080e-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="0080e-163">Certificati per il Front End Server in un pool Front End</span><span class="sxs-lookup"><span data-stu-id="0080e-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="0080e-164">Certificato</span><span class="sxs-lookup"><span data-stu-id="0080e-164">Certificate</span></span></th>
<th><span data-ttu-id="0080e-165">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="0080e-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="0080e-166">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="0080e-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="0080e-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="0080e-167">Example</span></span></th>
<th><span data-ttu-id="0080e-168">Commenti</span><span class="sxs-lookup"><span data-stu-id="0080e-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0080e-169">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="0080e-169">Default</span></span></p></td>
<td><p><span data-ttu-id="0080e-170">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-171">FQDN del pool e FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="0080e-172">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="0080e-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="0080e-173">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="0080e-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="0080e-174">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-175">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0080e-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-176">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="0080e-177">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="0080e-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0080e-178">Interno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="0080e-179">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-180">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-181">FQDN Web interno (che non corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="0080e-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="0080e-182">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-183">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="0080e-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-184">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="0080e-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="0080e-185">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-186">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="0080e-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-187">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-189">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="0080e-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="0080e-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-191">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="0080e-192">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="0080e-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0080e-193">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="0080e-194">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-195">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-196">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="0080e-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-197">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-198">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="0080e-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-199">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-201">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="0080e-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="0080e-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0080e-203">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0080e-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="0080e-204">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="0080e-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="0080e-205">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="0080e-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0080e-206">Certificato</span><span class="sxs-lookup"><span data-stu-id="0080e-206">Certificate</span></span></th>
<th><span data-ttu-id="0080e-207">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="0080e-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="0080e-208">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="0080e-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="0080e-209">Esempio</span><span class="sxs-lookup"><span data-stu-id="0080e-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0080e-210">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="0080e-210">Default</span></span></p></td>
<td><p><span data-ttu-id="0080e-211">FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="0080e-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-212">FQDN del Director, FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="0080e-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="0080e-213">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="0080e-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="0080e-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-215">Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0080e-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0080e-216">Interno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="0080e-217">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="0080e-218">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-219">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="0080e-220">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-221">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="0080e-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-222">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="0080e-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="0080e-223">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-224">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="0080e-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-225">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0080e-228">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="0080e-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="0080e-229">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="0080e-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="0080e-230">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0080e-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0080e-231">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="0080e-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="0080e-232">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="0080e-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-233">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="0080e-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="0080e-234">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="0080e-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0080e-235">Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.</span><span class="sxs-lookup"><span data-stu-id="0080e-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="0080e-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0080e-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0080e-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0080e-p107">Se è presente un pool Mediation Server autonomo, ognuno dei Mediation Server in esso contenuti richiederà i certificati riportati nella tabella seguente. Se si colloca un Mediation Server nei Front End Server, saranno sufficienti i certificati riportati nella tabella "Certificati per il Front End Server in un pool Front End" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0080e-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="0080e-240">Certificati per il Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="0080e-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0080e-241">Certificato</span><span class="sxs-lookup"><span data-stu-id="0080e-241">Certificate</span></span></th>
<th><span data-ttu-id="0080e-242">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="0080e-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="0080e-243">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="0080e-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="0080e-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="0080e-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0080e-245">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="0080e-245">Default</span></span></p></td>
<td><p><span data-ttu-id="0080e-246">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="0080e-247">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="0080e-248">FQDN del server membro del pool</span><span class="sxs-lookup"><span data-stu-id="0080e-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="0080e-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="0080e-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="0080e-250">Certificati per il Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="0080e-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0080e-251">Certificato</span><span class="sxs-lookup"><span data-stu-id="0080e-251">Certificate</span></span></th>
<th><span data-ttu-id="0080e-252">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="0080e-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="0080e-253">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="0080e-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="0080e-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="0080e-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0080e-255">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="0080e-255">Default</span></span></p></td>
<td><p><span data-ttu-id="0080e-256">FQDN del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0080e-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="0080e-257">SIP. &lt; SipDomain &gt; (è necessaria una voce per ogni dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="0080e-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="0080e-258">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="0080e-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0080e-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0080e-259">See Also</span></span>


[<span data-ttu-id="0080e-260">Supporto per i certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0080e-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

