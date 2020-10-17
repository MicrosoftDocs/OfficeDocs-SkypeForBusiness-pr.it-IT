---
title: 'Lync Server 2013: requisiti software aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4a0c2e200c779d87a13c08eada968b27a7447f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521233"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="a0d34-102">Requisiti software aggiuntivi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d34-102">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0d34-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="a0d34-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="a0d34-104">Oltre ai requisiti hardware e del sistema operativo per le piattaforme server, Lync Server 2013 richiede l'installazione di software aggiuntivo nei server distribuiti.</span><span class="sxs-lookup"><span data-stu-id="a0d34-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0d34-105">Per informazioni dettagliate sui requisiti della piattaforma per i server che eseguono Lync Server, vedere <A href="lync-server-2013-server-hardware-platforms.md">server hardware Platforms for Lync server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a0d34-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="a0d34-106">Per informazioni dettagliate sui requisiti di sistema per i computer e i dispositivi client, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a0d34-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="a0d34-107">Per informazioni dettagliate sui requisiti software per gli strumenti di amministrazione, vedere <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative Tools software requirements in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a0d34-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="a0d34-108">Software aggiuntivo necessario per tutti i ruoli del server interni</span><span class="sxs-lookup"><span data-stu-id="a0d34-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="a0d34-109">In questa sezione sono elencati i software necessari per tutti i ruoli del server interni, ovvero tutti i ruoli del server Lync Server, ad eccezione del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a0d34-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="a0d34-110">I requisiti per i server perimetrali e i pool perimetrali sono elencati più avanti in questo argomento in **software aggiuntivo per i server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="a0d34-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a0d34-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="a0d34-112">Per ogni server che esegue Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a0d34-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a0d34-113">Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="a0d34-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="a0d34-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a0d34-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="a0d34-115">Lync Server richiede Microsoft .NET Framework 4,5 su tutti i ruoli del server interno e su qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server o Microsoft Lync Server 2013, strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a0d34-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="a0d34-116">Per Lync Server 2013, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0d34-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a0d34-117">Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a0d34-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="a0d34-118">Installazione di Microsoft .NET Framework 4,5 nei server che eseguono Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a0d34-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="a0d34-119">Quando si installa Microsoft .NET Framework 4,5 nei server che eseguiranno Lync Server 2013 e Windows Server 2012, è necessario eseguire un ulteriore passaggio.</span><span class="sxs-lookup"><span data-stu-id="a0d34-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="a0d34-120">Dopo l'installazione di .NET Framework 4,5, utilizzare Server Manager per installare l'attivazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="a0d34-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="a0d34-121">**Per installare l'attivazione di .NET 4,5 HTTP su Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="a0d34-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="a0d34-122">Fare clic sul pulsante **Start** , scegliere **programmi**, quindi **strumenti di amministrazione**e quindi fare clic su **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="a0d34-123">In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="a0d34-124">Espandere **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="a0d34-125">Selezionare **attivazione WCF** se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="a0d34-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="a0d34-126">Quindi selezionare **attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="a0d34-127">Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a0d34-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="a0d34-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="a0d34-128">Windows Identity Foundation</span></span>

