---
title: "Lync Server 2013: requisiti tecnici per l'applicazione annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="dc4c7-102">Requisiti tecnici per l'applicazione annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc4c7-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc4c7-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="dc4c7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="dc4c7-104">In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione annuncio:</span><span class="sxs-lookup"><span data-stu-id="dc4c7-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="dc4c7-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="dc4c7-105">Hardware requirements</span></span>

  - <span data-ttu-id="dc4c7-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="dc4c7-106">Software requirements</span></span>

  - <span data-ttu-id="dc4c7-107">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="dc4c7-107">Port requirements</span></span>

  - <span data-ttu-id="dc4c7-108">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="dc4c7-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="dc4c7-109">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="dc4c7-109">Hardware Requirements</span></span>

<span data-ttu-id="dc4c7-110">L'applicazione annuncio ha gli stessi requisiti hardware dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="dc4c7-111">Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="dc4c7-112">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="dc4c7-112">Software Requirements</span></span>

<span data-ttu-id="dc4c7-113">L'applicazione annuncio ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="dc4c7-114">Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="dc4c7-115">Tutti i Front End Server o i server Standard Edition che eseguono l'applicazione annuncio devono disporre del runtime del formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="dc4c7-116">Per Windows Server 2008 R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="dc4c7-117">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (con estensione WMA) che l'applicazione annuncio riproduce per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="dc4c7-118">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="dc4c7-118">Port Requirements</span></span>

<span data-ttu-id="dc4c7-119">L'applicazione annuncio utilizza la porta seguente:</span><span class="sxs-lookup"><span data-stu-id="dc4c7-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="dc4c7-120">**Porta 5071**   utilizzata per le richieste di attesa SIP</span><span class="sxs-lookup"><span data-stu-id="dc4c7-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc4c7-121">Questa porta è l'impostazione predefinita, che può essere modificata utilizzando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="dc4c7-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="dc4c7-122">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="dc4c7-123">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="dc4c7-123">Audio File Requirements</span></span>

<span data-ttu-id="dc4c7-124">L'applicazione Annuncio supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per la musica e gli annunci.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="dc4c7-125">I requisiti dei file audio per l'applicazione annuncio sono identici a quelli dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="dc4c7-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="dc4c7-126">Per informazioni dettagliate, vedere [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="dc4c7-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

