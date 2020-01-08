---
title: "Lync Server 2013: Requisiti tecnici per l'applicazione Annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f92cc-102">Requisiti tecnici per l'applicazione Annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f92cc-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f92cc-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f92cc-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f92cc-104">Questa sezione descrive i requisiti tecnici seguenti per l'applicazione di annuncio:</span><span class="sxs-lookup"><span data-stu-id="f92cc-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="f92cc-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="f92cc-105">Hardware requirements</span></span>

  - <span data-ttu-id="f92cc-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="f92cc-106">Software requirements</span></span>

  - <span data-ttu-id="f92cc-107">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="f92cc-107">Port requirements</span></span>

  - <span data-ttu-id="f92cc-108">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="f92cc-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f92cc-109">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="f92cc-109">Hardware Requirements</span></span>

<span data-ttu-id="f92cc-110">L'applicazione di annuncio ha gli stessi requisiti hardware dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="f92cc-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="f92cc-111">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f92cc-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f92cc-112">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="f92cc-112">Software Requirements</span></span>

<span data-ttu-id="f92cc-113">L'applicazione di annuncio ha gli stessi requisiti di sistema operativo e prerequisiti software come server front-end.</span><span class="sxs-lookup"><span data-stu-id="f92cc-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="f92cc-114">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f92cc-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f92cc-115">Tutti i server front-end o i server Standard Edition che eseguono l'applicazione annunci devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f92cc-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="f92cc-116">Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="f92cc-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="f92cc-117">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che l'applicazione di annuncio riproduce per gli annunci e la musica.</span><span class="sxs-lookup"><span data-stu-id="f92cc-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="f92cc-118">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="f92cc-118">Port Requirements</span></span>

<span data-ttu-id="f92cc-119">L'applicazione di annuncio usa la porta seguente:</span><span class="sxs-lookup"><span data-stu-id="f92cc-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="f92cc-120">**Porta 5071**   usata per le richieste di ascolto SIP</span><span class="sxs-lookup"><span data-stu-id="f92cc-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f92cc-121">Questa porta è l'impostazione predefinita, che può essere modificata usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f92cc-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="f92cc-122">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f92cc-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="f92cc-123">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="f92cc-123">Audio File Requirements</span></span>

<span data-ttu-id="f92cc-124">L'applicazione di annuncio supporta il formato di file Wave (con estensione wav) e il formato di file WMA (Windows Media Audio) per musica e annunci.</span><span class="sxs-lookup"><span data-stu-id="f92cc-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="f92cc-125">I requisiti per i file audio per l'applicazione di annuncio sono gli stessi per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="f92cc-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="f92cc-126">Per informazioni dettagliate, vedere [requisiti tecnici per il gruppo di risposte in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="f92cc-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

