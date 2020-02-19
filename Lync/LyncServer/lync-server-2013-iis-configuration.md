---
title: 'Lync Server 2013: configurazione di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d284fa2082c886a583baf116893f792535a096b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="c03f9-102">Configurazione di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c03f9-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c03f9-103">_**Ultimo argomento modificato:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="c03f9-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="c03f9-104">Per eseguire questa procedura, è necessario aver eseguito l'accesso al server almeno come amministratore locale e utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="c03f9-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="c03f9-105">Prima di configurare e installare il front end server per Lync Server 2013, Standard Edition o il primo front end server in un pool, è necessario installare e configurare il ruolo del server e i servizi Web per Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c03f9-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c03f9-106">Se l'organizzazione richiede l'individuazione di IIS e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server 2013 nella finestra di dialogo Imposta quando si installa inizialmente Lync Server 2013. Strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c03f9-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="c03f9-107">È possibile installare gli strumenti di amministrazione prima di installare IIS.</span><span class="sxs-lookup"><span data-stu-id="c03f9-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="c03f9-108">Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server 2013 verranno distribuiti nell'unità.</span><span class="sxs-lookup"><span data-stu-id="c03f9-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="c03f9-109">Per Dtails, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c03f9-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="c03f9-110">Per informazioni dettagliate su come spostare il INETPUB distribuito da Windows Server Manager durante l'installazione di IIS, <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>vedere.</span><span class="sxs-lookup"><span data-stu-id="c03f9-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="c03f9-111">Nella tabella seguente sono indicati i servizi di ruolo IIS 7,5 necessari.</span><span class="sxs-lookup"><span data-stu-id="c03f9-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="c03f9-112">Servizi ruolo di IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c03f9-113">Intestazione ruolo</span><span class="sxs-lookup"><span data-stu-id="c03f9-113">Role Heading</span></span></th>
<th><span data-ttu-id="c03f9-114">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="c03f9-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-115">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="c03f9-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="c03f9-116">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="c03f9-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-117">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="c03f9-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="c03f9-118">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="c03f9-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-119">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="c03f9-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="c03f9-120">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-121">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c03f9-122">ASP.NET</span></span></p>
<p><span data-ttu-id="c03f9-123">Windows Server 2012 richiede anche ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="c03f9-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-124">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-125">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="c03f9-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-126">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-127">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="c03f9-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-128">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-129">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="c03f9-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-130">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-131">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-132">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-133">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="c03f9-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-134">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-135">Analisi della</span><span class="sxs-lookup"><span data-stu-id="c03f9-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-136">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-137">Autenticazione anonima (installata e abilitata per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c03f9-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-138">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-138">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-139">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="c03f9-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-140">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-140">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-141">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="c03f9-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-142">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-143">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="c03f9-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-144">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="c03f9-145">Compressione contenuto statico</span><span class="sxs-lookup"><span data-stu-id="c03f9-145">Static content compression</span></span></p>
<p><span data-ttu-id="c03f9-146">Compressione del contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="c03f9-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-147">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="c03f9-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c03f9-148">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="c03f9-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-149">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="c03f9-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c03f9-150">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="c03f9-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c03f9-151">Nel sistema operativo Windows Server 2008 R2 SP1 x64, è possibile utilizzare Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="c03f9-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="c03f9-152">È prima necessario importare il modulo ServerManager e quindi installare il ruolo e i servizi ruolo di IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="c03f9-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c03f9-153">L'autenticazione anonima viene installata per impostazione predefinita con il ruolo del server IIS.</span><span class="sxs-lookup"><span data-stu-id="c03f9-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="c03f9-154">È possibile gestire l'autenticazione anonima dopo l'installazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="c03f9-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="c03f9-155">Per informazioni dettagliate, vedere la sezione relativa all'abilitazione dell'autenticazione anonima (IIS 7) all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span><span class="sxs-lookup"><span data-stu-id="c03f9-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="c03f9-156">Nella tabella seguente sono indicati i servizi di ruolo IIS 8,0 e IIS 8,5 necessari per Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c03f9-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c03f9-157">Per Windows Server 2012 e Windows Server 2012 R2, il cmdlet Add-WindowsFeature è stato sostituito dal cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="c03f9-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="c03f9-158">Per informazioni dettagliate, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="c03f9-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="c03f9-159">Servizi ruolo IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c03f9-160">Intestazione ruolo</span><span class="sxs-lookup"><span data-stu-id="c03f9-160">Role Heading</span></span></th>
<th><span data-ttu-id="c03f9-161">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="c03f9-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-162">Web Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="c03f9-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="c03f9-163">Server Web</span><span class="sxs-lookup"><span data-stu-id="c03f9-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-164">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="c03f9-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-165">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="c03f9-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-166">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="c03f9-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-167">Esplorazione directory</span><span class="sxs-lookup"><span data-stu-id="c03f9-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-168">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="c03f9-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-169">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-170">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="c03f9-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-171">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="c03f9-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-172">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="c03f9-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-173">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-174">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-175">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-176">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-177">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="c03f9-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-178">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-179">Monitor richieste</span><span class="sxs-lookup"><span data-stu-id="c03f9-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-180">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c03f9-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c03f9-181">Analisi della</span><span class="sxs-lookup"><span data-stu-id="c03f9-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-182">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-182">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-183">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="c03f9-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-184">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-184">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-185">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="c03f9-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-186">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-186">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-187">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="c03f9-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-188">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03f9-188">Security</span></span></p></td>
<td><p><span data-ttu-id="c03f9-189">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="c03f9-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-190">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-191">Estensibilità .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-192">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-193">Estensibilità .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-194">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-196">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-198">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-199">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="c03f9-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-200">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-201">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="c03f9-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-202">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c03f9-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c03f9-203">Inclusioni sul lato server</span><span class="sxs-lookup"><span data-stu-id="c03f9-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-204">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="c03f9-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c03f9-205">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="c03f9-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-206">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="c03f9-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c03f9-207">Compatibilità della metabase di IIS 6</span><span class="sxs-lookup"><span data-stu-id="c03f9-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-208">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="c03f9-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c03f9-209">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="c03f9-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-210">Caratteristiche di .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-212">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-214">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-216">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-217">Attivazione HTTP</span><span class="sxs-lookup"><span data-stu-id="c03f9-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-218">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="c03f9-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="c03f9-219">Condivisione delle porte TCP</span><span class="sxs-lookup"><span data-stu-id="c03f9-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-220">Servizio di trasferimento intelligente in background</span><span class="sxs-lookup"><span data-stu-id="c03f9-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="c03f9-221">Estensioni del server IIS</span><span class="sxs-lookup"><span data-stu-id="c03f9-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-222">Servizi di riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="c03f9-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="c03f9-223">Servizi di riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="c03f9-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="c03f9-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="c03f9-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="c03f9-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-226">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c03f9-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="c03f9-227">Strumenti e infrastruttura di gestione grafica</span><span class="sxs-lookup"><span data-stu-id="c03f9-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-228">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c03f9-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="c03f9-229">Esperienza desktop</span><span class="sxs-lookup"><span data-stu-id="c03f9-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-230">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c03f9-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="c03f9-231">Shell grafica del server</span><span class="sxs-lookup"><span data-stu-id="c03f9-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="c03f9-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="c03f9-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f9-234">Servizio di attivazione del processo di Windows</span><span class="sxs-lookup"><span data-stu-id="c03f9-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="c03f9-235">Modello di processo</span><span class="sxs-lookup"><span data-stu-id="c03f9-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f9-236">Servizio di attivazione del processo di Windows</span><span class="sxs-lookup"><span data-stu-id="c03f9-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="c03f9-237">API di configurazione</span><span class="sxs-lookup"><span data-stu-id="c03f9-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c03f9-238">In Windows Server 2012 e Windows Server 2012 R2, è possibile utilizzare Windows PowerShell 3,0 per installare i requisiti di IIS.</span><span class="sxs-lookup"><span data-stu-id="c03f9-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="c03f9-239">Se si utilizza il modulo ServerManager in Windows PowerShell 3,0, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c03f9-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c03f9-240">Nuovo con Windows Server 2012 è il parametro – source che definisce la posizione in cui è possibile trovare il file multimediale di origine di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="c03f9-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="c03f9-241">Il supporto può essere definito come un'unità DVD (ad esempio, D:\Sources\Sxs) o in una condivisione di rete che i file multimediali sono stati copiati (ad esempio \\, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="c03f9-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c03f9-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c03f9-242">See Also</span></span>


[<span data-ttu-id="c03f9-243">Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c03f9-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

