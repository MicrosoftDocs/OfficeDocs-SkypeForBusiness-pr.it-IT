---
title: 'Lync Server 2013: requisiti tecnici per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dab3e57101efa2dd6dff1996a8f61eefc5d75021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="aa247-102">Requisiti tecnici per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa247-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa247-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="aa247-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="aa247-104">In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione Response Group:</span><span class="sxs-lookup"><span data-stu-id="aa247-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="aa247-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="aa247-105">Hardware requirements</span></span>

  - <span data-ttu-id="aa247-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="aa247-106">Software requirements</span></span>

  - <span data-ttu-id="aa247-107">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="aa247-107">Port requirements</span></span>

  - <span data-ttu-id="aa247-108">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="aa247-108">Audio file requirements</span></span>

  - <span data-ttu-id="aa247-109">Requisiti dello strumento di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="aa247-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="aa247-110">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="aa247-110">Hardware Requirements</span></span>

<span data-ttu-id="aa247-111">L'applicazione Response Group ha gli stessi requisiti hardware dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="aa247-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="aa247-112">Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="aa247-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="aa247-113">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="aa247-113">Software Requirements</span></span>

<span data-ttu-id="aa247-114">L'applicazione Response Group ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="aa247-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="aa247-115">Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="aa247-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="aa247-116">Se si utilizzano file di Windows Media Audio (con estensione WMA) per la musica e gli annunci di Response Group, tutti i Front End Server o i server Standard Edition che eseguono l'applicazione Response Group devono disporre del runtime di Windows Media Format installato per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="aa247-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="aa247-117">Per Windows Server 2008 R2, Windows Media Format Runtime è installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="aa247-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="aa247-118">Per ulteriori dettagli sui requisiti audio, vedere "Requisiti dei file audio" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="aa247-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="aa247-119">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="aa247-119">Port Requirements</span></span>

<span data-ttu-id="aa247-120">L'applicazione Response Group utilizza le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa247-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="aa247-121">**Porta 5071**   utilizzata per le richieste di attesa SIP</span><span class="sxs-lookup"><span data-stu-id="aa247-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="aa247-122">**Porta 8404**   utilizzata per le comunicazioni tra server</span><span class="sxs-lookup"><span data-stu-id="aa247-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa247-123">Questa porta viene utilizzata per il servizio di ricerca delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool con più server front-end.</span><span class="sxs-lookup"><span data-stu-id="aa247-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="aa247-124">Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aa247-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="aa247-125">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aa247-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="aa247-126">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="aa247-126">Audio File Requirements</span></span>

<span data-ttu-id="aa247-127">L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per i messaggi di Response Group, la musica di attesa o le domande del sistema IVR (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="aa247-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="aa247-128">Il formato di file Windows Media Audio richiede che il runtime del formato Windows Media sia installato nei front end server che eseguono Windows Server 2008 R2 e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa247-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="aa247-129">Per ulteriori dettagli, vedere i "Requisiti software" presi già in esame in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="aa247-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="aa247-130">Formati di file wave supportati</span><span class="sxs-lookup"><span data-stu-id="aa247-130">Supported Wave File Formats</span></span>

<span data-ttu-id="aa247-131">Tutti i file wave devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa247-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="aa247-132">File a 8 bit o a 16 bit</span><span class="sxs-lookup"><span data-stu-id="aa247-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="aa247-133">LPCM (Linear Pulse Code Modulation), formato A-Law o mu-Law</span><span class="sxs-lookup"><span data-stu-id="aa247-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="aa247-134">Mono o stereo</span><span class="sxs-lookup"><span data-stu-id="aa247-134">Mono or stereo</span></span>

  - <span data-ttu-id="aa247-135">Massimo 4 MB</span><span class="sxs-lookup"><span data-stu-id="aa247-135">4MB or less</span></span>

<span data-ttu-id="aa247-136">Per ottenere prestazioni ottimali con i file wave, è consigliabile utilizzare un file wave mono a 16 bit e 16 kHz.</span><span class="sxs-lookup"><span data-stu-id="aa247-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="aa247-137">Formati di file Windows Media Audio supportati</span><span class="sxs-lookup"><span data-stu-id="aa247-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="aa247-138">Se si utilizza un file Windows Media Audio, è consigliabile utilizzare velocità in bit basse e verificare le prestazioni del sistema sotto carico.</span><span class="sxs-lookup"><span data-stu-id="aa247-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="aa247-139">Per convertire un file nel formato Windows Media Audio, è possibile utilizzare Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="aa247-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="aa247-140">Per scaricare Expression Encoder 4, vedere [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="aa247-140">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="aa247-141">Requisiti dello Strumento di configurazione Response Group</span><span class="sxs-lookup"><span data-stu-id="aa247-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="aa247-142">Lo strumento di configurazione di Response Group supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="aa247-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa247-p107">Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="aa247-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="aa247-145">Sistemi operativi e Web browser supportati</span><span class="sxs-lookup"><span data-stu-id="aa247-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa247-146">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="aa247-146">Operating system</span></span></th>
<th><span data-ttu-id="aa247-147">Web browser</span><span class="sxs-lookup"><span data-stu-id="aa247-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa247-148">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="aa247-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="aa247-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa247-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa247-150">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-151">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa247-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="aa247-152">Windows 7</span></span></p>
<p><span data-ttu-id="aa247-153">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa247-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa247-154">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-155">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa247-156">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="aa247-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="aa247-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa247-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa247-158">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-159">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa247-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="aa247-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="aa247-161">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa247-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa247-162">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-163">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="aa247-164">Console degli agenti di Response Group</span><span class="sxs-lookup"><span data-stu-id="aa247-164">Response Group Agent Console</span></span>

<span data-ttu-id="aa247-165">La console degli agenti supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="aa247-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa247-p108">Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="aa247-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="aa247-168">Sistemi operativi e Web browser supportati</span><span class="sxs-lookup"><span data-stu-id="aa247-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa247-169">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="aa247-169">Operating system</span></span></th>
<th><span data-ttu-id="aa247-170">Web browser</span><span class="sxs-lookup"><span data-stu-id="aa247-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa247-171">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="aa247-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="aa247-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa247-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa247-173">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-174">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa247-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="aa247-175">Windows 7</span></span></p>
<p><span data-ttu-id="aa247-176">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa247-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa247-177">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-178">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="aa247-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="aa247-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="aa247-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa247-181">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="aa247-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="aa247-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="aa247-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="aa247-183">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-184">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa247-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="aa247-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="aa247-186">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="aa247-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="aa247-187">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-188">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="aa247-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="aa247-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="aa247-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="aa247-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="aa247-190">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

