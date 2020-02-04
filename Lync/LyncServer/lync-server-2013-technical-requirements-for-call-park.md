---
title: 'Lync Server 2013: Requisiti tecnici per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="063ce-102">Requisiti tecnici per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="063ce-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="063ce-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="063ce-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="063ce-104">Questa sezione descrive i requisiti tecnici seguenti per il parcheggio delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="063ce-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="063ce-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="063ce-105">Hardware requirements</span></span>

  - <span data-ttu-id="063ce-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="063ce-106">Software requirements</span></span>

  - <span data-ttu-id="063ce-107">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="063ce-107">Port requirements</span></span>

  - <span data-ttu-id="063ce-108">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="063ce-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="063ce-109">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="063ce-109">Hardware Requirements</span></span>

<span data-ttu-id="063ce-110">L'applicazione Call Park ha gli stessi requisiti hardware dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="063ce-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="063ce-111">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="063ce-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="063ce-112">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="063ce-112">Software Requirements</span></span>

<span data-ttu-id="063ce-113">L'applicazione Call Park ha gli stessi requisiti del sistema operativo e i prerequisiti software come server front-end.</span><span class="sxs-lookup"><span data-stu-id="063ce-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="063ce-114">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="063ce-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="063ce-115">Tutti i server front-end e i server Standard Edition in cui è distribuita l'applicazione Parcheggio di chiamata devono avere installato Windows Media Format Runtime per i server che utilizzano Windows Server 2008 R2 o Microsoft Media Foundation per i server che utilizzano Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="063ce-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="063ce-116">Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="063ce-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="063ce-117">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che chiamano Play Park per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="063ce-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="063ce-118">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="063ce-118">Port Requirements</span></span>

<span data-ttu-id="063ce-119">L'applicazione Call Park USA la porta seguente:</span><span class="sxs-lookup"><span data-stu-id="063ce-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="063ce-120">**Porta 5075**   usata per le richieste di ascolto SIP.</span><span class="sxs-lookup"><span data-stu-id="063ce-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="063ce-121">Questa porta è un'impostazione predefinita che puoi modificare usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="063ce-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="063ce-122">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="063ce-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="063ce-123">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="063ce-123">Audio File Requirements</span></span>

<span data-ttu-id="063ce-124">L'applicazione Call Park supporta solo file con estensione WMA (Windows Media Audio) per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="063ce-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="063ce-125">È possibile usare Microsoft Expression Encoder 4 per personalizzare i file per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="063ce-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="063ce-126">Per scaricare Expression Encoder 4, vedere "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="063ce-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="063ce-127">Usare lo strumento per convertire il file in un formato WMA.</span><span class="sxs-lookup"><span data-stu-id="063ce-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="063ce-128">Il formato consigliato per i file musicali di Call Park-in-blocco è l'audio multimediale 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="063ce-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="063ce-129">Il file convertito viene riprodotto al telefono solo a 16 kHz, anche se è stato registrato in 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="063ce-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

