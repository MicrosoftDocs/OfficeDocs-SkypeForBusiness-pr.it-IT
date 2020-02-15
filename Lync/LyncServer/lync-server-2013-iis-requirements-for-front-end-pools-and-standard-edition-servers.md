---
title: Requisiti di IIS per pool Front end e server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="ad1e7-102">Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad1e7-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad1e7-103">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ad1e7-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ad1e7-104">Per i server Standard Edition e front end server e Director, il programma di installazione di Lync Server 2013 crea directory virtuali in Internet Information Services (IIS) per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad1e7-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="ad1e7-105">Consentire agli utenti di scaricare file dal servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="ad1e7-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="ad1e7-106">Per consentire ai client di ottenere gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="ad1e7-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="ad1e7-107">Abilitare le conferenze</span><span class="sxs-lookup"><span data-stu-id="ad1e7-107">To enable conferencing</span></span>

  - <span data-ttu-id="ad1e7-108">Consentire agli utenti di scaricare il contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="ad1e7-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="ad1e7-109">Consentire agli utenti di espandere i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ad1e7-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="ad1e7-110">Abilitare le conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="ad1e7-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="ad1e7-111">Abilitare le funzionalità di Response Group</span><span class="sxs-lookup"><span data-stu-id="ad1e7-111">To enable response group features</span></span>

<span data-ttu-id="ad1e7-112">Inoltre, l'aggiornamento cumulativo per Lync Server 2010: il programma di installazione di novembre 2011 crea directory virtuali in IIS per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad1e7-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="ad1e7-113">Nei Front End Server o nei server Standard Edition per supportare la funzionalità per dispositivi mobili, ad esempio messaggistica istantanea e presenza, per i telefoni cellulari</span><span class="sxs-lookup"><span data-stu-id="ad1e7-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="ad1e7-114">Nei Front End Server o nei server Standard Edition e nei direttori per consentire ai dispositivi mobili di individuare automaticamente le risorse mobili</span><span class="sxs-lookup"><span data-stu-id="ad1e7-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="ad1e7-115">Se si distribuiscono dispositivi mobili, è consigliabile utilizzare IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="ad1e7-116">Il programma di installazione di Lync Server Mobility Service imposta alcuni flag di ASP.NET per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="ad1e7-117">IIS 7.5 viene installato per impostazione predefinita in Windows Server 2008 R2 e le impostazioni ASP.NET vengono modificate automaticamente dal programma di installazione del servizio per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="ad1e7-118">Se si utilizza IIS 7.0 in Windows Server 2008, è necessario modificare manualmente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="ad1e7-119">Per l'installazione di Lync Server, è necessario installare i seguenti moduli IIS:</span><span class="sxs-lookup"><span data-stu-id="ad1e7-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ad1e7-120">Se l'organizzazione richiede l'individuazione di IIS e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server nella finestra di dialogo Imposta.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="ad1e7-121">Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server verranno distribuiti nell'unità.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="ad1e7-122">Per informazioni dettagliate su come spostare il INETPUB distribuito da Windows Server Manager durante l'installazione di IIS, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>vedere.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="ad1e7-123">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="ad1e7-123">Static Content</span></span>

  - <span data-ttu-id="ad1e7-124">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="ad1e7-124">Default Document</span></span>

  - <span data-ttu-id="ad1e7-125">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="ad1e7-125">HTTP Errors</span></span>

  - <span data-ttu-id="ad1e7-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ad1e7-126">ASP.NET</span></span>

  - <span data-ttu-id="ad1e7-127">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="ad1e7-127">.NET Extensibility</span></span>

  - <span data-ttu-id="ad1e7-128">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="ad1e7-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="ad1e7-129">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="ad1e7-129">ISAPI Filters</span></span>

  - <span data-ttu-id="ad1e7-130">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="ad1e7-130">HTTP Logging</span></span>

  - <span data-ttu-id="ad1e7-131">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="ad1e7-131">Logging Tools</span></span>

  - <span data-ttu-id="ad1e7-132">Analisi della</span><span class="sxs-lookup"><span data-stu-id="ad1e7-132">Tracing</span></span>

  - <span data-ttu-id="ad1e7-133">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="ad1e7-133">Windows Authentication</span></span>

  - <span data-ttu-id="ad1e7-134">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="ad1e7-134">Request Filtering</span></span>

  - <span data-ttu-id="ad1e7-135">Compressione contenuto statico</span><span class="sxs-lookup"><span data-stu-id="ad1e7-135">Static Content Compression</span></span>

  - <span data-ttu-id="ad1e7-136">Compressione contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="ad1e7-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="ad1e7-137">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="ad1e7-137">IIS Management Console</span></span>

  - <span data-ttu-id="ad1e7-138">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="ad1e7-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="ad1e7-139">Autenticazione anonima (installata per impostazione predefinita insieme a IIS)</span><span class="sxs-lookup"><span data-stu-id="ad1e7-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="ad1e7-140">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="ad1e7-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="ad1e7-141">Nella tabella seguente vengono elencati gli URI delle directory virtuali per l'accesso interno e le risorse del file system a cui si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="ad1e7-142">Directory virtuali per l'accesso interno</span><span class="sxs-lookup"><span data-stu-id="ad1e7-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad1e7-143">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="ad1e7-143">Feature</span></span></th>
