---
title: Installare i sistemi operativi e il software prerequisito nei server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="b5651-102">Installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5651-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5651-103">_**Argomento Ultima modifica:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="b5651-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="b5651-104">Dopo aver configurato l'infrastruttura hardware e di sistema, è necessario installare i sistemi operativi e gli aggiornamenti appropriati di Windows, oltre a tutti gli altri software prerequisiti in ogni server che si sta distribuendo.</span><span class="sxs-lookup"><span data-stu-id="b5651-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="b5651-105">Questo include ogni ruolo del server Lync Server 2013 e tutti i server di infrastruttura o i server aggiuntivi che esegue SQL Server necessari per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b5651-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5651-106">Questa sezione descrive l'installazione di sistemi operativi e software prerequisito per i server interni.</span><span class="sxs-lookup"><span data-stu-id="b5651-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="b5651-107">Se si distribuisce Edge Server per supportare l'accesso degli utenti esterni, è necessario installare anche sistemi operativi e software prerequisito per questi server, inclusi i server perimetrali e i server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="b5651-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="b5651-108">Per informazioni dettagliate sulla preparazione dei server per il supporto dell'accesso degli utenti esterni, vedere <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b5651-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="b5651-109">Installare sistemi operativi Windows nei server</span><span class="sxs-lookup"><span data-stu-id="b5651-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="b5651-110">In ogni server che si sta distribuendo installare il sistema operativo Windows appropriato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b5651-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="b5651-111">**Server che effettuano Lync Server 2013**   per informazioni dettagliate sui requisiti del sistema operativo per i server che utilizzano Lync Server 2013, vedere [supporto dei sistemi operativi per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="b5651-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="b5651-112">**Server di database**   per informazioni dettagliate sui requisiti di sistema operativo per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5651-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="b5651-113">Per SQL Server 2012, vedere la documentazione online di [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b5651-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5651-114">Se si sta installando Lync Server 2013 in Windows&nbsp;server&nbsp;2008 R2 con SP1, è necessario installare prima di tutto l'aggiornamento descritto nell'articolo della Microsoft Knowledge based 2646886, "FIX: il danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="b5651-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="b5651-115">È inoltre necessario modificare il registro di sistema come descritto nell'articolo della Knowledge fine, gli <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">ID evento 32402, 61045 vengono registrati nei server front end di Lync server 2013 installati in Windows Server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="b5651-115">You must also modify the registry as described in the KB article, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="b5651-116">Installare Windows Update nei server</span><span class="sxs-lookup"><span data-stu-id="b5651-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="b5651-117">Installare gli aggiornamenti seguenti da Windows Update in ogni server:</span><span class="sxs-lookup"><span data-stu-id="b5651-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="b5651-118">**Windows Update per i server che esegue Lync Server 2013**   per informazioni dettagliate sugli aggiornamenti di Windows Update necessari per i server che usano Lync Server 2013, vedere [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b5651-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="b5651-119">**Server di database**   per informazioni dettagliate sugli aggiornamenti di Windows Update necessari per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b5651-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="b5651-120">Per SQL Server 2012, vedere la documentazione online di [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b5651-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="b5651-121">Installare altri software prerequisiti nei server</span><span class="sxs-lookup"><span data-stu-id="b5651-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="b5651-122">Lync Server 2013 richiede l'installazione del software aggiuntivo seguente nei server:</span><span class="sxs-lookup"><span data-stu-id="b5651-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="b5651-123">**Software prerequisito per i server che utilizzano Lync Server 2013**   i prerequisiti software aggiuntivi per i server che utilizzano Lync Server 2013 dipendono dal ruolo del server distribuito.</span><span class="sxs-lookup"><span data-stu-id="b5651-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="b5651-124">Per informazioni dettagliate sui requisiti software specifici per ogni server, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b5651-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="b5651-125">**Windows Identity Foundation**   Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="b5651-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="b5651-126">Per verificare che sia già stato installato nel computer, aprire il pannello di controllo, fare clic su **programmi e funzionalità**, **visualizzare gli aggiornamenti installati**e cercare in **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="b5651-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="b5651-127">Per informazioni dettagliate sull'installazione di Windows Identity Foundation [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657), vedere.</span><span class="sxs-lookup"><span data-stu-id="b5651-127">For details about installing Windows Identity Foundation, see [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="b5651-128">**Microsoft .NET Framework 4,5**   è necessaria la versione a 64 bit di Microsoft .NET Framework 4,5 per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5651-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="b5651-129">**Software prerequisito per i server**   di database per informazioni dettagliate sul Windows Update necessario per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)vedere la documentazione di SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b5651-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b5651-130">Lync Server 2013 installa automaticamente Microsoft SQL Server 2012 Express in ogni server Standard Edition e ogni server in cui è in uso Lync Server 2013 in cui si trova l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="b5651-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="b5651-131">**Windows Media Format Runtime**   tutti i server front-end e i server Standard Edition in cui verranno distribuiti i servizi di conferenza devono avere installato Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="b5651-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="b5651-132">Windows Media Format Runtime è necessario per eseguire i file di Windows Media Audio (con estensione WMA) che vengono riprodotti dalle applicazioni Park, annuncio e Response Group per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="b5651-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b5651-133">Per Windows Server 2012 e Windows Server 2012 R2 Windows Media Format Runtime viene installato con Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="b5651-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b5651-134">Per Windows Server&nbsp;2008 e windows server&nbsp;2008&nbsp;R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="b5651-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="b5651-135">È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5651-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="b5651-136">Se Lync Server 2013 non trova il software sul server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b5651-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

