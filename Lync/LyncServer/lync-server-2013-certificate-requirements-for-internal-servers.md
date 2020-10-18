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
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="c81e0-103">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81e0-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c81e0-104">_**Ultimo argomento modificato:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="c81e0-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="c81e0-105">I server interni che eseguono Lync Server e che richiedono i certificati includono il server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="c81e0-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="c81e0-106">Nella tabella seguente sono riportati i requisiti dei certificati per tali server.</span><span class="sxs-lookup"><span data-stu-id="c81e0-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="c81e0-107">È possibile utilizzare la configurazione guidata certificati di Lync Server per richiedere questi certificati.</span><span class="sxs-lookup"><span data-stu-id="c81e0-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c81e0-108">I certificati con caratteri jolly sono supportati per i nomi alternativi del soggetto associati agli URL semplici del pool Front End, Front End Server o Director.</span><span class="sxs-lookup"><span data-stu-id="c81e0-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="c81e0-109">Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto per i certificati con caratteri jolly in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c81e0-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c81e0-110">Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="c81e0-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="c81e0-111">Per un elenco delle CA pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati per comunicazioni unificate e che hanno collaborato con Microsoft per assicurarsi che funzionino con la configurazione guidata certificati di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificato per le comunicazioni unificate per Exchange Server e per Communications Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="c81e0-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="c81e0-112">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato da altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="c81e0-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="c81e0-113">Per la versione 2013, Lync Server 2013 e altri prodotti server Microsoft, tra cui Exchange 2013 e SharePoint Server, supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="c81e0-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="c81e0-114">Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="c81e0-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="c81e0-115">Per le connessioni dai client che eseguono il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) certificati firmati utilizzando la funzione hash di crittografia SHA-256.</span><span class="sxs-lookup"><span data-stu-id="c81e0-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="c81e0-116">Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.</span><span class="sxs-lookup"><span data-stu-id="c81e0-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="c81e0-p106">Nelle tabelle seguenti sono indicati i requisiti dei certificati in base al ruolo del server per i pool Front End e i server Standard Edition. Sono tutti certificati del server Web standard con chiave privata non esportabili.</span><span class="sxs-lookup"><span data-stu-id="c81e0-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="c81e0-119">Si noti che l'utilizzo chiavi avanzato nel server viene configurato automaticamente quando si utilizza la Configurazione guidata certificati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="c81e0-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c81e0-120">Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.</span><span class="sxs-lookup"><span data-stu-id="c81e0-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c81e0-121">Se nel DNS sono stati configurati sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo del soggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="c81e0-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="c81e0-122">Certificati per il server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c81e0-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="c81e0-123">Certificato</span><span class="sxs-lookup"><span data-stu-id="c81e0-123">Certificate</span></span></th>
<th><span data-ttu-id="c81e0-124">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="c81e0-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="c81e0-125">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="c81e0-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="c81e0-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81e0-126">Example</span></span></th>
<th><span data-ttu-id="c81e0-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="c81e0-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-128">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="c81e0-128">Default</span></span></p></td>
<td><p><span data-ttu-id="c81e0-129">Nome di dominio completo (FQDN) del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-130">FQDN del pool e del nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="c81e0-131">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="c81e0-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="c81e0-132">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="c81e0-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="c81e0-133">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-134">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c81e0-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-135">Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="c81e0-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="c81e0-136">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="c81e0-137">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="c81e0-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81e0-138">Interno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="c81e0-139">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="c81e0-140">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-141">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="c81e0-142">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="c81e0-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="c81e0-143">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-144">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-145">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-146">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-147">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="c81e0-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="c81e0-148">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-149">Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c81e0-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="c81e0-150">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="c81e0-151">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="c81e0-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-152">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="c81e0-153">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="c81e0-154">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-155">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="c81e0-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-156">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-157">Rispettare gli URL semplici per dominio SIP</span><span class="sxs-lookup"><span data-stu-id="c81e0-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="c81e0-158">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-159">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-160">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="c81e0-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="c81e0-161">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-162">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="c81e0-163">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="c81e0-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="c81e0-164">Certificati per il Front End Server in un pool Front End</span><span class="sxs-lookup"><span data-stu-id="c81e0-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="c81e0-165">Certificato</span><span class="sxs-lookup"><span data-stu-id="c81e0-165">Certificate</span></span></th>
<th><span data-ttu-id="c81e0-166">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="c81e0-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="c81e0-167">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="c81e0-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="c81e0-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81e0-168">Example</span></span></th>
<th><span data-ttu-id="c81e0-169">Commenti</span><span class="sxs-lookup"><span data-stu-id="c81e0-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-170">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="c81e0-170">Default</span></span></p></td>
<td><p><span data-ttu-id="c81e0-171">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-172">FQDN del pool e FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="c81e0-173">Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="c81e0-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="c81e0-174">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="c81e0-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="c81e0-175">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-176">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c81e0-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-177">La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="c81e0-178">È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="c81e0-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81e0-179">Interno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="c81e0-180">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-181">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-182">FQDN Web interno (che non corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="c81e0-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="c81e0-183">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-184">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="c81e0-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-185">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="c81e0-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="c81e0-186">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-187">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-188">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-189">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-190">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="c81e0-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="c81e0-191">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-192">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="c81e0-193">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="c81e0-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-194">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="c81e0-195">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-196">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-197">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="c81e0-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-198">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-199">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-200">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-201">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-202">Nel caso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="c81e0-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="c81e0-203">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c81e0-204">Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c81e0-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="c81e0-205">Le voci con caratteri jolly sono supportate per le voci di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="c81e0-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="c81e0-206">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="c81e0-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81e0-207">Certificato</span><span class="sxs-lookup"><span data-stu-id="c81e0-207">Certificate</span></span></th>
<th><span data-ttu-id="c81e0-208">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="c81e0-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="c81e0-209">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="c81e0-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="c81e0-210">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81e0-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-211">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="c81e0-211">Default</span></span></p></td>
<td><p><span data-ttu-id="c81e0-212">FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c81e0-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-213">FQDN del Director, FQDN del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c81e0-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="c81e0-214">Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="c81e0-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="c81e0-215">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-216">Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c81e0-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81e0-217">Interno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="c81e0-218">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="c81e0-219">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-220">FQDN Web interno, che corrisponde all'FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="c81e0-221">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-222">FQDN del pool Lync</span><span class="sxs-lookup"><span data-stu-id="c81e0-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-223">URL semplici per le riunioni (meet)</span><span class="sxs-lookup"><span data-stu-id="c81e0-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="c81e0-224">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-225">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-226">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-227">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-228">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-229">Esterno Web</span><span class="sxs-lookup"><span data-stu-id="c81e0-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="c81e0-230">FQDN del server</span><span class="sxs-lookup"><span data-stu-id="c81e0-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="c81e0-231">Ognuno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81e0-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c81e0-232">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="c81e0-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="c81e0-233">URL semplice per l'accesso esterno (dialin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-234">URL semplice per l'accesso amministrativo (admin)</span><span class="sxs-lookup"><span data-stu-id="c81e0-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="c81e0-235">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="c81e0-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c81e0-236">Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.</span><span class="sxs-lookup"><span data-stu-id="c81e0-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="c81e0-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="c81e0-238">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c81e0-p107">Se è presente un pool Mediation Server autonomo, ognuno dei Mediation Server in esso contenuti richiederà i certificati riportati nella tabella seguente. Se si colloca un Mediation Server nei Front End Server, saranno sufficienti i certificati riportati nella tabella "Certificati per il Front End Server in un pool Front End" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c81e0-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="c81e0-241">Certificati per il Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="c81e0-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81e0-242">Certificato</span><span class="sxs-lookup"><span data-stu-id="c81e0-242">Certificate</span></span></th>
<th><span data-ttu-id="c81e0-243">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="c81e0-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="c81e0-244">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="c81e0-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="c81e0-245">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81e0-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-246">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="c81e0-246">Default</span></span></p></td>
<td><p><span data-ttu-id="c81e0-247">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="c81e0-248">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="c81e0-249">FQDN del server membro del pool</span><span class="sxs-lookup"><span data-stu-id="c81e0-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="c81e0-250">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="c81e0-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="c81e0-251">Certificati per il Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c81e0-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81e0-252">Certificato</span><span class="sxs-lookup"><span data-stu-id="c81e0-252">Certificate</span></span></th>
<th><span data-ttu-id="c81e0-253">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="c81e0-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="c81e0-254">Nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="c81e0-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="c81e0-255">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81e0-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81e0-256">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="c81e0-256">Default</span></span></p></td>
<td><p><span data-ttu-id="c81e0-257">FQDN del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c81e0-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="c81e0-258">SIP. &lt; SipDomain &gt; (è necessaria una voce per ogni dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="c81e0-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="c81e0-259">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="c81e0-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c81e0-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c81e0-260">See Also</span></span>


[<span data-ttu-id="c81e0-261">Supporto per i certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81e0-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