<th><span data-ttu-id="ad1e7-144">URI directory virtuale</span><span class="sxs-lookup"><span data-stu-id="ad1e7-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="ad1e7-145">Riferimento</span><span class="sxs-lookup"><span data-stu-id="ad1e7-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-146">Server della Rubrica</span><span class="sxs-lookup"><span data-stu-id="ad1e7-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-147">/ABS/int/Handler&lt;d'FQDN&gt;interno https://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-148">Percorso dei file di download del server della Rubrica per gli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1e7-149">Servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="ad1e7-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-150">/Autodiscover&lt;d'FQDN&gt;interno https://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-151">Percorso del servizio di individuazione automatica di Lync Server che individua le risorse mobili per gli utenti di dispositivi mobili interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-152">Aggiornamenti client</span><span class="sxs-lookup"><span data-stu-id="ad1e7-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-153">/AutoUpdate/int&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-154">Percorso dei file di aggiornamento per i client interni basati su computer.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1e7-155">Conf</span><span class="sxs-lookup"><span data-stu-id="ad1e7-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-156">/Conf/int&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-157">Percorso delle risorse per conferenze per utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-158">Aggiornamenti per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="ad1e7-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-159">FQDN&lt;&gt;interno/DeviceUpdateFiles_Int di http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-160">Percorso dei file di aggiornamento per i dispositivi interni per comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1e7-161">Riunione</span><span class="sxs-lookup"><span data-stu-id="ad1e7-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-162">/etc/place/null&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-163">Percorso del contenuto della riunione per utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-164">Servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ad1e7-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-165">/MCX&lt;d'FQDN&gt;interno https://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-166">Percorso delle risorse del servizio per dispositivi mobili per utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1e7-167">Servizio di espansione gruppo e query Web della Rubrica</span><span class="sxs-lookup"><span data-stu-id="ad1e7-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-168">/GroupExpansion/int/Service.asmx&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-169">Percorso del servizio Web che consente l'espansione gruppo per utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="ad1e7-170">Inoltre, la posizione del servizio di query Web della rubrica che fornisce informazioni sugli elenchi di indirizzi globali ai client mobili di Lync Mobile Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-171">Phone Conferencing</span><span class="sxs-lookup"><span data-stu-id="ad1e7-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-172">/PhoneConferencing/int&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-173">Percorso dei dati relativi alle conferenze telefoniche per utenti interni.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad1e7-174">Aggiornamenti per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="ad1e7-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-175">/RequestHandler&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-176">Percorso del gestore richieste del servizio Web di aggiornamento dispositivi che consente ai dispositivi per comunicazioni unificate interni di caricare registri e verificare la presenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad1e7-177">Applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="ad1e7-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-178">/RgsConfig&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="ad1e7-179">/RgsClients&lt;d'FQDN&gt;interno http://</span><span class="sxs-lookup"><span data-stu-id="ad1e7-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="ad1e7-180">Percorso dello strumento di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="ad1e7-181">Per i pool Front end in una configurazione consolidata, è necessario distribuire IIS prima di poter aggiungere server al pool.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="ad1e7-183">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="ad1e7-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ad1e7-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span><span class="sxs-lookup"><span data-stu-id="ad1e7-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

