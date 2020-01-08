---
title: 'Lync Server 2013: Requisiti software aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="2886e-102">Requisiti software aggiuntivi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2886e-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2886e-103">_**Argomento Ultima modifica:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2886e-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="2886e-104">Oltre ai requisiti relativi a hardware e sistemi operativi per le piattaforme server, Lync Server 2013 richiede l'installazione di software aggiuntivo nei server distribuiti.</span><span class="sxs-lookup"><span data-stu-id="2886e-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2886e-105">Per informazioni dettagliate sui requisiti della piattaforma per i server che utilizzano Lync Server, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A> e supporto per il <A href="lync-server-2013-server-and-tools-operating-system-support.md">sistema operativo per server e strumenti in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2886e-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="2886e-106">Per informazioni dettagliate sui requisiti di sistema per i computer e i dispositivi client, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">pianificazione di client e dispositivi in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2886e-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="2886e-107">Per informazioni dettagliate sui requisiti software per gli strumenti di amministrazione, vedere <A href="lync-server-2013-administrative-tools-software-requirements.md">requisiti software per strumenti di amministrazione in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2886e-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="2886e-108">Software aggiuntivo necessario per tutti i ruoli server interni</span><span class="sxs-lookup"><span data-stu-id="2886e-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="2886e-109">Questa sezione elenca il software necessario per tutti i ruoli server interni, che sono tutti i ruoli di Lync Server server eccetto Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2886e-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="2886e-110">I requisiti per gli Edge Server e i pool di Edge sono elencati più avanti in questo argomento in **software aggiuntivo per Edge Server**.</span><span class="sxs-lookup"><span data-stu-id="2886e-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="2886e-111">Windows PowerShell 3,0</span><span class="sxs-lookup"><span data-stu-id="2886e-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="2886e-112">Ogni server in cui è in uso Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2886e-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="2886e-113">Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="2886e-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="2886e-114">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="2886e-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="2886e-115">Lync Server richiede Microsoft .NET Framework 4,5 in tutti i ruoli server interni e in qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server o Microsoft Lync Server 2013, strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2886e-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="2886e-116">Per Lync Server 2013 è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2886e-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="2886e-117">Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="2886e-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="2886e-118">Installazione di Microsoft .NET Framework 4,5 su server che esegue Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2886e-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="2886e-119">Quando si installa Microsoft .NET Framework 4,5 su server che eseguono Lync Server 2013 e Windows Server 2012, è necessario eseguire un ulteriore passaggio.</span><span class="sxs-lookup"><span data-stu-id="2886e-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="2886e-120">Dopo l'installazione di .NET Framework 4,5, usare Server Manager per installare l'attivazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="2886e-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="2886e-121">**Per installare l'attivazione HTTP di .NET 4,5 in Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="2886e-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="2886e-122">Nel menu **Start** fare clic su **programmi**, quindi su **strumenti di amministrazione**e quindi su **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="2886e-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="2886e-123">In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2886e-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="2886e-124">Espandere **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="2886e-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="2886e-125">Selezionare l' **attivazione di WCF** se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="2886e-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="2886e-126">Quindi seleziona **attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="2886e-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="2886e-127">Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2886e-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="2886e-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="2886e-128">Windows Identity Foundation</span></span>

