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
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528153"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="6e3be-102">Configurazione di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e3be-102">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e3be-103">_**Ultimo argomento modificato:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="6e3be-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="6e3be-104">Per eseguire questa procedura, è necessario aver eseguito l'accesso al server almeno come amministratore locale e utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="6e3be-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="6e3be-105">Prima di configurare e installare il front end server per Lync Server 2013, Standard Edition o il primo front end server in un pool, è necessario installare e configurare il ruolo del server e i servizi Web per Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6e3be-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="6e3be-106">Se l'organizzazione richiede l'individuazione di IIS e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server 2013 nella finestra di dialogo Imposta quando si installano inizialmente gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e3be-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="6e3be-107">È possibile installare gli strumenti di amministrazione prima di installare IIS.</span><span class="sxs-lookup"><span data-stu-id="6e3be-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="6e3be-108">Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche il resto dei file di Lync Server 2013 verrà distribuito in questa unità.</span><span class="sxs-lookup"><span data-stu-id="6e3be-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="6e3be-109">Per Dtails, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e3be-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="6e3be-110">Per informazioni dettagliate su come spostare il INETPUB distribuito da Windows Server Manager durante l'installazione di IIS, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="6e3be-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="6e3be-111">Nella tabella seguente sono indicati i servizi di ruolo IIS 7,5 necessari.</span><span class="sxs-lookup"><span data-stu-id="6e3be-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="6e3be-112">Servizi ruolo di IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e3be-113">Intestazione ruolo</span><span class="sxs-lookup"><span data-stu-id="6e3be-113">Role Heading</span></span></th>
<th><span data-ttu-id="6e3be-114">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="6e3be-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-115">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="6e3be-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="6e3be-116">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="6e3be-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-117">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="6e3be-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="6e3be-118">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="6e3be-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-119">Funzionalità HTTP comuni installate</span><span class="sxs-lookup"><span data-stu-id="6e3be-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="6e3be-120">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-121">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6e3be-122">ASP.NET</span></span></p>
<p><span data-ttu-id="6e3be-123">Windows Server 2012 richiede anche ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="6e3be-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-124">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-125">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="6e3be-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-126">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-127">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="6e3be-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-128">Sviluppo applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-129">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="6e3be-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-130">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-131">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-132">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-133">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="6e3be-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-134">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-135">Analisi della</span><span class="sxs-lookup"><span data-stu-id="6e3be-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-136">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-137">Autenticazione anonima (installata e abilitata per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="6e3be-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-138">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-138">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-139">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="6e3be-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-140">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-140">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-141">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="6e3be-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-142">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-143">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="6e3be-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-144">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="6e3be-145">Compressione contenuto statico</span><span class="sxs-lookup"><span data-stu-id="6e3be-145">Static content compression</span></span></p>
<p><span data-ttu-id="6e3be-146">Compressione del contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="6e3be-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-147">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="6e3be-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6e3be-148">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="6e3be-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-149">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="6e3be-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6e3be-150">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="6e3be-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6e3be-151">Nel sistema operativo Windows Server 2008 R2 SP1 x64, è possibile utilizzare Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="6e3be-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="6e3be-152">È prima necessario importare il modulo ServerManager e quindi installare il ruolo e i servizi ruolo di IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="6e3be-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="6e3be-153">L'autenticazione anonima viene installata per impostazione predefinita con il ruolo del server IIS.</span><span class="sxs-lookup"><span data-stu-id="6e3be-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="6e3be-154">È possibile gestire l'autenticazione anonima dopo l'installazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="6e3be-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="6e3be-155">Per informazioni dettagliate, vedere la sezione relativa all'abilitazione dell'autenticazione anonima (IIS 7) all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="6e3be-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="6e3be-156">Nella tabella seguente sono indicati i servizi di ruolo IIS 8,0 e IIS 8,5 necessari per Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="6e3be-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="6e3be-157">Per Windows Server 2012 e Windows Server 2012 R2, il cmdlet Add-WindowsFeature è stato sostituito dal cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="6e3be-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="6e3be-158">Per informazioni dettagliate, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="6e3be-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="6e3be-159">Servizi ruolo IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e3be-160">Intestazione ruolo</span><span class="sxs-lookup"><span data-stu-id="6e3be-160">Role Heading</span></span></th>
<th><span data-ttu-id="6e3be-161">Servizio ruolo</span><span class="sxs-lookup"><span data-stu-id="6e3be-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-162">Web Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="6e3be-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="6e3be-163">Server Web</span><span class="sxs-lookup"><span data-stu-id="6e3be-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-164">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="6e3be-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-165">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="6e3be-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-166">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="6e3be-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-167">Esplorazione directory</span><span class="sxs-lookup"><span data-stu-id="6e3be-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-168">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="6e3be-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-169">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-170">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="6e3be-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-171">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="6e3be-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-172">Caratteristiche HTTP comuni</span><span class="sxs-lookup"><span data-stu-id="6e3be-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-173">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-174">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-175">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-176">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-177">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="6e3be-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-178">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-179">Monitor richieste</span><span class="sxs-lookup"><span data-stu-id="6e3be-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-180">Integrità e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6e3be-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6e3be-181">Analisi della</span><span class="sxs-lookup"><span data-stu-id="6e3be-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-182">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-182">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-183">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="6e3be-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-184">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-184">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-185">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="6e3be-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-186">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-186">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-187">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="6e3be-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-188">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e3be-188">Security</span></span></p></td>
<td><p><span data-ttu-id="6e3be-189">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="6e3be-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-190">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-191">Estensibilità .NET 3,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-192">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-193">Estensibilità .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-194">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-196">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-198">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-199">Estensioni ISAPI</span><span class="sxs-lookup"><span data-stu-id="6e3be-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-200">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-201">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="6e3be-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-202">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6e3be-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6e3be-203">Inclusioni sul lato server</span><span class="sxs-lookup"><span data-stu-id="6e3be-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-204">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="6e3be-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6e3be-205">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="6e3be-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-206">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="6e3be-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6e3be-207">Compatibilità della metabase di IIS 6</span><span class="sxs-lookup"><span data-stu-id="6e3be-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-208">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="6e3be-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6e3be-209">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="6e3be-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-210">Caratteristiche di .NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-212">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-214">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-216">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-217">Attivazione HTTP</span><span class="sxs-lookup"><span data-stu-id="6e3be-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-218">Caratteristiche di .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="6e3be-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="6e3be-219">Condivisione delle porte TCP</span><span class="sxs-lookup"><span data-stu-id="6e3be-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-220">Servizio di trasferimento intelligente in background</span><span class="sxs-lookup"><span data-stu-id="6e3be-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="6e3be-221">Estensioni del server IIS</span><span class="sxs-lookup"><span data-stu-id="6e3be-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-222">Servizi di riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="6e3be-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="6e3be-223">Servizi di riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="6e3be-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="6e3be-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="6e3be-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="6e3be-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-226">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="6e3be-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="6e3be-227">Strumenti e infrastruttura di gestione grafica</span><span class="sxs-lookup"><span data-stu-id="6e3be-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-228">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="6e3be-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="6e3be-229">Esperienza desktop</span><span class="sxs-lookup"><span data-stu-id="6e3be-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-230">Interfacce utente e infrastruttura</span><span class="sxs-lookup"><span data-stu-id="6e3be-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="6e3be-231">Shell grafica del server</span><span class="sxs-lookup"><span data-stu-id="6e3be-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="6e3be-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="6e3be-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e3be-234">Servizio di attivazione del processo di Windows</span><span class="sxs-lookup"><span data-stu-id="6e3be-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="6e3be-235">Modello di processo</span><span class="sxs-lookup"><span data-stu-id="6e3be-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e3be-236">Servizio di attivazione del processo di Windows</span><span class="sxs-lookup"><span data-stu-id="6e3be-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="6e3be-237">API di configurazione</span><span class="sxs-lookup"><span data-stu-id="6e3be-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6e3be-238">In Windows Server 2012 e Windows Server 2012 R2, è possibile utilizzare Windows PowerShell 3,0 per installare i requisiti di IIS.</span><span class="sxs-lookup"><span data-stu-id="6e3be-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="6e3be-239">Se si utilizza il modulo ServerManager in Windows PowerShell 3,0, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6e3be-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="6e3be-240">Nuovo con Windows Server 2012 è il parametro – source che definisce la posizione in cui è possibile trovare il file multimediale di origine di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="6e3be-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="6e3be-241">Il supporto può essere definito come un'unità DVD (ad esempio, D:\Sources\Sxs) o in una condivisione di rete che i file multimediali sono stati copiati (ad esempio, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="6e3be-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e3be-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e3be-242">See Also</span></span>


[<span data-ttu-id="6e3be-243">Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e3be-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

