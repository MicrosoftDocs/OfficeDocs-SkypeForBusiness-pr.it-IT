---
title: 'Lync Server 2013: Requisiti tecnici per le conferenze'
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
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="17c37-102">Requisiti tecnici per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17c37-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c37-103">_**Argomento Ultima modifica:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="17c37-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="17c37-104">Per Lync Server 2013, i servizi di conferenza telefonica con accesso esterno, le conferenze A/V, i servizi di messaggistica istantanea (IM) e le funzionalità di conferenza Web vengono sempre eseguiti nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="17c37-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="17c37-105">Questa sezione descrive i requisiti hardware e software per questi server, insieme alla collocazione supportata.</span><span class="sxs-lookup"><span data-stu-id="17c37-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="17c37-106">I servizi di conferenza telefonica con accesso esterno sono una funzionalità che include una vasta gamma di componenti.</span><span class="sxs-lookup"><span data-stu-id="17c37-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="17c37-107">Alcuni componenti sono specifici per i servizi di conferenza telefonica con accesso esterno e alcuni sono componenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="17c37-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="17c37-108">Questa sezione descrive i requisiti per i componenti specifici dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="17c37-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="17c37-109">Per informazioni dettagliate sui requisiti del gateway di Mediation Server e PSTN (Public Switched Telephone Network), vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md) e [topologie per Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="17c37-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="17c37-110">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="17c37-110">Hardware Requirements</span></span>

<span data-ttu-id="17c37-111">Poiché i servizi di conferenza Web e le conferenze A/V sono collocati con il front end server, i requisiti hardware del server sono gli stessi per i server front-end.</span><span class="sxs-lookup"><span data-stu-id="17c37-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="17c37-112">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="17c37-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="17c37-113">I componenti seguenti necessari per i servizi di conferenza telefonica con accesso esterno hanno anche gli stessi requisiti hardware dei server front-end:</span><span class="sxs-lookup"><span data-stu-id="17c37-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="17c37-114">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="17c37-114">Application service</span></span>

  - <span data-ttu-id="17c37-115">Applicazione Supervisore conferenza</span><span class="sxs-lookup"><span data-stu-id="17c37-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="17c37-116">Applicazione per l'annuncio di conferenza</span><span class="sxs-lookup"><span data-stu-id="17c37-116">Conferencing Announcement application</span></span>

<span data-ttu-id="17c37-117">I requisiti hardware per il server front-end sono gli stessi che per molti altri ruoli del server in Lync Server 2013 sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="17c37-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="17c37-118">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="17c37-118">Software Requirements</span></span>