<span data-ttu-id="2886e-129">**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione server-server.</span><span class="sxs-lookup"><span data-stu-id="2886e-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="2886e-130">Windows Server 2008 R2 e Windows Server 2012 richiedono diverse procedure per installare Windows identifica Foundation.</span><span class="sxs-lookup"><span data-stu-id="2886e-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="2886e-131">Selezionare il sistema operativo del server dall'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="2886e-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="2886e-132">Windows Server 2008 R2 per Windows Server 2008 R2, verificare se è già stato installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="2886e-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="2886e-133">Per eseguire questa operazione, vedere **aggiungere/rimuovere programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="2886e-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="2886e-134">Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.</span><span class="sxs-lookup"><span data-stu-id="2886e-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="2886e-135">Windows Server 2012 per Windows Server 2012, è possibile usare **Server Manager** per installare Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="2886e-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="2886e-136">Nella **procedura guidata per l'aggiunta di ruoli e funzionalità**in Server Manager selezionare **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2886e-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="2886e-137">Selezionare **Windows Identity Foundation 3,5** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2886e-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="2886e-138">Fare clic su **Avanti**e quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="2886e-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="2886e-139">Software aggiuntivo per tutti i server front-end e i server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2886e-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="2886e-140">Tutti i server front-end e i server Standard Edition devono eseguire anche Internet Information Services (IIS) con determinati moduli.</span><span class="sxs-lookup"><span data-stu-id="2886e-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="2886e-141">Inoltre, tutti i server front-end e i server Standard Edition in cui sono distribuiti i servizi di conferenza, l'applicazione di Call Park, l'annuncio o i gruppi di risposta devono eseguire Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="2886e-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="2886e-142">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="2886e-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="2886e-143">I server front-end e i server Standard Edition devono eseguire Internet Information Services (IIS), con i moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2886e-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="2886e-144">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="2886e-144">Static Content</span></span>

  - <span data-ttu-id="2886e-145">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="2886e-145">Default Document</span></span>

  - <span data-ttu-id="2886e-146">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="2886e-146">HTTP Errors</span></span>

  - <span data-ttu-id="2886e-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2886e-147">ASP.NET</span></span>

  - <span data-ttu-id="2886e-148">Estensibilità .NET</span><span class="sxs-lookup"><span data-stu-id="2886e-148">.NET Extensibility</span></span>

  - <span data-ttu-id="2886e-149">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="2886e-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="2886e-150">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="2886e-150">ISAPI Filters</span></span>

  - <span data-ttu-id="2886e-151">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="2886e-151">HTTP Logging</span></span>

  - <span data-ttu-id="2886e-152">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="2886e-152">Logging Tools</span></span>

  - <span data-ttu-id="2886e-153">Traccia</span><span class="sxs-lookup"><span data-stu-id="2886e-153">Tracing</span></span>

  - <span data-ttu-id="2886e-154">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="2886e-154">Windows Authentication</span></span>

  - <span data-ttu-id="2886e-155">Filtro delle richieste</span><span class="sxs-lookup"><span data-stu-id="2886e-155">Request Filtering</span></span>

  - <span data-ttu-id="2886e-156">Compressione del contenuto statico</span><span class="sxs-lookup"><span data-stu-id="2886e-156">Static Content Compression</span></span>

  - <span data-ttu-id="2886e-157">Compressione del contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="2886e-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="2886e-158">Console di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="2886e-158">IIS Management Console</span></span>

  - <span data-ttu-id="2886e-159">Script e strumenti di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="2886e-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="2886e-160">Autenticazione anonima (questa operazione viene installata per impostazione predefinita quando IIS è installato).</span><span class="sxs-lookup"><span data-stu-id="2886e-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="2886e-161">Autenticazione del mapping dei certificati client</span><span class="sxs-lookup"><span data-stu-id="2886e-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="2886e-162">Windows Media Format Runtime e Windows Desktop Experience</span><span class="sxs-lookup"><span data-stu-id="2886e-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="2886e-163">**Esperienza desktop di Windows** Tutti i server front-end e i server Standard Edition in cui verranno distribuiti i servizi di conferenza devono avere installato Windows Media Format Runtime, che, ad eccezione di Windows Server 2012, è installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="2886e-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="2886e-164">Windows Server 2012 richiede Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="2886e-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="2886e-165">Windows Media Format Runtime è necessario per eseguire i file di Windows Media Audio (con estensione WMA) che vengono riprodotti dalle applicazioni Park, annuncio e Response Group per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="2886e-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="2886e-166">È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2886e-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="2886e-167">Se Lync Server 2013 non trova il software sul server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2886e-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="2886e-168">Software aggiuntivo per i server front-end e i server Standard Edition in Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2886e-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="2886e-169">I server front-end richiedono .NET 3,5, che non è installato per impostazione predefinita in Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="2886e-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="2886e-170">Per installarlo, inserire il supporto di installazione di Windows Server 2012 nell'unità D e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2886e-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="2886e-171">Per informazioni dettagliate sull'installazione di .NET 3,5 nei server che esegue Windows Server 2012, vedere "Considerazioni sulla distribuzione di Microsoft <https://go.microsoft.com/fwlink/p/?linkid=275032>.net Framework 3,5".</span><span class="sxs-lookup"><span data-stu-id="2886e-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="2886e-172">Software aggiuntivo per amministratori</span><span class="sxs-lookup"><span data-stu-id="2886e-172">Additional Software for Directors</span></span>

