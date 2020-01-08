---
title: 'Lync Server 2013: configurazione della larghezza di banda video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="8000c-102">Configurazione della larghezza di banda video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8000c-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8000c-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8000c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8000c-104">Lync Server 2013 include diverse impostazioni per la gestione di video per le chiamate a due parti e conferenze multiparte.</span><span class="sxs-lookup"><span data-stu-id="8000c-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="8000c-105">Quando si distribuisce Lync Server 2013, è necessario valutare se le impostazioni predefinite sono appropriate per l'organizzazione e modificarle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8000c-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="8000c-106">I parametri descritti in questa sezione sono validi sia per le chiamate a due parti che per le conferenze multiparte.</span><span class="sxs-lookup"><span data-stu-id="8000c-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="8000c-107">Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8000c-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="8000c-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="8000c-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="8000c-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="8000c-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="8000c-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="8000c-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="8000c-111">Verificare le impostazioni seguenti nei criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="8000c-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="8000c-112">**VideoBitRateKb**   questa impostazione specifica la velocità in bit video massima in kilobit al secondo (Kbps) usata per il video inviato da un utente.</span><span class="sxs-lookup"><span data-stu-id="8000c-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="8000c-113">Il valore predefinito è 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="8000c-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="8000c-114">I valori validi sono compresi tra 0 e 50000.</span><span class="sxs-lookup"><span data-stu-id="8000c-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="8000c-115">Questa impostazione si applica separatamente al video principale e al video panoramico.</span><span class="sxs-lookup"><span data-stu-id="8000c-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="8000c-116">Esempio: se si specifica 2000 kbps, Lync Server può inviare 2000 kbps per il flusso video principale e 2000 kbps per il flusso video panoramico.</span><span class="sxs-lookup"><span data-stu-id="8000c-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8000c-117">La larghezza di banda massima della rete video per un endpoint di Lync 2013 è 8000 kbps per il video principale e 2500 kbps per il video panoramico.</span><span class="sxs-lookup"><span data-stu-id="8000c-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="8000c-118">Questi valori massimi vengono raggiunti solo se vengono ricevuti o inviati più video.</span><span class="sxs-lookup"><span data-stu-id="8000c-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="8000c-119">Per informazioni dettagliate, vedere la sezione "utilizzo della rete traffico multimediale" nei <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8000c-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="8000c-120">Questa sezione elenca la larghezza di banda del flusso video massima e tipica per tutte le risoluzioni supportate.</span><span class="sxs-lookup"><span data-stu-id="8000c-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="8000c-121">**TotalReceiveVideoBitRateKb**   questa impostazione, che è una novità di Lync Server 2013, specifica il bitrate massimo consentito (in kilobit al secondo) per tutti i flussi video ricevuti da un client.</span><span class="sxs-lookup"><span data-stu-id="8000c-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="8000c-122">Questo significa che specifica il totale combinato per tutti i flussi video, ad eccezione dei flussi video panoramici, che un client può ricevere.</span><span class="sxs-lookup"><span data-stu-id="8000c-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="8000c-123">Se ad esempio specifichi 1500 Kbps, un client può ricevere fino a 1500 kbps di video, che possono essere costituiti da più flussi video o da un singolo flusso video.</span><span class="sxs-lookup"><span data-stu-id="8000c-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="8000c-124">Questa impostazione si applica solo ai client di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8000c-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="8000c-125">Il valore predefinito per **TotalReceiveVideoBitRateKb** è 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="8000c-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="8000c-126">Se l'impostazione **EnableMultiviewJoin** per la visualizzazione raccolta è impostata su true, **TotalReceiveVideoBitRateKb** non deve essere impostato sotto 420 kbps.</span><span class="sxs-lookup"><span data-stu-id="8000c-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="8000c-127">Se l'impostazione **EnableMultiviewJoin** per la visualizzazione raccolta è impostata su false, **TotalReceiveVideoBitRateKb** non deve essere impostato sotto 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="8000c-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="8000c-128">Se **EnableMultiviewJoin** è impostato su true e si imposta il valore sotto 420 Kbps, i valori verranno impostati automaticamente sul valore soglia.</span><span class="sxs-lookup"><span data-stu-id="8000c-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="8000c-129">Questa soglia consente di evitare la disconfigurazione accidentale che potrebbe causare un'esperienza utente insufficiente.</span><span class="sxs-lookup"><span data-stu-id="8000c-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8000c-130">Per informazioni dettagliate sull'impostazione di <STRONG>EnableMultiviewJoin</STRONG> , vedere <A href="lync-server-2013-configuring-gallery-view.md">configurazione della visualizzazione raccolta in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8000c-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="8000c-131">**MaxVideoConferencingResolution**   questo parametro non viene più usato per i client di Lync Server 2013 nelle conferenze di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8000c-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="8000c-132">Le conferenze di Lync Server 2013 usano i controlli di velocità in bit descritti in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8000c-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="8000c-133">Questa impostazione viene ancora usata per i client legacy che partecipano a una conferenza di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8000c-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="8000c-134">Questo parametro determina la risoluzione massima consentita per i client legacy nelle conferenze organizzate dagli utenti residenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8000c-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="8000c-135">I client legacy vengono trattati nello stesso modo in cui si trovavano nelle versioni precedenti di Lync Server o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="8000c-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="8000c-136">Oltre alle impostazioni dei criteri di conferenza che si applicano agli utenti, valutare le impostazioni di configurazione multimediale.</span><span class="sxs-lookup"><span data-stu-id="8000c-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="8000c-137">Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8000c-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="8000c-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="8000c-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="8000c-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="8000c-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="8000c-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="8000c-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="8000c-141">Verificare l'impostazione seguente:</span><span class="sxs-lookup"><span data-stu-id="8000c-141">Verify the following setting:</span></span>

  - <span data-ttu-id="8000c-142">**MaxVideoRateAllowed**   questa impostazione per pool specifica la frequenza massima in cui i segnali video verranno trasferiti agli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="8000c-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="8000c-143">Si applica solo alle versioni precedenti dei client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8000c-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8000c-144">I client di Lync Server 2013 ignorano questa impostazione e usano invece l'impostazione TotalReceiveVideoBitRateKb nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="8000c-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="8000c-145">Il valore predefinito è HD720P.</span><span class="sxs-lookup"><span data-stu-id="8000c-145">The default value is HD720P.</span></span> <span data-ttu-id="8000c-146">I valori validi sono HD720p15M, VGA600K e CIF250K.</span><span class="sxs-lookup"><span data-stu-id="8000c-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="8000c-147">Esempio: se si specifica 1500 Kbps, tutti i client legacy del pool possono ricevere fino a 1500 kbps di video in conferenze a due o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="8000c-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="8000c-148">Le procedure seguenti sono esempi di utilizzo di Lync Server Management Shell per modificare le impostazioni descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8000c-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="8000c-149">Per modificare i criteri di conferenza per le impostazioni video</span><span class="sxs-lookup"><span data-stu-id="8000c-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="8000c-150">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8000c-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8000c-151">Nella riga di comando eseguire il cmdlet seguente per modificare i criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="8000c-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="8000c-152">Per modificare la configurazione multimediale per i client legacy</span><span class="sxs-lookup"><span data-stu-id="8000c-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="8000c-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8000c-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8000c-154">Nella riga di comando eseguire il cmdlet seguente per modificare la configurazione multimediale:</span><span class="sxs-lookup"><span data-stu-id="8000c-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

