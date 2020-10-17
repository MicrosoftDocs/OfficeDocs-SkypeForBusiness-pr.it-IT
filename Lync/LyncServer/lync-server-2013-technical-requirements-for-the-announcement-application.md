---
title: "Lync Server 2013: requisiti tecnici per l'applicazione annuncio"
description: "Lync Server 2013: requisiti tecnici per l'applicazione annuncio."
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
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550312"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f41aa-103">Requisiti tecnici per l'applicazione annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f41aa-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f41aa-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f41aa-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f41aa-105">In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione annuncio:</span><span class="sxs-lookup"><span data-stu-id="f41aa-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="f41aa-106">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="f41aa-106">Hardware requirements</span></span>

  - <span data-ttu-id="f41aa-107">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="f41aa-107">Software requirements</span></span>

  - <span data-ttu-id="f41aa-108">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="f41aa-108">Port requirements</span></span>

  - <span data-ttu-id="f41aa-109">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="f41aa-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f41aa-110">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="f41aa-110">Hardware Requirements</span></span>

<span data-ttu-id="f41aa-111">L'applicazione annuncio ha gli stessi requisiti hardware dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="f41aa-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="f41aa-112">Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f41aa-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f41aa-113">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="f41aa-113">Software Requirements</span></span>

<span data-ttu-id="f41aa-114">L'applicazione annuncio ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="f41aa-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="f41aa-115">Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f41aa-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f41aa-116">Tutti i Front End Server o i server Standard Edition che eseguono l'applicazione annuncio devono disporre del runtime del formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f41aa-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="f41aa-117">Per Windows Server 2008 R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="f41aa-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="f41aa-118">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (con estensione WMA) che l'applicazione annuncio riproduce per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="f41aa-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="f41aa-119">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="f41aa-119">Port Requirements</span></span>

<span data-ttu-id="f41aa-120">L'applicazione annuncio utilizza la porta seguente:</span><span class="sxs-lookup"><span data-stu-id="f41aa-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="f41aa-121">**Porta 5071**     Utilizzato per le richieste di attesa SIP</span><span class="sxs-lookup"><span data-stu-id="f41aa-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f41aa-122">Questa porta è l'impostazione predefinita, che può essere modificata utilizzando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f41aa-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="f41aa-123">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f41aa-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="f41aa-124">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="f41aa-124">Audio File Requirements</span></span>

<span data-ttu-id="f41aa-125">L'applicazione Annuncio supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per la musica e gli annunci.</span><span class="sxs-lookup"><span data-stu-id="f41aa-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="f41aa-126">I requisiti dei file audio per l'applicazione annuncio sono identici a quelli dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="f41aa-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="f41aa-127">Per informazioni dettagliate, vedere [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="f41aa-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

