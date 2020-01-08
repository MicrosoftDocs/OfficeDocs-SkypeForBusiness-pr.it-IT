---
title: 'Lync Server 2013: Requisiti dei certificati per i server interni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="cbe94-102">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe94-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbe94-103">_**Argomento Ultima modifica:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="cbe94-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="cbe94-104">I server interni che esegue Lync Server e che richiedono certificati includono server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="cbe94-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="cbe94-105">La tabella seguente mostra i requisiti dei certificati per questi server.</span><span class="sxs-lookup"><span data-stu-id="cbe94-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="cbe94-106">È possibile usare la configurazione guidata certificati di Lync Server per richiedere questi certificati.</span><span class="sxs-lookup"><span data-stu-id="cbe94-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="cbe94-107">I certificati con caratteri jolly sono supportati per i nomi alternativi dell'oggetto associati agli URL semplici nel pool Front-End, nel server front fine o nel Director.</span><span class="sxs-lookup"><span data-stu-id="cbe94-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="cbe94-108">Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto di certificati jolly in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cbe94-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="cbe94-109">Anche se è consigliata un'autorità di certificazione (CA) interna per i server interni, è anche possibile usare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="cbe94-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="cbe94-110">Per un elenco delle autorità di certificazione pubbliche che includono certificati che soddisfano requisiti specifici per i certificati di Unified Communications (UC) e che hanno collaborato con Microsoft per verificare che funzionino con la procedura guidata certificato di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificati per le comunicazioni unificate [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)per Exchange Server e per Communications Server".</span><span class="sxs-lookup"><span data-stu-id="cbe94-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="cbe94-111">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato dalle altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="cbe94-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="cbe94-112">Per la versione di 2013, Lync Server 2013 e altri prodotti di Microsoft Server, inclusi Exchange 2013 e SharePoint Server, supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="cbe94-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="cbe94-113">Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="cbe94-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="cbe94-114">Per le connessioni da client che utilizzano il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non Richiedi) certificati firmati con la funzione hash crittografico SHA-256.</span><span class="sxs-lookup"><span data-stu-id="cbe94-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="cbe94-115">Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.</span><span class="sxs-lookup"><span data-stu-id="cbe94-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="cbe94-116">Le tabelle seguenti mostrano i requisiti dei certificati per il ruolo del server per i pool Front end e i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cbe94-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="cbe94-117">Tutti questi sono certificati server Web standard, chiave privata, non esportabile.</span><span class="sxs-lookup"><span data-stu-id="cbe94-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="cbe94-118">Tieni presente che l'utilizzo della chiave avanzata del server viene configurato automaticamente quando usi la procedura guidata certificati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="cbe94-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cbe94-119">Ogni nome descrittivo del certificato deve essere univoco nell'archivio di computer.</span><span class="sxs-lookup"><span data-stu-id="cbe94-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="cbe94-120">Se nel DNS è stato configurato sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo soggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="cbe94-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="cbe94-121">Certificati per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="cbe94-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="cbe94-122">Certificato</span><span class="sxs-lookup"><span data-stu-id="cbe94-122">Certificate</span></span></th>
<th><span data-ttu-id="cbe94-123">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="cbe94-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="cbe94-124">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="cbe94-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="cbe94-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbe94-125">Example</span></span></th>
<th><span data-ttu-id="cbe94-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="cbe94-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-127">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cbe94-127">Default</span></span></p></td>
<td><p><span data-ttu-id="cbe94-128">Nome di dominio completo (FQDN) del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-129">FQDN del pool e il nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="cbe94-130">Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="cbe94-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="cbe94-131">Se questo pool è il server di accesso automatico per i client e la corrispondenza Strict Domain Name System (DNS) è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="cbe94-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="cbe94-132">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-133">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-134">Nel server Standard Edition il nome di dominio completo del server è uguale al nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="cbe94-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="cbe94-135">La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="cbe94-136">Puoi anche usare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="cbe94-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe94-137">Interno Web</span><span class="sxs-lookup"><span data-stu-id="cbe94-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="cbe94-138">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="cbe94-139">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-140">FQDN Web interno (che corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="cbe94-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="cbe94-141">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="cbe94-142">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-143">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="cbe94-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-144">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-145">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-146">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="cbe94-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="cbe94-147">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-148">Non è possibile eseguire l'override del FQDN Web interno in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cbe94-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="cbe94-149">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="cbe94-150">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="cbe94-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-151">Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="cbe94-152">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="cbe94-153">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-154">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-155">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-156">Soddisfare URL semplici per ogni dominio SIP</span><span class="sxs-lookup"><span data-stu-id="cbe94-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="cbe94-157">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-158">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-159">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="cbe94-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="cbe94-160">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-161">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="cbe94-162">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="cbe94-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="cbe94-163">Certificati per il server front-end in un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="cbe94-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="cbe94-164">Certificato</span><span class="sxs-lookup"><span data-stu-id="cbe94-164">Certificate</span></span></th>
<th><span data-ttu-id="cbe94-165">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="cbe94-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="cbe94-166">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="cbe94-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="cbe94-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbe94-167">Example</span></span></th>
<th><span data-ttu-id="cbe94-168">Commenti</span><span class="sxs-lookup"><span data-stu-id="cbe94-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-169">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cbe94-169">Default</span></span></p></td>
<td><p><span data-ttu-id="cbe94-170">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-171">FQDN del pool e del nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="cbe94-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="cbe94-172">Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="cbe94-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="cbe94-173">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="cbe94-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="cbe94-174">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-175">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-176">La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="cbe94-177">Puoi anche usare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="cbe94-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe94-178">Interno Web</span><span class="sxs-lookup"><span data-stu-id="cbe94-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="cbe94-179">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-180">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-181">FQDN Web interno (che non corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="cbe94-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="cbe94-182">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-183">FQDN del pool di Lync</span><span class="sxs-lookup"><span data-stu-id="cbe94-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-184">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="cbe94-185">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-186">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="cbe94-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-187">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-189">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="cbe94-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="cbe94-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-191">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="cbe94-192">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="cbe94-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-193">Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="cbe94-194">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-195">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-196">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-197">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-198">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="cbe94-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-199">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-201">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="cbe94-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="cbe94-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cbe94-203">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbe94-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="cbe94-204">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="cbe94-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="cbe94-205">Certificati per Director</span><span class="sxs-lookup"><span data-stu-id="cbe94-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbe94-206">Certificato</span><span class="sxs-lookup"><span data-stu-id="cbe94-206">Certificate</span></span></th>
<th><span data-ttu-id="cbe94-207">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="cbe94-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="cbe94-208">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="cbe94-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="cbe94-209">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbe94-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-210">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cbe94-210">Default</span></span></p></td>
<td><p><span data-ttu-id="cbe94-211">Nome di dominio completo del pool di Director</span><span class="sxs-lookup"><span data-stu-id="cbe94-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-212">Nome di dominio completo del Director, FQDN del pool di Director</span><span class="sxs-lookup"><span data-stu-id="cbe94-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="cbe94-213">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="cbe94-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="cbe94-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-215">Se questo pool di Director è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe94-216">Interno Web</span><span class="sxs-lookup"><span data-stu-id="cbe94-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="cbe94-217">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="cbe94-218">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-219">FQDN Web interno (che corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="cbe94-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="cbe94-220">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-221">FQDN del pool di Lync</span><span class="sxs-lookup"><span data-stu-id="cbe94-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-222">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="cbe94-223">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-224">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="cbe94-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-225">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-228">Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="cbe94-229">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="cbe94-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="cbe94-230">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbe94-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbe94-231">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="cbe94-232">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cbe94-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-233">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="cbe94-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="cbe94-234">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cbe94-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cbe94-235">Il nome FQDN Web esterno del Director deve essere diverso dal pool Front-end o dal server front-end.</span><span class="sxs-lookup"><span data-stu-id="cbe94-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="cbe94-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="cbe94-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cbe94-238">Se si dispone di un pool di Mediation Server autonomo, i server di mediazione in ognuno di essi richiedono i certificati elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cbe94-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="cbe94-239">Se si colloca Mediation Server con i server front-end, i certificati elencati nella tabella "certificati per il server front-end in pool Front-End" in questo argomento sono sufficienti.</span><span class="sxs-lookup"><span data-stu-id="cbe94-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="cbe94-240">Certificati per Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="cbe94-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbe94-241">Certificato</span><span class="sxs-lookup"><span data-stu-id="cbe94-241">Certificate</span></span></th>
<th><span data-ttu-id="cbe94-242">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="cbe94-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="cbe94-243">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="cbe94-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="cbe94-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbe94-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-245">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cbe94-245">Default</span></span></p></td>
<td><p><span data-ttu-id="cbe94-246">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="cbe94-247">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="cbe94-248">FQDN del server dei membri del pool</span><span class="sxs-lookup"><span data-stu-id="cbe94-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="cbe94-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="cbe94-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="cbe94-250">Certificati per Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="cbe94-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbe94-251">Certificato</span><span class="sxs-lookup"><span data-stu-id="cbe94-251">Certificate</span></span></th>
<th><span data-ttu-id="cbe94-252">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="cbe94-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="cbe94-253">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="cbe94-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="cbe94-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbe94-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe94-255">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cbe94-255">Default</span></span></p></td>
<td><p><span data-ttu-id="cbe94-256">Nome di dominio completo dell'accessorio</span><span class="sxs-lookup"><span data-stu-id="cbe94-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="cbe94-257">SIP. &lt;SipDomain&gt; (serve una voce per ogni dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="cbe94-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="cbe94-258">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="cbe94-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cbe94-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbe94-259">See Also</span></span>


[<span data-ttu-id="cbe94-260">Supporto dei certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe94-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

