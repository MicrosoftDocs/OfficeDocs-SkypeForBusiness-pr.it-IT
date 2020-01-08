---
title: 'Lync Server 2013: Requisiti tecnici per i Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="64623-102">Requisiti tecnici per i Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64623-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64623-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="64623-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="64623-104">In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione Response Group:</span><span class="sxs-lookup"><span data-stu-id="64623-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="64623-105">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="64623-105">Hardware requirements</span></span>

  - <span data-ttu-id="64623-106">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="64623-106">Software requirements</span></span>

  - <span data-ttu-id="64623-107">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="64623-107">Port requirements</span></span>

  - <span data-ttu-id="64623-108">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="64623-108">Audio file requirements</span></span>

  - <span data-ttu-id="64623-109">Requisiti dello strumento di configurazione dei gruppi di risposta</span><span class="sxs-lookup"><span data-stu-id="64623-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="64623-110">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="64623-110">Hardware Requirements</span></span>

<span data-ttu-id="64623-111">L'applicazione Response Group ha gli stessi requisiti hardware dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="64623-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="64623-112">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="64623-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="64623-113">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="64623-113">Software Requirements</span></span>

<span data-ttu-id="64623-114">L'applicazione Response Group offre gli stessi requisiti del sistema operativo e i prerequisiti software come server front-end.</span><span class="sxs-lookup"><span data-stu-id="64623-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="64623-115">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="64623-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="64623-116">Se si usano file di Windows Media Audio (con estensione WMA) per la musica e gli annunci di Response Group, tutti i server front-end o le edizioni standard che eseguono l'applicazione Response Group devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per server che utilizzano Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="64623-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="64623-117">Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="64623-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="64623-118">Per altre informazioni sui requisiti audio, vedere "requisiti per i file audio" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="64623-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="64623-119">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="64623-119">Port Requirements</span></span>

<span data-ttu-id="64623-120">L'applicazione Response Group usa le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="64623-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="64623-121">**Porta 5071**   usata per le richieste di ascolto SIP</span><span class="sxs-lookup"><span data-stu-id="64623-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="64623-122">**Porta 8404**   usata per le comunicazioni interserver</span><span class="sxs-lookup"><span data-stu-id="64623-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64623-123">Questa porta viene usata per il servizio di creazione delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool che ha più di un server front-end.</span><span class="sxs-lookup"><span data-stu-id="64623-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="64623-124">Queste porte sono impostazioni predefinite che è possibile modificare usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="64623-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="64623-125">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="64623-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="64623-126">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="64623-126">Audio File Requirements</span></span>

<span data-ttu-id="64623-127">L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (con estensione WMA) per i messaggi di Response Group, la musica in attesa o le domande di risposta vocale interattiva (IVR).</span><span class="sxs-lookup"><span data-stu-id="64623-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="64623-128">Il formato di file audio Windows Media richiede che Windows Media Format Runtime sia installato nei server front-end in cui è in esecuzione Windows Server 2008 R2 e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="64623-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="64623-129">Per altri dettagli, vedere "requisiti software" in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="64623-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="64623-130">Formati di file Wave supportati</span><span class="sxs-lookup"><span data-stu-id="64623-130">Supported Wave File Formats</span></span>

<span data-ttu-id="64623-131">Tutti i file Wave devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="64623-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="64623-132">file a 8 bit o a 16 bit</span><span class="sxs-lookup"><span data-stu-id="64623-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="64623-133">Modulazione del codice pulsazione lineare (LPCM), A-Law o mu-Law Format</span><span class="sxs-lookup"><span data-stu-id="64623-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="64623-134">Mono o stereo</span><span class="sxs-lookup"><span data-stu-id="64623-134">Mono or stereo</span></span>

  - <span data-ttu-id="64623-135">4 MB o meno</span><span class="sxs-lookup"><span data-stu-id="64623-135">4MB or less</span></span>

<span data-ttu-id="64623-136">Per ottenere prestazioni ottimali, è consigliabile un file Wave da 16 kHz, mono e a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="64623-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="64623-137">Formati di file audio Windows Media supportati</span><span class="sxs-lookup"><span data-stu-id="64623-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="64623-138">Se si usa un file audio Windows Media, valutare l'uso di velocità in bit bassi e verificare le prestazioni del sistema in Load.</span><span class="sxs-lookup"><span data-stu-id="64623-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="64623-139">Puoi usare Microsoft Expression Encoder 4 per convertire un file nel formato audio di Windows Media.</span><span class="sxs-lookup"><span data-stu-id="64623-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="64623-140">Per scaricare Expression Encoder 4, vedere [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="64623-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="64623-141">Requisiti dello strumento di configurazione dei gruppi di risposta</span><span class="sxs-lookup"><span data-stu-id="64623-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="64623-142">Lo strumento di configurazione Response Group supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="64623-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64623-143">sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="64623-143">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="64623-144">Sono supportate solo le versioni a 32 bit di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="64623-144">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="64623-145">Sistemi operativi e browser Web supportati</span><span class="sxs-lookup"><span data-stu-id="64623-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64623-146">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="64623-146">Operating system</span></span></th>
<th><span data-ttu-id="64623-147">Web browser</span><span class="sxs-lookup"><span data-stu-id="64623-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64623-148">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="64623-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="64623-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="64623-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="64623-150">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-151">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64623-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="64623-152">Windows 7</span></span></p>
<p><span data-ttu-id="64623-153">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="64623-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="64623-154">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-155">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64623-156">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="64623-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="64623-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="64623-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="64623-158">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-159">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64623-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="64623-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="64623-161">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="64623-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="64623-162">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-163">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="64623-164">Console agente di Response Group</span><span class="sxs-lookup"><span data-stu-id="64623-164">Response Group Agent Console</span></span>

<span data-ttu-id="64623-165">La console agente supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="64623-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64623-166">sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="64623-166">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="64623-167">Sono supportate solo le versioni a 32 bit di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="64623-167">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="64623-168">Sistemi operativi e browser Web supportati</span><span class="sxs-lookup"><span data-stu-id="64623-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64623-169">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="64623-169">Operating system</span></span></th>
<th><span data-ttu-id="64623-170">Web browser</span><span class="sxs-lookup"><span data-stu-id="64623-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64623-171">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="64623-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="64623-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="64623-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="64623-173">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-174">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64623-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="64623-175">Windows 7</span></span></p>
<p><span data-ttu-id="64623-176">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="64623-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="64623-177">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-178">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="64623-179">Firefox 10,0</span><span class="sxs-lookup"><span data-stu-id="64623-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="64623-180">Chrome 18,0</span><span class="sxs-lookup"><span data-stu-id="64623-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64623-181">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="64623-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="64623-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="64623-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="64623-183">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-184">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64623-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="64623-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="64623-186">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="64623-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="64623-187">Internet Explorer 8 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="64623-188">Internet Explorer 9 (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="64623-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="64623-189">Firefox 10,0</span><span class="sxs-lookup"><span data-stu-id="64623-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="64623-190">Chrome 18,0</span><span class="sxs-lookup"><span data-stu-id="64623-190">Chrome 18.0</span></span></p></td>
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

