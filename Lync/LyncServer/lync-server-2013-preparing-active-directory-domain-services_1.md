---
title: 'Lync Server 2013: preparazione di servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03436a59fa9fbab99608e4fa3b979e4802115ed1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="d6908-102">Preparazione di servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6908-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6908-103">_**Ultimo argomento modificato:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="d6908-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="d6908-104">In Lync Server 2013, è possibile utilizzare la distribuzione guidata di Lync Server per preparare i servizi di dominio Active Directory oppure è possibile utilizzare i cmdlet di Lync Server Management Shell direttamente.</span><span class="sxs-lookup"><span data-stu-id="d6908-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="d6908-105">È inoltre possibile utilizzare lo strumento da riga di comando ldifde.exe nei controller di dominio, come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d6908-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="d6908-106">La distribuzione guidata di Lync Server Guida l'utente attraverso ogni attività di preparazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d6908-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="d6908-107">La distribuzione guidata esegue i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d6908-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="d6908-108">Questo strumento è utile per gli ambienti con una topologia a singolo dominio e a singola foresta o con un'altra topologia simile.</span><span class="sxs-lookup"><span data-stu-id="d6908-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6908-109">È possibile distribuire Lync Server in una foresta o un dominio in cui i controller di dominio eseguono versioni a 32 bit di alcuni sistemi operativi (per informazioni dettagliate, vedere <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure requirements for Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="d6908-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="d6908-110">Tuttavia, non è possibile utilizzare la distribuzione guidata di Lync Server per eseguire la preparazione dello schema, della foresta e del dominio in questi ambienti perché la distribuzione guidata e i file di supporto sono solo di 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d6908-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="d6908-111">È tuttavia possibile utilizzare ldifde.exe e i file con estensione ldf associati in un controller di dominio a 32 bit per preparare lo schema, la foresta e il dominio.</span><span class="sxs-lookup"><span data-stu-id="d6908-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="d6908-112">Vedere la sezione "Utilizzo dei cmdlet e di Ldifde.exe" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d6908-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="d6908-113">È possibile utilizzare i cmdlet di Lync Server Management Shell per eseguire le attività in modalità remota o per ambienti più complessi.</span><span class="sxs-lookup"><span data-stu-id="d6908-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="d6908-114">Prerequisiti di preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="d6908-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="d6908-115">È necessario eseguire i passaggi di preparazione di Active Directory in un computer che esegue Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bit).</span><span class="sxs-lookup"><span data-stu-id="d6908-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="d6908-116">La preparazione di Active Directory richiede Lync Server Management Shell e OCSCore.</span><span class="sxs-lookup"><span data-stu-id="d6908-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="d6908-117">Per eseguire le attività di preparazione di Active Directory sono necessari i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6908-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="d6908-118">Componenti di base di Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="d6908-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6908-119">Se si prevede di utilizzare Lync Server Management Shell per la preparazione di Active Directory, è necessario eseguire prima la distribuzione guidata di Lync Server per installare i componenti di base.</span><span class="sxs-lookup"><span data-stu-id="d6908-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="d6908-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d6908-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6908-121">Per Windows Server 2012 e Windows Server 2012 R2, è necessario installare e attivare .NET Framework 4,5 tramite Server Manager.</span><span class="sxs-lookup"><span data-stu-id="d6908-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="d6908-122">Per informazioni dettagliate, vedere "Microsoft .NET Framework 4,5" in <A href="lync-server-2013-additional-software-requirements.md">Additional Software Requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d6908-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="d6908-123">Per Windows Server&nbsp;2008&nbsp;R2, scaricare e installare <A href="http://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> dal sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6908-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="d6908-124">Strumenti di amministrazione remota del server</span><span class="sxs-lookup"><span data-stu-id="d6908-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6908-125">Se si eseguono le attività di preparazione di Active Directory in un server membro anziché in un controller di dominio, sono necessari alcuni strumenti inclusi in Strumenti di amministrazione remota del server.</span><span class="sxs-lookup"><span data-stu-id="d6908-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="d6908-126">Installare gli snap-in di AD DS e gli strumenti da riga di comando e il modulo di Active Directory per Windows PowerShell dal nodo AD DS e AD LDS Tools in Server Manager.</span><span class="sxs-lookup"><span data-stu-id="d6908-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="d6908-127">Microsoft Visual C++ 11 Redistributable</span><span class="sxs-lookup"><span data-stu-id="d6908-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6908-p107">Se il componente non è già presente nel computer, nel corso dell'installazione viene richiesto di installare questo prerequisito. Il pacchetto è fornito in dotazione e non è necessario acquistarlo separatamente.</span><span class="sxs-lookup"><span data-stu-id="d6908-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="d6908-130">Windows PowerShell 3,0 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="d6908-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="d6908-131">Per Windows Server 2012 e Windows Server 2012 R2, Windows PowerShell 3,0 deve essere incluso nell'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6908-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="d6908-132">Per Windows Server 2008 R2, è necessario installare o eseguire l'aggiornamento a Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d6908-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="d6908-133">Per informazioni dettagliate, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="d6908-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="d6908-134">Diritti e ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="d6908-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="d6908-135">Nella tabella seguente vengono indicati i diritti e i ruoli amministrativi necessari per ogni attività di preparazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d6908-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="d6908-136">Diritti utente necessari per la preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="d6908-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6908-137">Procedura</span><span class="sxs-lookup"><span data-stu-id="d6908-137">Procedure</span></span></th>
<th><span data-ttu-id="d6908-138">Diritti o ruoli</span><span class="sxs-lookup"><span data-stu-id="d6908-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6908-139">Preparazione dello schema</span><span class="sxs-lookup"><span data-stu-id="d6908-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="d6908-140">Membro del gruppo Schema Admins per il dominio radice della foresta e diritti di amministratore per il master schema</span><span class="sxs-lookup"><span data-stu-id="d6908-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6908-141">Preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="d6908-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="d6908-142">Membro del gruppo Enterprise Admins della foresta</span><span class="sxs-lookup"><span data-stu-id="d6908-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6908-143">Preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="d6908-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="d6908-144">Membro del gruppo Enterprise Admins o Domain Admins per il dominio specificato</span><span class="sxs-lookup"><span data-stu-id="d6908-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="d6908-145">Cmdlet per la preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="d6908-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="d6908-146">Nella tabella seguente vengono confrontati i cmdlet di Lync Server Management Shell utilizzati per preparare Servizi di dominio Active Directory ai comandi LcsCmd utilizzati per preparare Servizi di dominio Active Directory in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d6908-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="d6908-147">Confronto tra cmdlet e LcsCmd</span><span class="sxs-lookup"><span data-stu-id="d6908-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6908-148">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6908-148">Cmdlets</span></span></th>
<th><span data-ttu-id="d6908-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="d6908-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6908-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d6908-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d6908-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="d6908-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6908-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d6908-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d6908-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="d6908-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6908-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d6908-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d6908-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="d6908-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6908-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d6908-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d6908-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="d6908-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6908-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d6908-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d6908-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="d6908-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6908-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d6908-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d6908-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="d6908-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6908-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d6908-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d6908-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="d6908-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6908-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d6908-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d6908-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="d6908-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="d6908-166">Requisiti per un ambiente Active Directory bloccato</span><span class="sxs-lookup"><span data-stu-id="d6908-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="d6908-167">Se l'ereditarietà delle autorizzazioni è disabilitata o è necessario disabilitare le autorizzazioni degli utenti autenticati nell'organizzazione, durante la preparazione del dominio sono necessari alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d6908-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="d6908-168">Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6908-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="d6908-169">Autorizzazioni per contenitori personalizzati</span><span class="sxs-lookup"><span data-stu-id="d6908-169">Custom Container Permissions</span></span>