<span data-ttu-id="17c37-119">Poiché i servizi di conferenza Web e le conferenze A/V sono collocati con il front end server, i requisiti software server sono gli stessi per i server front-end.</span><span class="sxs-lookup"><span data-stu-id="17c37-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="17c37-120">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="17c37-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="17c37-121">Per le conferenze Web, Lync Server 2013 richiede anche Office Web Apps e il server Office Web Apps (in precedenza noto come server WAC) per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="17c37-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="17c37-122">Per informazioni dettagliate, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="17c37-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="17c37-123">Per i servizi di conferenza telefonica con accesso esterno, il servizio applicazione, l'applicazione di conferenza e l'applicazione di annunci di conferenza hanno gli stessi requisiti di sistema operativo di front end server.</span><span class="sxs-lookup"><span data-stu-id="17c37-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="17c37-124">Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="17c37-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="17c37-125">L'applicazione per i servizi di conferenza e l'applicazione per le conferenze richiede che Windows Media Format Runtime sia installato nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="17c37-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="17c37-126">Windows Media Format Runtime è necessario per riprodurre file di Windows Media Audio (WMA) usati per la musica in attesa, i nomi registrati e le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="17c37-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="17c37-127">Ad eccezione di Windows Server 2012 e Windows Server 2012 R2, Windows Media Format Runtime viene installato automaticamente come parte dell'esperienza desktop di Windows quando si esegue il programma di installazione, ma potrebbe essere necessario riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="17c37-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="17c37-128">Per questo motivo, ti consigliamo di installare come parte dell'esperienza desktop di Windows, che include Windows Media Format Runtime prima di eseguire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="17c37-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="17c37-129">Windows Server 2012 e Windows Server 2012 R2 richiede Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="17c37-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="17c37-130">Requisiti della porta per i servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="17c37-131">La tabella seguente descrive le porte usate dai servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="17c37-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="17c37-132">Se si usa un bilanciamento del carico, verificare che il bilanciamento del carico sia configurato per le porte usate da qualsiasi applicazione che verrà eseguita nel pool.</span><span class="sxs-lookup"><span data-stu-id="17c37-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="17c37-133">Queste porte sono impostazioni predefinite che è possibile modificare usando il cmdlet **Set-CsApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="17c37-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="17c37-134">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="17c37-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17c37-135">Tutte le istanze della stessa applicazione in un pool usano la stessa porta di ascolto SIP.</span><span class="sxs-lookup"><span data-stu-id="17c37-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="17c37-136">Porte usate dai servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17c37-137">Numero di porta</span><span class="sxs-lookup"><span data-stu-id="17c37-137">Port number</span></span></th>
<th><span data-ttu-id="17c37-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17c37-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17c37-139">5072</span><span class="sxs-lookup"><span data-stu-id="17c37-139">5072</span></span></p></td>
<td><p><span data-ttu-id="17c37-140">Usato dall'applicazione di assistente conferenza per le richieste di ascolto SIP</span><span class="sxs-lookup"><span data-stu-id="17c37-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c37-141">5073</span><span class="sxs-lookup"><span data-stu-id="17c37-141">5073</span></span></p></td>
<td><p><span data-ttu-id="17c37-142">Usato dall'applicazione di annuncio per conferenze per le richieste di ascolto SIP</span><span class="sxs-lookup"><span data-stu-id="17c37-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="17c37-143">Client supportati per i servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="17c37-144">Per pianificare conferenze locali che supportano l'accesso esterno, è possibile usare il client seguente:</span><span class="sxs-lookup"><span data-stu-id="17c37-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="17c37-145">Componente aggiuntivo riunione online per Lync 2013 (installato automaticamente durante l'installazione di Lync 2013 o partecipante)</span><span class="sxs-lookup"><span data-stu-id="17c37-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="17c37-146">Requisiti della pagina Impostazioni conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="17c37-147">La pagina delle impostazioni per i servizi di conferenza telefonica con accesso esterno supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="17c37-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17c37-148">sono supportate le versioni di 32 bit e 64 bit dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="17c37-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="17c37-149">Sistemi operativi e browser Web supportati</span><span class="sxs-lookup"><span data-stu-id="17c37-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17c37-150">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="17c37-150">Operating system</span></span></th>
<th><span data-ttu-id="17c37-151">Web browser</span><span class="sxs-lookup"><span data-stu-id="17c37-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17c37-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="17c37-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="17c37-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="17c37-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="17c37-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="17c37-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="17c37-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="17c37-155">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="17c37-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="17c37-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="17c37-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="17c37-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="17c37-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="17c37-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="17c37-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="17c37-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c37-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="17c37-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="17c37-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="17c37-161">Firefox</span></span></p>
<p><span data-ttu-id="17c37-162">Safari</span><span class="sxs-lookup"><span data-stu-id="17c37-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="17c37-163">Requisiti per i file audio per i servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="17c37-164">Lync Server 2013 non supporta la personalizzazione delle istruzioni vocali e della musica per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="17c37-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="17c37-165">Tuttavia, se si ha bisogno di cambiare i file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base [su come personalizzare le richieste vocali o i file musicali per i servizi di conferenza telefonica con accesso esterno in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="17c37-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="17c37-166">È anche possibile usare l'utilità per la gestione delle [richieste vocali personalizzate di Microsoft Lync Server Conferencing](http://go.microsoft.com/fwlink/p/?linkid=396880) , che consente agli amministratori di sostituire le richieste vocali predefinite usate quando un chiamante di un telefono entra in una riunione Lync con istruzioni personalizzate per creare un'esperienza di partecipazione a una riunione diversa.</span><span class="sxs-lookup"><span data-stu-id="17c37-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="17c37-167">Le istruzioni vocali personalizzate possono essere installate in un server in cui è in uso Lync Server 2010 o Lync Server 2013, Enterprise o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="17c37-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="17c37-168">Applicazione per i servizi di conferenza e l'applicazione di annuncio di conferenza sono i requisiti seguenti per la musica in attesa, il nome registrato e i file di prompt audio:</span><span class="sxs-lookup"><span data-stu-id="17c37-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="17c37-169">Formato di file di Windows Media Audio (WMA)</span><span class="sxs-lookup"><span data-stu-id="17c37-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="17c37-170">16 bit mono</span><span class="sxs-lookup"><span data-stu-id="17c37-170">16-bit mono</span></span>

  - <span data-ttu-id="17c37-171">CBR a due passaggi di 48 kbps (velocità in bit costante)</span><span class="sxs-lookup"><span data-stu-id="17c37-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="17c37-172">Livello di riconoscimento vocale at-24DB</span><span class="sxs-lookup"><span data-stu-id="17c37-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="17c37-173">Requisiti degli utenti per i servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="17c37-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="17c37-174">Gli utenti dei servizi di conferenza telefonica con accesso esterno devono avere un numero o un'estensione di telefono univoco assegnati al proprio account.</span><span class="sxs-lookup"><span data-stu-id="17c37-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="17c37-175">Questo requisito supporta l'autenticazione durante i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="17c37-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="17c37-176">Gli utenti aziendali, ovvero gli utenti che hanno credenziali di servizi di dominio Active Directory e gli account di Lync Server all'interno dell'organizzazione, immettono il proprio numero di telefono (o estensione) e un PIN per accedere alle conferenze come utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="17c37-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

