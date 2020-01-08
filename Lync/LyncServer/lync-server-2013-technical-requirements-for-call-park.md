---
title: 'Lync Server 2013: Requisiti tecnici per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="005dc-102">Requisiti tecnici per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005dc-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="005dc-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="005dc-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="005dc-104">Questa sezione descrive i requisiti tecnici seguenti per il parcheggio delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="005dc-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="005dc-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="005dc-105">Hardware requirements</span></span>

  - <span data-ttu-id="005dc-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="005dc-106">Software requirements</span></span>

  - <span data-ttu-id="005dc-107">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="005dc-107">Port requirements</span></span>

  - <span data-ttu-id="005dc-108">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="005dc-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="005dc-109">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="005dc-109">Hardware Requirements</span></span>

<span data-ttu-id="005dc-110">L'applicazione Call Park ha gli stessi requisiti hardware dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="005dc-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="005dc-111">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="005dc-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="005dc-112">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="005dc-112">Software Requirements</span></span>

<span data-ttu-id="005dc-113">L'applicazione Call Park ha gli stessi requisiti del sistema operativo e i prerequisiti software come server front-end.</span><span class="sxs-lookup"><span data-stu-id="005dc-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="005dc-114">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="005dc-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="005dc-115">Tutti i server front-end e i server Standard Edition in cui è distribuita l'applicazione Parcheggio di chiamata devono avere installato Windows Media Format Runtime per i server che utilizzano Windows Server 2008 R2 o Microsoft Media Foundation per i server che utilizzano Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="005dc-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="005dc-116">Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="005dc-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="005dc-117">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che chiamano Play Park per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="005dc-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="005dc-118">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="005dc-118">Port Requirements</span></span>

<span data-ttu-id="005dc-119">L'applicazione Call Park USA la porta seguente:</span><span class="sxs-lookup"><span data-stu-id="005dc-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="005dc-120">**Porta 5075**   usata per le richieste di ascolto SIP.</span><span class="sxs-lookup"><span data-stu-id="005dc-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="005dc-121">Questa porta è un'impostazione predefinita che puoi modificare usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="005dc-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="005dc-122">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="005dc-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="005dc-123">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="005dc-123">Audio File Requirements</span></span>

<span data-ttu-id="005dc-124">L'applicazione Call Park supporta solo file con estensione WMA (Windows Media Audio) per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="005dc-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="005dc-125">È possibile usare Microsoft Expression Encoder 4 per personalizzare i file per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="005dc-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="005dc-126">Per scaricare Expression Encoder 4, vedere "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="005dc-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="005dc-127">Usare lo strumento per convertire il file in un formato WMA.</span><span class="sxs-lookup"><span data-stu-id="005dc-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="005dc-128">Il formato consigliato per i file musicali di Call Park-in-blocco è l'audio multimediale 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="005dc-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="005dc-129">Il file convertito viene riprodotto al telefono solo a 16 kHz, anche se è stato registrato in 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="005dc-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

