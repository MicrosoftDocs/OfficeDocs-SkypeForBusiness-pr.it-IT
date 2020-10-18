---
title: Installare i sistemi operativi e il software prerequisito nei server
description: Installare i sistemi operativi e il software prerequisito nei server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574132"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="5a082-103">Installare i sistemi operativi e il software prerequisito sui server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a082-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a082-104">_**Ultimo argomento modificato:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="5a082-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="5a082-105">Dopo aver configurato l'hardware e l'infrastruttura del sistema, è necessario installare i sistemi operativi e gli aggiornamenti Windows appropriati, oltre a tutti gli altri prerequisiti software, in ogni server che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="5a082-105">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="5a082-106">Questo include ogni ruolo del server Lync Server 2013 e qualsiasi server o server dell'infrastruttura aggiuntivi che eseguono SQL Server necessari per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a082-106">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5a082-107">In questa sezione viene descritta l'installazione dei sistemi operativi e del software prerequisito per i server interni.</span><span class="sxs-lookup"><span data-stu-id="5a082-107">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="5a082-108">Se si distribuiscono server perimetrali per il supporto dell'accesso degli utenti esterni, è inoltre necessario installare i sistemi operativi e il software prerequisito per tali server, inclusi i server perimetrali e i server proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="5a082-108">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="5a082-109">Per informazioni dettagliate sulla preparazione dei server per il supporto dell'accesso degli utenti esterni, vedere <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a082-109">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="5a082-110">Installare il sistema operativo Windows nei server</span><span class="sxs-lookup"><span data-stu-id="5a082-110">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="5a082-111">In ogni server che si sta distribuendo, installare il sistema operativo Windows appropriato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5a082-111">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="5a082-112">**Server che eseguono Lync Server 2013**     Per informazioni dettagliate sui requisiti del sistema operativo per i server che eseguono Lync Server 2013, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="5a082-112">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="5a082-113">**Server**     di database Per informazioni dettagliate sui requisiti del sistema operativo per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a082-113">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="5a082-114">Per SQL Server 2012, vedere la documentazione in linea di SQL Server 2012 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="5a082-114">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5a082-115">Se si sta installando Lync Server 2013 su Windows Server &nbsp; 2008 &nbsp; R2 con SP1, è innanzitutto necessario installare l'aggiornamento descritto nell'articolo 2646886 della Microsoft Knowledge Base "FIX: l'heap danneggiati si verifica quando un modulo chiama il metodo INSERTENTITYBODY in IIS 7,5", a <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="5a082-115">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="5a082-116">È inoltre necessario modificare il registro di sistema come descritto nell'articolo della Knowledge base, gli <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">ID evento 32402, 61045 vengono registrati nei server front end di Lync server 2013 installati in Windows Server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="5a082-116">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="5a082-117">Installare l'aggiornamento di Windows nei server</span><span class="sxs-lookup"><span data-stu-id="5a082-117">Install Windows Update on Servers</span></span>

<span data-ttu-id="5a082-118">Installare gli aggiornamenti seguenti da Windows Update su ogni server:</span><span class="sxs-lookup"><span data-stu-id="5a082-118">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="5a082-119">**Windows Update per i server che eseguono Lync Server 2013**     Per informazioni dettagliate sugli aggiornamenti da Windows Update necessari per i server che eseguono Lync Server 2013, vedere [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5a082-119">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="5a082-120">**Server**     di database Per informazioni dettagliate sugli aggiornamenti da Windows Update necessari per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="5a082-120">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="5a082-121">Per SQL Server 2012, vedere la documentazione in linea di SQL Server 2012 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="5a082-121">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="5a082-122">Installare altro software prerequisito nei server</span><span class="sxs-lookup"><span data-stu-id="5a082-122">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="5a082-123">Lync Server 2013 richiede l'installazione del software aggiuntivo seguente nei server:</span><span class="sxs-lookup"><span data-stu-id="5a082-123">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="5a082-124">**Software prerequisito per i server che eseguono Lync Server 2013**     I prerequisiti software aggiuntivi per i server che eseguono Lync Server 2013 dipendono dal ruolo del server in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a082-124">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="5a082-125">Per informazioni dettagliate sui requisiti software specifici per ogni server, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5a082-125">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="5a082-126">**Windows Identity Foundation**     Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="5a082-126">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="5a082-127">Per verificare che sia già stato installato nel computer, andare al pannello di controllo, fare clic su **programmi e funzionalità**, **visualizzare gli aggiornamenti installati**e guardare in **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="5a082-127">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="5a082-128">Per informazioni dettagliate sull'installazione di Windows Identity Foundation, vedere [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="5a082-128">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="5a082-129">**Microsoft .NET Framework 4,5**     Per Lync Server 2013 è necessaria l'edizione a 64 bit di Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="5a082-129">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="5a082-130">**Software prerequisito per i server**     di database Per informazioni dettagliate su Windows Update necessario per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server 2012 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="5a082-130">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5a082-131">Lync Server 2013 installa automaticamente Microsoft SQL Server 2012 Express in ogni server Standard Edition e in ogni server che esegue Lync Server 2013 in cui si trova l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="5a082-131">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="5a082-132">Runtime formato Windows **media**     Tutti i Front End Server e i server Standard Edition in cui verrà distribuito il servizio di conferenza devono avere installato Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="5a082-132">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="5a082-133">Runtime formato Windows Media è necessario per l'esecuzione di file Windows Media Audio (con estensione wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="5a082-133">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5a082-134">Per Windows Server 2012 e Windows Server 2012 R2, il runtime del formato Windows Media viene installato con Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="5a082-134">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5a082-135">Per Windows Server &nbsp; 2008 e Windows server &nbsp; 2008 &nbsp; R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="5a082-135">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="5a082-136">È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a082-136">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="5a082-137">Se Lync Server 2013 non trova questo software nel server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5a082-137">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