<span data-ttu-id="d6908-170">Se nell'organizzazione vengono utilizzati contenitori personalizzati anziché tre contenitori incorporati (ovvero utenti, computer e controller di dominio), è necessario concedere l'accesso in lettura ai contenitori personalizzati per il gruppo Authenticated Users.</span><span class="sxs-lookup"><span data-stu-id="d6908-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="d6908-171">L'accesso in lettura ai contenitori è necessario per la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="d6908-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="d6908-172">Per ulteriori informazioni, vedere [preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="d6908-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="d6908-173">Utilizzo dei cmdlet e di Ldifde.exe</span><span class="sxs-lookup"><span data-stu-id="d6908-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="d6908-174">Il passaggio di **preparazione dello schema** nella distribuzione guidata di Lync Server e il cmdlet **Install-CsAdServerSchema** estendono lo schema di Active Directory sui controller di dominio che eseguono un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d6908-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="d6908-175">Se è necessario estendere lo schema di Active Directory in un controller di dominio che esegue un sistema operativo a 32 bit, è possibile utilizzare il cmdlet **Install-CsAdServerSchema** in remoto da un server membro (procedura consigliata).</span><span class="sxs-lookup"><span data-stu-id="d6908-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="d6908-176">Se è necessario eseguire la preparazione dello schema direttamente nel controller di dominio, è tuttavia possibile utilizzare lo strumento Ldifde.exe per importare i file di schema.</span><span class="sxs-lookup"><span data-stu-id="d6908-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="d6908-177">Lo strumento Ldifde.exe è incluso nella maggior parte delle versioni del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="d6908-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="d6908-p112">Se si utilizza o strumento Ldifde.exe per importare i file di schema è necessario importare tutti e quattro i file, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente oppure un'installazione pulita. I file vanno importati nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="d6908-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="d6908-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d6908-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="d6908-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d6908-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="d6908-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d6908-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="d6908-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d6908-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6908-184">I quattro file con estensione ldf si trovano nella directory \Support\Schema del supporto di installazione o del download.</span><span class="sxs-lookup"><span data-stu-id="d6908-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="d6908-185">Per utilizzare Ldifde.exe per importare i quattro file di schema in un controller di dominio che funge da master schema, utilizzare il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d6908-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="d6908-186">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d6908-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="d6908-p113">Utilizzare il parametro b solo se si è effettuato l'accesso come un altro utente. Per informazioni dettagliate sui diritti utente necessari, vedere la sezione "Diritti e ruoli amministrativi" in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d6908-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="d6908-189">Per utilizzare Ldifde.exe per importare i quattro file di schema in un controller di dominio che non funge da master schema, utilizzare il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d6908-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="d6908-190">Per informazioni dettagliate sull'utilizzo di LDIFDE, vedere l'articolo 237677 della Microsoft Knowledge Base "using LDIFDE to Import and Export Directory Objects to Active [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)directory".</span><span class="sxs-lookup"><span data-stu-id="d6908-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6908-191">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d6908-191">In This Section</span></span>

  - [<span data-ttu-id="d6908-192">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6908-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="d6908-193">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6908-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="d6908-194">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6908-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

