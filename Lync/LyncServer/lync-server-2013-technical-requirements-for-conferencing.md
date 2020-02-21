---
title: Lync Server 2013 requisiti tecnici per le conferenze
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f28effa3ac80f4a2bca1fa062fcc3dfafb5d7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="d23c8-102">Requisiti tecnici per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d23c8-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d23c8-103">_**Ultimo argomento modificato:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="d23c8-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="d23c8-104">Per Lync Server 2013, servizi di conferenza telefonica con accesso esterno, A/V Conferencing, messaggistica istantanea e funzionalità di Web Conferencing vengono sempre eseguiti nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d23c8-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="d23c8-105">In questa sezione vengono fornite informazioni dettagliate sui requisiti hardware e software per questi server, insieme alla collocazione supportata.</span><span class="sxs-lookup"><span data-stu-id="d23c8-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="d23c8-106">La funzionalità di conferenza telefonica con accesso esterno include una vasta gamma di componenti.</span><span class="sxs-lookup"><span data-stu-id="d23c8-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="d23c8-107">Alcuni dei componenti sono specifici delle conferenze telefoniche con accesso esterno, mentre altri sono componenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d23c8-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="d23c8-108">In questa sezione vengono descritti i requisiti per i componenti specifici delle conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d23c8-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="d23c8-109">Per informazioni dettagliate sui requisiti del gateway PSTN (Mediation Server e Public Switched Telephone Network), vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) e [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d23c8-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="d23c8-110">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="d23c8-110">Hardware Requirements</span></span>

<span data-ttu-id="d23c8-111">Poiché Web Conferencing e A/V Conferencing sono collocati con Front End Server, i requisiti hardware del server sono uguali a quelli dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d23c8-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="d23c8-112">Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d23c8-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="d23c8-113">I componenti seguenti necessari per le conferenze telefoniche con accesso esterno dispongono anche degli stessi requisiti hardware dei Front End Server:</span><span class="sxs-lookup"><span data-stu-id="d23c8-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="d23c8-114">Servizio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d23c8-114">Application service</span></span>

  - <span data-ttu-id="d23c8-115">Applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="d23c8-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="d23c8-116">Applicazione Annuncio conferenza</span><span class="sxs-lookup"><span data-stu-id="d23c8-116">Conferencing Announcement application</span></span>

<span data-ttu-id="d23c8-117">I requisiti hardware per Front End Server sono gli stessi di molti altri ruoli del server in Lync Server 2013 sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d23c8-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="d23c8-118">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="d23c8-118">Software Requirements</span></span>

<span data-ttu-id="d23c8-119">Poiché Web Conferencing e A/V Conferencing sono collocati con Front End Server, i requisiti software del server sono uguali a quelli dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d23c8-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="d23c8-120">Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d23c8-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d23c8-121">Per le conferenze Web, Lync Server 2013 richiede anche Office Web Apps e il server Office Web Apps (in precedenza noto come server WAC) per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d23c8-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="d23c8-122">Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="d23c8-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="d23c8-123">Per le conferenze telefoniche con accesso esterno, il servizio applicazione, l'applicazione Operatore Conferenza e l'applicazione Annuncio conferenza dispongono degli stessi requisiti del sistema operativo dei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d23c8-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="d23c8-124">Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d23c8-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d23c8-125">Applicazione Operatore Conferenza e l'applicazione Annuncio conferenza richiedono l'installazione di Windows Media Format Runtime nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d23c8-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="d23c8-126">Runtime formato Windows Media è richiesto per la riproduzione dei file audio WMA (Windows Media Audio) usati per la musica in attesa, i nomi registrati e i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d23c8-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="d23c8-127">Ad eccezione di Windows Server 2012 e Windows Server 2012 R2, il runtime del formato Windows Media viene installato automaticamente come parte dell'esperienza desktop di Windows durante l'esecuzione del programma di installazione, ma potrebbe essere necessario riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d23c8-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="d23c8-128">È consigliabile pertanto installare il componente come parte dell'esperienza desktop di Windows prima di eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="d23c8-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="d23c8-129">Windows Server 2012 e Windows Server 2012 R2 richiedono Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="d23c8-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="d23c8-130">Requisiti delle porte per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="d23c8-p107">Nella tabella seguente vengono descritte le porte usate per le conferenze telefoniche con accesso esterno. Se si usa un servizio di bilanciamento del carico, assicurarsi che sia configurato per le porte usate dalle applicazioni che verranno eseguite nel pool.</span><span class="sxs-lookup"><span data-stu-id="d23c8-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="d23c8-133">Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="d23c8-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="d23c8-134">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d23c8-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d23c8-135">Tutte le istanze della stessa applicazione in un pool usano la stessa porta di attesa SIP.</span><span class="sxs-lookup"><span data-stu-id="d23c8-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="d23c8-136">Porte usate dalle conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d23c8-137">Numero di porta</span><span class="sxs-lookup"><span data-stu-id="d23c8-137">Port number</span></span></th>
<th><span data-ttu-id="d23c8-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d23c8-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d23c8-139">5072</span><span class="sxs-lookup"><span data-stu-id="d23c8-139">5072</span></span></p></td>
<td><p><span data-ttu-id="d23c8-140">Utilizzato dall'applicazione Operatore Conferenza per le richieste di attesa SIP</span><span class="sxs-lookup"><span data-stu-id="d23c8-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d23c8-141">5073</span><span class="sxs-lookup"><span data-stu-id="d23c8-141">5073</span></span></p></td>
<td><p><span data-ttu-id="d23c8-142">Utilizzato dall'applicazione Annuncio di conferenza per le richieste di attesa SIP</span><span class="sxs-lookup"><span data-stu-id="d23c8-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="d23c8-143">Client supportati per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="d23c8-144">È possibile usare il client seguente per pianificare conferenze locali che supportino la conferenza telefonica con accesso esterno:</span><span class="sxs-lookup"><span data-stu-id="d23c8-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="d23c8-145">Componente aggiuntivo per riunioni online per Lync 2013 (installato automaticamente quando si installa Lync 2013 o Attendee)</span><span class="sxs-lookup"><span data-stu-id="d23c8-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="d23c8-146">Requisiti della pagina Impostazioni conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="d23c8-147">La pagina Impostazioni conferenza telefonica con accesso esterno supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d23c8-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d23c8-148">Sono supportate le versioni a 32 bit e a 64 bit dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="d23c8-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="d23c8-149">Sistemi operativi e Web browser supportati</span><span class="sxs-lookup"><span data-stu-id="d23c8-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d23c8-150">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d23c8-150">Operating system</span></span></th>
<th><span data-ttu-id="d23c8-151">Web browser</span><span class="sxs-lookup"><span data-stu-id="d23c8-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d23c8-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d23c8-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="d23c8-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="d23c8-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="d23c8-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="d23c8-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="d23c8-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="d23c8-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d23c8-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d23c8-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="d23c8-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="d23c8-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="d23c8-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="d23c8-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="d23c8-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="d23c8-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d23c8-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="d23c8-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="d23c8-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="d23c8-161">Firefox</span></span></p>
<p><span data-ttu-id="d23c8-162">Safari</span><span class="sxs-lookup"><span data-stu-id="d23c8-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="d23c8-163">Requisiti dei file audio per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="d23c8-164">Lync Server 2013 non supporta la personalizzazione di istruzioni vocali e musica per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d23c8-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="d23c8-165">Tuttavia, se si ha un'esigenza aziendale complessa che richiede la modifica dei file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base, [come personalizzare i messaggi vocali o i file musicali per le conferenze telefoniche con accesso esterno in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="d23c8-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="d23c8-166">È inoltre possibile utilizzare [Microsoft Lync Server Conferencing Attendant Custom voice prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) Management Utility, che consente agli amministratori di sostituire le istruzioni vocali predefinite utilizzate quando un chiamante del telefono entra in una riunione di Lync con prompt personalizzati per fornire un'esperienza di ingresso per le riunioni diversa.</span><span class="sxs-lookup"><span data-stu-id="d23c8-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="d23c8-167">Le istruzioni vocali personalizzate possono essere installate su un server che esegue Lync Server 2010 o Lync Server 2013, Enterprise o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d23c8-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="d23c8-168">Applicazione per i servizi di conferenza e applicazione di annuncio di conferenza sono necessari i seguenti requisiti per la musica di attesa, il nome registrato e i file delle istruzioni audio:</span><span class="sxs-lookup"><span data-stu-id="d23c8-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="d23c8-169">Formato file WMA (Windows Media Audio)</span><span class="sxs-lookup"><span data-stu-id="d23c8-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="d23c8-170">Mono a 16 bit</span><span class="sxs-lookup"><span data-stu-id="d23c8-170">16-bit mono</span></span>

  - <span data-ttu-id="d23c8-171">CBR (Constant Bit Rate) a due passaggi 48 kbps</span><span class="sxs-lookup"><span data-stu-id="d23c8-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="d23c8-172">Livello parlato a -24 DB</span><span class="sxs-lookup"><span data-stu-id="d23c8-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="d23c8-173">Requisiti utente per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d23c8-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="d23c8-174">Gli utenti delle conferenze telefoniche con accesso esterno devono avere un numero di telefono univoco o un interno assegnato al loro account.</span><span class="sxs-lookup"><span data-stu-id="d23c8-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="d23c8-175">Questo requisito supporta l'autenticazione durante l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d23c8-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="d23c8-176">Gli utenti aziendali (ovvero gli utenti che dispongono di credenziali di servizi di dominio Active Directory e account di Lync Server all'interno dell'organizzazione) immettere il proprio numero di telefono (o estensione) e un PIN per accedere alle conferenze come un utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="d23c8-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

