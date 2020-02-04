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

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="6fd9e-102">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fd9e-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd9e-103">_**Argomento Ultima modifica:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="6fd9e-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="6fd9e-104">I server interni che esegue Lync Server e che richiedono certificati includono server Standard Edition, Enterprise Edition Front End Server, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="6fd9e-105">La tabella seguente mostra i requisiti dei certificati per questi server.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="6fd9e-106">È possibile usare la configurazione guidata certificati di Lync Server per richiedere questi certificati.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6fd9e-107">I certificati con caratteri jolly sono supportati per i nomi alternativi dell'oggetto associati agli URL semplici nel pool Front-End, nel server front fine o nel Director.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="6fd9e-108">Per informazioni dettagliate sul supporto dei certificati con caratteri jolly, vedere <A href="lync-server-2013-wildcard-certificate-support.md">supporto di certificati jolly in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6fd9e-109">Anche se è consigliata un'autorità di certificazione (CA) interna per i server interni, è anche possibile usare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="6fd9e-110">Per un elenco delle autorità di certificazione pubbliche che includono certificati che soddisfano requisiti specifici per i certificati di Unified Communications (UC) e che hanno collaborato con Microsoft per verificare che funzionino con la procedura guidata certificato di Lync Server, vedere l'articolo Microsoft Knowledge Base 929395, "partner di certificati per le comunicazioni unificate [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)per Exchange Server e per Communications Server".</span><span class="sxs-lookup"><span data-stu-id="6fd9e-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="6fd9e-111">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato dalle altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="6fd9e-112">Per la versione di 2013, Lync Server 2013 e altri prodotti di Microsoft Server, inclusi Exchange 2013 e SharePoint Server, supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="6fd9e-113">Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="6fd9e-114">Per le connessioni da client che utilizzano il sistema operativo Windows 7, il sistema operativo Windows Server 2008, il sistema operativo Windows Server 2008 R2, il sistema operativo Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 include il supporto per (ma non Richiedi) certificati firmati con la funzione hash crittografico SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="6fd9e-115">Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="6fd9e-116">Le tabelle seguenti mostrano i requisiti dei certificati per il ruolo del server per i pool Front end e i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="6fd9e-117">Tutti questi sono certificati server Web standard, chiave privata, non esportabile.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="6fd9e-118">Tieni presente che l'utilizzo della chiave avanzata del server viene configurato automaticamente quando usi la procedura guidata certificati per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fd9e-119">Ogni nome descrittivo del certificato deve essere univoco nell'archivio di computer.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6fd9e-120">Se nel DNS è stato configurato sipinternal.contoso.com o sipexternal.contoso.com, sarà necessario aggiungerli nel nome alternativo soggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="6fd9e-121">Certificati per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6fd9e-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="6fd9e-122">Certificato</span><span class="sxs-lookup"><span data-stu-id="6fd9e-122">Certificate</span></span></th>
<th><span data-ttu-id="6fd9e-123">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="6fd9e-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6fd9e-124">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="6fd9e-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="6fd9e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-125">Example</span></span></th>
<th><span data-ttu-id="6fd9e-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="6fd9e-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-127">Predefinita</span><span class="sxs-lookup"><span data-stu-id="6fd9e-127">Default</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-128">Nome di dominio completo (FQDN) del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-129">FQDN del pool e il nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="6fd9e-130">Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6fd9e-131">Se questo pool è il server di accesso automatico per i client e la corrispondenza Strict Domain Name System (DNS) è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="6fd9e-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-132">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-133">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-134">Nel server Standard Edition il nome di dominio completo del server è uguale al nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="6fd9e-135">La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6fd9e-136">Puoi anche usare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9e-137">Interno Web</span><span class="sxs-lookup"><span data-stu-id="6fd9e-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-138">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-139">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-140">FQDN Web interno (che corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="6fd9e-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-141">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-142">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-143">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="6fd9e-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-144">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-145">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-146">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6fd9e-147">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-148">Non è possibile eseguire l'override del FQDN Web interno in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="6fd9e-149">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6fd9e-150">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-151">Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-152">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-153">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-154">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-155">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-156">Soddisfare URL semplici per ogni dominio SIP</span><span class="sxs-lookup"><span data-stu-id="6fd9e-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-157">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-158">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-159">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6fd9e-160">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-161">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6fd9e-162">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="6fd9e-163">Certificati per il server front-end in un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="6fd9e-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="6fd9e-164">Certificato</span><span class="sxs-lookup"><span data-stu-id="6fd9e-164">Certificate</span></span></th>
<th><span data-ttu-id="6fd9e-165">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="6fd9e-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6fd9e-166">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="6fd9e-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="6fd9e-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-167">Example</span></span></th>
<th><span data-ttu-id="6fd9e-168">Commenti</span><span class="sxs-lookup"><span data-stu-id="6fd9e-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-169">Predefinita</span><span class="sxs-lookup"><span data-stu-id="6fd9e-169">Default</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-170">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-171">FQDN del pool e del nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="6fd9e-172">Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6fd9e-173">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="6fd9e-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-174">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-175">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-176">La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6fd9e-177">Puoi anche usare questo certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9e-178">Interno Web</span><span class="sxs-lookup"><span data-stu-id="6fd9e-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-179">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-180">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-181">FQDN Web interno (che non corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="6fd9e-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-182">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-183">FQDN del pool di Lync</span><span class="sxs-lookup"><span data-stu-id="6fd9e-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-184">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-185">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-186">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="6fd9e-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-187">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-189">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6fd9e-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-191">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6fd9e-192">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-193">Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-194">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-195">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-196">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-197">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-198">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="6fd9e-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-199">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-201">Uso di un certificato con caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6fd9e-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-203">Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6fd9e-204">Le voci con caratteri jolly sono supportate per le voci URL semplici.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="6fd9e-205">Certificati per Director</span><span class="sxs-lookup"><span data-stu-id="6fd9e-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd9e-206">Certificato</span><span class="sxs-lookup"><span data-stu-id="6fd9e-206">Certificate</span></span></th>
<th><span data-ttu-id="6fd9e-207">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="6fd9e-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6fd9e-208">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="6fd9e-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="6fd9e-209">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-210">Predefinita</span><span class="sxs-lookup"><span data-stu-id="6fd9e-210">Default</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-211">Nome di dominio completo del pool di Director</span><span class="sxs-lookup"><span data-stu-id="6fd9e-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-212">Nome di dominio completo del Director, FQDN del pool di Director</span><span class="sxs-lookup"><span data-stu-id="6fd9e-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="6fd9e-213">Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="6fd9e-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-215">Se questo pool di Director è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9e-216">Interno Web</span><span class="sxs-lookup"><span data-stu-id="6fd9e-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-217">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-218">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-219">FQDN Web interno (che corrisponde al nome di dominio completo del server)</span><span class="sxs-lookup"><span data-stu-id="6fd9e-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-220">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-221">FQDN del pool di Lync</span><span class="sxs-lookup"><span data-stu-id="6fd9e-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-222">Soddisfare URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-223">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-224">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="6fd9e-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-225">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-228">Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-229">Nome di dominio completo del server</span><span class="sxs-lookup"><span data-stu-id="6fd9e-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-230">Ognuna delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fd9e-231">FQDN Web esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-232">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6fd9e-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-233">URL semplice amministratore</span><span class="sxs-lookup"><span data-stu-id="6fd9e-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6fd9e-234">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="6fd9e-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6fd9e-235">Il nome FQDN Web esterno del Director deve essere diverso dal pool Front-end o dal server front-end.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="6fd9e-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6fd9e-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6fd9e-238">Se si dispone di un pool di Mediation Server autonomo, i server di mediazione in ognuno di essi richiedono i certificati elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="6fd9e-239">Se si colloca Mediation Server con i server front-end, i certificati elencati nella tabella "certificati per il server front-end in pool Front-End" in questo argomento sono sufficienti.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="6fd9e-240">Certificati per Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="6fd9e-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd9e-241">Certificato</span><span class="sxs-lookup"><span data-stu-id="6fd9e-241">Certificate</span></span></th>
<th><span data-ttu-id="6fd9e-242">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="6fd9e-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6fd9e-243">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="6fd9e-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="6fd9e-244">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-245">Predefinita</span><span class="sxs-lookup"><span data-stu-id="6fd9e-245">Default</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-246">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-247">Nome di dominio completo del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="6fd9e-248">FQDN del server dei membri del pool</span><span class="sxs-lookup"><span data-stu-id="6fd9e-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="6fd9e-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="6fd9e-250">Certificati per Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6fd9e-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd9e-251">Certificato</span><span class="sxs-lookup"><span data-stu-id="6fd9e-251">Certificate</span></span></th>
<th><span data-ttu-id="6fd9e-252">Nome soggetto/nome comune</span><span class="sxs-lookup"><span data-stu-id="6fd9e-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6fd9e-253">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="6fd9e-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="6fd9e-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9e-255">Predefinita</span><span class="sxs-lookup"><span data-stu-id="6fd9e-255">Default</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-256">Nome di dominio completo dell'accessorio</span><span class="sxs-lookup"><span data-stu-id="6fd9e-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-257">SIP. &lt;SipDomain&gt; (serve una voce per ogni dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="6fd9e-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="6fd9e-258">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="6fd9e-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6fd9e-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fd9e-259">See Also</span></span>


[<span data-ttu-id="6fd9e-260">Supporto dei certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fd9e-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