<span data-ttu-id="a0d34-129">**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="a0d34-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a0d34-130">Windows Server 2008 R2 e Windows Server 2012 richiedono procedure diverse per installare Windows identificate Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0d34-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a0d34-131">Selezionare il sistema operativo del server dall'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="a0d34-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="a0d34-132">Windows Server 2008 R2 per Windows Server 2008 R2, controllare se è già stato installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="a0d34-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a0d34-133">A tale scopo, andare a **Aggiungi/Rimuovi programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a0d34-134">Per informazioni dettagliate sull'installazione di Windows Identity Foundation, vedere [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="a0d34-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="a0d34-135">Windows Server 2012 per Windows Server 2012, è possibile utilizzare **Gestione server** per installare Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0d34-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a0d34-136">Nell' **Aggiunta guidata ruoli e funzionalità**in Server Manager, selezionare **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a0d34-137">Selezionare **Windows Identity Foundation 3,5** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a0d34-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a0d34-138">Fare clic su **Avanti**e quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="a0d34-139">Software aggiuntivo per tutti i Front End Server e i server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a0d34-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="a0d34-140">Tutti i Front End Server e i server Standard Edition devono eseguire anche Internet Information Services (IIS) con alcuni moduli.</span><span class="sxs-lookup"><span data-stu-id="a0d34-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="a0d34-141">Inoltre, tutti i Front End Server e i server Standard Edition in cui vengono distribuite le conferenze, l'applicazione Parcheggio di chiamata, l'annuncio o i Response Group devono eseguire Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="a0d34-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="a0d34-142">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="a0d34-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="a0d34-143">I Front End Server e i server Standard Edition devono eseguire Internet Information Services (IIS), con i moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0d34-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a0d34-144">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="a0d34-144">Static Content</span></span>

  - <span data-ttu-id="a0d34-145">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="a0d34-145">Default Document</span></span>

  - <span data-ttu-id="a0d34-146">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="a0d34-146">HTTP Errors</span></span>

  - <span data-ttu-id="a0d34-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a0d34-147">ASP.NET</span></span>

  - <span data-ttu-id="a0d34-148">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="a0d34-148">.NET Extensibility</span></span>

  - <span data-ttu-id="a0d34-149">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="a0d34-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a0d34-150">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="a0d34-150">ISAPI Filters</span></span>

  - <span data-ttu-id="a0d34-151">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="a0d34-151">HTTP Logging</span></span>

  - <span data-ttu-id="a0d34-152">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="a0d34-152">Logging Tools</span></span>

  - <span data-ttu-id="a0d34-153">Analisi della</span><span class="sxs-lookup"><span data-stu-id="a0d34-153">Tracing</span></span>

  - <span data-ttu-id="a0d34-154">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="a0d34-154">Windows Authentication</span></span>

  - <span data-ttu-id="a0d34-155">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="a0d34-155">Request Filtering</span></span>

  - <span data-ttu-id="a0d34-156">Compressione contenuto statico</span><span class="sxs-lookup"><span data-stu-id="a0d34-156">Static Content Compression</span></span>

  - <span data-ttu-id="a0d34-157">Compressione contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="a0d34-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="a0d34-158">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="a0d34-158">IIS Management Console</span></span>

  - <span data-ttu-id="a0d34-159">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="a0d34-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a0d34-160">Autenticazione anonima (è installata per impostazione predefinita durante l'installazione di IIS).</span><span class="sxs-lookup"><span data-stu-id="a0d34-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a0d34-161">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="a0d34-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="a0d34-162">Windows Media Format Runtime e Windows Desktop Experience</span><span class="sxs-lookup"><span data-stu-id="a0d34-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="a0d34-163">**Esperienza desktop di Windows** Tutti i Front End Server e i server Standard Edition in cui verrà distribuito il servizio di conferenza devono avere installato Windows Media Format Runtime, che, ad eccezione di Windows Server 2012, è installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="a0d34-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="a0d34-164">Windows Server 2012 richiede Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0d34-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="a0d34-165">Runtime formato Windows Media è necessario per l'esecuzione di file Windows Media Audio (con estensione wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="a0d34-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="a0d34-166">È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0d34-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="a0d34-167">Se Lync Server 2013 non trova questo software nel server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a0d34-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="a0d34-168">Software aggiuntivo per server front end e server Standard Edition in esecuzione su Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a0d34-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="a0d34-169">I Front End Server richiedono .NET 3,5, che non è installato per impostazione predefinita in Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a0d34-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="a0d34-170">Per installarlo, inserire il supporto di installazione di Windows Server 2012 nell'unità D e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a0d34-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="a0d34-171">Per informazioni dettagliate sull'installazione di .NET 3,5 nei server che eseguono Windows Server 2012, vedere "Considerazioni sulla distribuzione di Microsoft .NET Framework 3,5" all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=275032> .</span><span class="sxs-lookup"><span data-stu-id="a0d34-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="a0d34-172">Software aggiuntivo per i server Director</span><span class="sxs-lookup"><span data-stu-id="a0d34-172">Additional Software for Directors</span></span>

<span data-ttu-id="a0d34-173">Gli amministratori devono eseguire Internet Information Services (IIS), con i moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0d34-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a0d34-174">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="a0d34-174">Static Content</span></span>

  - <span data-ttu-id="a0d34-175">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="a0d34-175">Default Document</span></span>

  - <span data-ttu-id="a0d34-176">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="a0d34-176">HTTP Errors</span></span>

  - <span data-ttu-id="a0d34-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a0d34-177">ASP.NET</span></span>

  - <span data-ttu-id="a0d34-178">Estendibilità .NET</span><span class="sxs-lookup"><span data-stu-id="a0d34-178">.NET Extensibility</span></span>

  - <span data-ttu-id="a0d34-179">Estensioni ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="a0d34-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a0d34-180">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="a0d34-180">ISAPI Filters</span></span>

  - <span data-ttu-id="a0d34-181">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="a0d34-181">HTTP Logging</span></span>

  - <span data-ttu-id="a0d34-182">Strumenti di registrazione</span><span class="sxs-lookup"><span data-stu-id="a0d34-182">Logging Tools</span></span>

  - <span data-ttu-id="a0d34-183">Analisi della</span><span class="sxs-lookup"><span data-stu-id="a0d34-183">Tracing</span></span>

  - <span data-ttu-id="a0d34-184">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="a0d34-184">Windows Authentication</span></span>

  - <span data-ttu-id="a0d34-185">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="a0d34-185">Request Filtering</span></span>

  - <span data-ttu-id="a0d34-186">Compressione contenuto statico</span><span class="sxs-lookup"><span data-stu-id="a0d34-186">Static Content Compression</span></span>

  - <span data-ttu-id="a0d34-187">Console di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="a0d34-187">IIS Management Console</span></span>

  - <span data-ttu-id="a0d34-188">Strumenti e script di gestione IIS</span><span class="sxs-lookup"><span data-stu-id="a0d34-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a0d34-189">Autenticazione anonima (modulo installato per impostazione predefinita durante l'installazione di IIS)</span><span class="sxs-lookup"><span data-stu-id="a0d34-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a0d34-190">Autenticazione mapping certificati client</span><span class="sxs-lookup"><span data-stu-id="a0d34-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="a0d34-191">Software aggiuntivo per i front end server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="a0d34-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="a0d34-192">I server front end di chat persistente devono eseguire Accodamento messaggi (noto anche come MSMQ), che è un componente di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a0d34-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="a0d34-193">Per informazioni sull'abilitazione di MSMQ, [fare clic qui.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0d34-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="a0d34-194">Software aggiuntivo per server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a0d34-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="a0d34-195">I server perimetrali richiedono il software seguente:</span><span class="sxs-lookup"><span data-stu-id="a0d34-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="a0d34-196">Per ogni server che esegue Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a0d34-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a0d34-197">Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="a0d34-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="a0d34-198">Lync Server richiede Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="a0d34-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="a0d34-199">Per Lync Server 2013 installato in Windows Server 2008 R2, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0d34-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a0d34-200">Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a0d34-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="a0d34-201">**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="a0d34-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a0d34-202">Windows Server 2008 R2 e Windows Server 2012 richiedono procedure diverse per installare Windows identificate Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0d34-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a0d34-203">Selezionare il sistema operativo del server dall'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="a0d34-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="a0d34-204">Windows Server 2008 R2 per Windows Server 2008 R2, controllare se è già stato installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="a0d34-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a0d34-205">A tale scopo, andare a **Aggiungi/Rimuovi programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a0d34-206">Per informazioni dettagliate sull'installazione di Windows Identity Foundation, vedere [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="a0d34-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="a0d34-207">Windows Server 2012 per Windows Server 2012, è possibile utilizzare **Gestione server** per installare Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0d34-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a0d34-208">Nell' **Aggiunta guidata ruoli e funzionalità**in Server Manager, selezionare **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a0d34-209">Selezionare **Windows Identity Foundation 3,5** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a0d34-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a0d34-210">Fare clic su **Avanti**e quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a0d34-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="a0d34-211">Non installare provider LSP (Layered Service Provider) nei server multimediali</span><span class="sxs-lookup"><span data-stu-id="a0d34-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="a0d34-212">Non installare alcun software client del server Microsoft Internet Security and Acceleration (ISA) o qualsiasi altro software LSP (Layered Service Providers) di Winsock, in tutti i Front End Server o Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="a0d34-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="a0d34-213">L'installazione di questo software potrebbe causare scarse prestazioni del traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="a0d34-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0d34-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0d34-214">See Also</span></span>


[<span data-ttu-id="a0d34-215">Requisiti software per gli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d34-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