<span data-ttu-id="2886e-173">Gli amministratori devono eseguire Internet Information Services (IIS) con i moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2886e-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="2886e-174">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="2886e-174">Static Content</span></span>

  - <span data-ttu-id="2886e-175">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="2886e-175">Default Document</span></span>

  - <span data-ttu-id="2886e-176">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="2886e-176">HTTP Errors</span></span>

  - <span data-ttu-id="2886e-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2886e-177">ASP.NET</span></span>

  - <span data-ttu-id="2886e-178">Estensibilità .NET</span><span class="sxs-lookup"><span data-stu-id="2886e-178">.NET Extensibility</span></span>

  - <span data-ttu-id="2886e-179">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="2886e-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="2886e-180">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="2886e-180">ISAPI Filters</span></span>

  - <span data-ttu-id="2886e-181">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="2886e-181">HTTP Logging</span></span>

  - <span data-ttu-id="2886e-182">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="2886e-182">Logging Tools</span></span>

  - <span data-ttu-id="2886e-183">Traccia</span><span class="sxs-lookup"><span data-stu-id="2886e-183">Tracing</span></span>

  - <span data-ttu-id="2886e-184">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="2886e-184">Windows Authentication</span></span>

  - <span data-ttu-id="2886e-185">Filtro delle richieste</span><span class="sxs-lookup"><span data-stu-id="2886e-185">Request Filtering</span></span>

  - <span data-ttu-id="2886e-186">Compressione del contenuto statico</span><span class="sxs-lookup"><span data-stu-id="2886e-186">Static Content Compression</span></span>

  - <span data-ttu-id="2886e-187">Console di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="2886e-187">IIS Management Console</span></span>

  - <span data-ttu-id="2886e-188">Script e strumenti di gestione di IIS</span><span class="sxs-lookup"><span data-stu-id="2886e-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="2886e-189">Autenticazione anonima (questa operazione viene installata per impostazione predefinita quando IIS è installato).</span><span class="sxs-lookup"><span data-stu-id="2886e-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="2886e-190">Autenticazione del mapping dei certificati client</span><span class="sxs-lookup"><span data-stu-id="2886e-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="2886e-191">Software aggiuntivo per i server front end della chat persistente</span><span class="sxs-lookup"><span data-stu-id="2886e-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="2886e-192">I server front-end della chat persistente devono eseguire Accodamento messaggi (noto anche come MSMQ), che è un componente di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2886e-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="2886e-193">Per informazioni sull'abilitazione di MSMQ, [fare clic qui.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="2886e-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="2886e-194">Software aggiuntivo per Edge Server</span><span class="sxs-lookup"><span data-stu-id="2886e-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="2886e-195">I server perimetrali richiedono il software seguente:</span><span class="sxs-lookup"><span data-stu-id="2886e-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="2886e-196">Ogni server in cui è in uso Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2886e-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="2886e-197">Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="2886e-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="2886e-198">Lync Server richiede Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="2886e-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="2886e-199">Per Lync Server 2013 installato in Windows Server 2008 R2, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2886e-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="2886e-200">Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="2886e-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="2886e-201">**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione server-server.</span><span class="sxs-lookup"><span data-stu-id="2886e-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="2886e-202">Windows Server 2008 R2 e Windows Server 2012 richiedono diverse procedure per installare Windows identifica Foundation.</span><span class="sxs-lookup"><span data-stu-id="2886e-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="2886e-203">Selezionare il sistema operativo del server dall'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="2886e-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="2886e-204">Windows Server 2008 R2 per Windows Server 2008 R2, verificare se è già stato installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="2886e-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="2886e-205">Per eseguire questa operazione, vedere **aggiungere/rimuovere programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="2886e-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="2886e-206">Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.</span><span class="sxs-lookup"><span data-stu-id="2886e-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="2886e-207">Windows Server 2012 per Windows Server 2012, è possibile usare **Server Manager** per installare Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="2886e-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="2886e-208">Nella **procedura guidata per l'aggiunta di ruoli e funzionalità**in Server Manager selezionare **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2886e-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="2886e-209">Selezionare **Windows Identity Foundation 3,5** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2886e-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="2886e-210">Fare clic su **Avanti**e quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="2886e-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="2886e-211">Non installare provider di socket sovrapposti nei server multimediali</span><span class="sxs-lookup"><span data-stu-id="2886e-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="2886e-212">Non installare alcun software client server ISA (Microsoft Internet Security and Acceleration) o qualsiasi altro software LSP (Layered Service Provider) Winsock in qualsiasi server front-end o mediazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="2886e-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="2886e-213">L'installazione di questo software può causare scarse prestazioni del traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="2886e-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2886e-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2886e-214">See Also</span></span>


[<span data-ttu-id="2886e-215">Requisiti software degli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2886e-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

