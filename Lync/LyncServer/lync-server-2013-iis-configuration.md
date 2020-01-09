---
title: 'Lync Server 2013: Configurazione di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b9803fdb6c4a048fdf072b5ba2e5722b863640
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="1d48d-102">Configurazione di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d48d-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d48d-103">_**Argomento Ultima modifica:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="1d48d-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="1d48d-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server come amministratore locale e un utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="1d48d-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="1d48d-105">Prima di configurare e installare il front end server per Lync Server 2013, Standard Edition o il primo server front-end in un pool, è possibile installare e configurare il ruolo del server e i servizi Web per Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1d48d-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="1d48d-106">Se l'organizzazione richiede l'individuazione di IIS e tutti i servizi Web in un'unità diversa da quella dell'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server 2013 nella finestra di dialogo Imposta durante l'installazione iniziale di Lync Server 2013 Strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1d48d-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="1d48d-107">Gli strumenti di amministrazione vengono installati prima dell'installazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="1d48d-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="1d48d-108">Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito nell'unità.</span><span class="sxs-lookup"><span data-stu-id="1d48d-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="1d48d-109">Per Dtails, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1d48d-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="1d48d-110">Per informazioni dettagliate su come rilocare il INETPUB distribuito da Windows Server Manager durante l'installazione di <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>IIS, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d48d-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="1d48d-111">La tabella seguente indica i servizi ruolo di IIS 7,5 necessari.</span><span class="sxs-lookup"><span data-stu-id="1d48d-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="1d48d-112">Servizi ruolo di IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d48d-113">Titolo del ruolo</span><span class="sxs-lookup"><span data-stu-id="1d48d-113">Role Heading</span></span></th>
<th><span data-ttu-id="1d48d-114">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="1d48d-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-115">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="1d48d-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="1d48d-116">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="1d48d-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-117">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="1d48d-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="1d48d-118">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="1d48d-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-119">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="1d48d-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="1d48d-120">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-121">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1d48d-122">ASP.NET</span></span></p>
<p><span data-ttu-id="1d48d-123">Windows Server 2012 richiede anche ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="1d48d-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-124">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-125">Estensibilità .NET</span><span class="sxs-lookup"><span data-stu-id="1d48d-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-126">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-127">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="1d48d-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-128">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-129">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="1d48d-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-130">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-131">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-132">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-133">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="1d48d-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-134">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-135">Traccia</span><span class="sxs-lookup"><span data-stu-id="1d48d-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-136">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-137">Autenticazione anonima (installata e abilitata per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1d48d-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-138">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-138">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-139">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="1d48d-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-140">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-140">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-141">Autenticazione del mapping dei certificati client</span><span class="sxs-lookup"><span data-stu-id="1d48d-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-142">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-143">Filtro delle richieste</span><span class="sxs-lookup"><span data-stu-id="1d48d-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-144">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="1d48d-145">Compressione del contenuto statico</span><span class="sxs-lookup"><span data-stu-id="1d48d-145">Static content compression</span></span></p>
<p><span data-ttu-id="1d48d-146">Compressione del contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="1d48d-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-147">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="1d48d-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d48d-148">Console di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="1d48d-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-149">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="1d48d-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d48d-150">Script e strumenti di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="1d48d-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d48d-151">Nel sistema operativo Windows Server 2008 R2 SP1 x64 è possibile usare Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="1d48d-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="1d48d-152">È prima di tutto necessario importare il modulo ServerManager e quindi installare il ruolo e i servizi ruolo di IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="1d48d-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="1d48d-153">Per impostazione predefinita, l'autenticazione anonima viene installata con il ruolo del server IIS.</span><span class="sxs-lookup"><span data-stu-id="1d48d-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="1d48d-154">È possibile gestire l'autenticazione anonima dopo l'installazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="1d48d-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="1d48d-155">Per informazioni dettagliate, vedere "abilitare l'autenticazione anonima (IIS 7 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1d48d-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="1d48d-156">La tabella seguente indica i servizi ruolo di IIS 8,0 e IIS 8,5 necessari per Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="1d48d-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="1d48d-157">Per Windows Server 2012 e Windows Server 2012 R2, il cmdlet Add-WindowsFeature è stato sostituito dal cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="1d48d-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="1d48d-158">Per informazioni dettagliate, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="1d48d-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="1d48d-159">Servizi ruolo di IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d48d-160">Titolo del ruolo</span><span class="sxs-lookup"><span data-stu-id="1d48d-160">Role Heading</span></span></th>
<th><span data-ttu-id="1d48d-161">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="1d48d-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-162">Server Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="1d48d-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="1d48d-163">Server Web</span><span class="sxs-lookup"><span data-stu-id="1d48d-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-164">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="1d48d-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-165">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="1d48d-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-166">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="1d48d-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-167">Esplorazione della directory</span><span class="sxs-lookup"><span data-stu-id="1d48d-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-168">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="1d48d-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-169">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-170">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="1d48d-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-171">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="1d48d-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-172">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="1d48d-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-173">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-174">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-175">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-176">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-177">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="1d48d-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-178">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-179">Richiedi monitor</span><span class="sxs-lookup"><span data-stu-id="1d48d-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-180">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1d48d-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d48d-181">Traccia</span><span class="sxs-lookup"><span data-stu-id="1d48d-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-182">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-182">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-183">Filtro delle richieste</span><span class="sxs-lookup"><span data-stu-id="1d48d-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-184">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-184">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-185">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="1d48d-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-186">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-186">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-187">Autenticazione del mapping dei certificati client</span><span class="sxs-lookup"><span data-stu-id="1d48d-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-188">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d48d-188">Security</span></span></p></td>
<td><p><span data-ttu-id="1d48d-189">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="1d48d-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-190">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-191">Estensibilità .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-192">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-193">Estensibilità .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-194">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-196">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-198">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-199">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="1d48d-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-200">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-201">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="1d48d-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-202">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d48d-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d48d-203">Lato server include</span><span class="sxs-lookup"><span data-stu-id="1d48d-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-204">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="1d48d-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d48d-205">Console di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="1d48d-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-206">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="1d48d-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d48d-207">Compatibilità della metabase di IIS 6</span><span class="sxs-lookup"><span data-stu-id="1d48d-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-208">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="1d48d-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d48d-209">Script e strumenti di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="1d48d-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-210">Caratteristiche di .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-212">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-214">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-216">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-217">Attivazione HTTP</span><span class="sxs-lookup"><span data-stu-id="1d48d-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-218">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1d48d-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="1d48d-219">Condivisione della porta TCP</span><span class="sxs-lookup"><span data-stu-id="1d48d-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-220">Servizio trasferimento intelligente in background</span><span class="sxs-lookup"><span data-stu-id="1d48d-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="1d48d-221">Estensioni del server IIS</span><span class="sxs-lookup"><span data-stu-id="1d48d-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-222">Servizi a penna e grafia</span><span class="sxs-lookup"><span data-stu-id="1d48d-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="1d48d-223">Servizi a penna e grafia</span><span class="sxs-lookup"><span data-stu-id="1d48d-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="1d48d-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="1d48d-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="1d48d-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-226">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="1d48d-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="1d48d-227">Strumenti e infrastrutture di gestione grafica</span><span class="sxs-lookup"><span data-stu-id="1d48d-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-228">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="1d48d-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="1d48d-229">Esperienza desktop</span><span class="sxs-lookup"><span data-stu-id="1d48d-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-230">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="1d48d-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="1d48d-231">Shell grafica del server</span><span class="sxs-lookup"><span data-stu-id="1d48d-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="1d48d-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="1d48d-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d48d-234">Servizio di attivazione processo Windows</span><span class="sxs-lookup"><span data-stu-id="1d48d-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="1d48d-235">Modello di processo</span><span class="sxs-lookup"><span data-stu-id="1d48d-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d48d-236">Servizio di attivazione processo Windows</span><span class="sxs-lookup"><span data-stu-id="1d48d-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="1d48d-237">API di configurazione</span><span class="sxs-lookup"><span data-stu-id="1d48d-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d48d-238">In Windows Server 2012 e Windows Server 2012 R2 è possibile usare Windows PowerShell 3,0 per installare i requisiti di IIS.</span><span class="sxs-lookup"><span data-stu-id="1d48d-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="1d48d-239">Usando il modulo ServerManager in Windows PowerShell 3,0, digitare:</span><span class="sxs-lookup"><span data-stu-id="1d48d-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="1d48d-240">Nuovo con Windows Server 2012 è il parametro – source che definisce la posizione in cui è possibile trovare il file multimediale di origine di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="1d48d-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="1d48d-241">Il contenuto multimediale può essere definito come unità DVD (ad esempio, D:\Sources\Sxs) o in una condivisione di rete che i file multimediali sono stati copiati (ad esempio \\, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="1d48d-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d48d-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d48d-242">See Also</span></span>


[<span data-ttu-id="1d48d-243">Requisiti di IIS per pool Front End e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d48d-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

