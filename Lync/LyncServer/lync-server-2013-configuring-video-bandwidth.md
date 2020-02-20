---
title: 'Lync Server 2013: configurazione della larghezza di banda video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1dfd2e8879776733e6ca6fbd8d6024533ef622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="2a03e-102">Configurazione della larghezza di banda video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a03e-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a03e-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2a03e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2a03e-104">Lync Server 2013 include diverse impostazioni per la gestione del video per le chiamate a due o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="2a03e-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="2a03e-105">Quando si distribuisce Lync Server 2013, è necessario valutare se le impostazioni predefinite sono appropriate per l'organizzazione e modificarle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2a03e-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="2a03e-p102">I parametri descritti in questa sezione si applicano sia alle chiamate con due partecipanti che alle conferenze con più partecipanti. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a03e-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="2a03e-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="2a03e-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="2a03e-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="2a03e-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="2a03e-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="2a03e-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="2a03e-111">Verificare le impostazioni seguenti nei criteri conferenza:</span><span class="sxs-lookup"><span data-stu-id="2a03e-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="2a03e-112">**VideoBitRateKb**   questa impostazione consente di specificare la frequenza di bit video massima in kilobit al secondo (Kbps) utilizzata per il video inviato da un utente.</span><span class="sxs-lookup"><span data-stu-id="2a03e-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="2a03e-113">Il valore predefinito è 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="2a03e-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="2a03e-114">I valori validi sono compresi tra 0 e 50000.</span><span class="sxs-lookup"><span data-stu-id="2a03e-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="2a03e-115">Questa impostazione si applica separatamente al video principale e alla panoramica.</span><span class="sxs-lookup"><span data-stu-id="2a03e-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="2a03e-116">Esempio: se si specifica 2000 kbps, Lync Server può inviare 2000 kbps per il flusso video principale e 2000 kbps per il flusso video panoramico.</span><span class="sxs-lookup"><span data-stu-id="2a03e-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a03e-117">La larghezza di banda massima della rete video per un endpoint Lync 2013 è 8000 kbps per il video principale e 2500 kbps per il video panoramico.</span><span class="sxs-lookup"><span data-stu-id="2a03e-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="2a03e-118">Questi valori massimi vengono raggiunti solo nel caso di invio o ricezione di più video.</span><span class="sxs-lookup"><span data-stu-id="2a03e-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="2a03e-119">Per informazioni dettagliate, vedere la sezione "utilizzo della rete per il traffico multimediale" in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2a03e-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="2a03e-120">In questa sezione sono elencati i valori massimi e tipici della larghezza di base dei flussi video per tutte le risoluzioni supportate.</span><span class="sxs-lookup"><span data-stu-id="2a03e-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="2a03e-121">**TotalReceiveVideoBitRateKb**   questa impostazione, che è una novità di Lync Server 2013, specifica il bitrate massimo consentito (in kilobit al secondo) per tutti i flussi video ricevuti da un client.</span><span class="sxs-lookup"><span data-stu-id="2a03e-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="2a03e-122">In altre parole, specifica il totale combinato per tutti i flussi video, ad eccezione di quelli della panoramica, che un client può ricevere.</span><span class="sxs-lookup"><span data-stu-id="2a03e-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="2a03e-123">Se si specifica il valore 1500 kbps, un client può ad esempio ricevere fino a 1500 kbps di video, in cui possono essere compresi uno o più flussi video.</span><span class="sxs-lookup"><span data-stu-id="2a03e-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="2a03e-124">Questa impostazione si applica solo ai client Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a03e-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="2a03e-p106">Il valore predefinito di **TotalReceiveVideoBitRateKb** è 50000 kbps. Se l'impostazione **EnableMultiviewJoin** della visualizzazione Raccolta corrisponde a True, **TotalReceiveVideoBitRateKb** non deve essere impostato al di sotto di 420 kbps. Se l'impostazione **EnableMultiviewJoin** relativa alla visualizzazione Raccolta corrisponde a False, **TotalReceiveVideoBitRateKb** non deve essere impostato al di sotto di 100 kbps. Se **EnableMultiviewJoin** è impostato su True e il valore impostato è al di sotto di 420 kbps, i valori assumeranno per impostazione predefinita quello della soglia. Il valore della soglia impedisce un'errata configurazione accidentale che potrebbe determinare un'esperienza scarsa per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a03e-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a03e-130">Per informazioni dettagliate sull'impostazione <STRONG>EnableMultiviewJoin</STRONG> , vedere <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2a03e-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="2a03e-131">**MaxVideoConferencingResolution**   questo parametro non è più utilizzato per i client di Lync Server 2013 nelle conferenze di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a03e-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="2a03e-132">Le conferenze di Lync Server 2013 utilizzano i controlli di bit rate descritti in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2a03e-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="2a03e-133">Questa impostazione è ancora utilizzata per i client legacy che partecipano a una conferenza di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a03e-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="2a03e-134">Questo parametro determina la risoluzione massima consentita per i client legacy nelle conferenze organizzate dagli utenti che si trovano in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a03e-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="2a03e-135">Vale a dire che i client legacy vengono considerati come nelle versioni precedenti di Lync Server o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="2a03e-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="2a03e-p108">Oltre alle impostazioni dei criteri conferenza che si applicano agli utenti, prendere in considerazione l'uso delle impostazioni di configurazione multimediale. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a03e-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="2a03e-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="2a03e-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="2a03e-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="2a03e-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="2a03e-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="2a03e-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="2a03e-141">Verificare l'impostazione seguente:</span><span class="sxs-lookup"><span data-stu-id="2a03e-141">Verify the following setting:</span></span>

  - <span data-ttu-id="2a03e-142">**MaxVideoRateAllowed**   questa impostazione per pool specifica la velocità massima di trasferimento dei segnali video negli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="2a03e-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="2a03e-143">Si applica solo alle versioni precedenti dei client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a03e-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a03e-144">I client di Lync Server 2013 ignorano questa impostazione e utilizzano invece l'impostazione TotalReceiveVideoBitRateKb nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2a03e-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="2a03e-p110">Il valore predefinito è HD720P. I valori validi sono HD720p15M, VGA600K e CIF250K.</span><span class="sxs-lookup"><span data-stu-id="2a03e-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="2a03e-147">Esempio: se si specifica il valore 1500 kbps, tutti i client legacy del pool possono ricevere fino a 1500 kbps di video in conferenze con due o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="2a03e-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="2a03e-148">Nelle procedure seguenti sono riportati alcuni esempi di utilizzo di Lync Server Management Shell per modificare le impostazioni descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2a03e-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="2a03e-149">Per modificare i criteri conferenza per le impostazioni video</span><span class="sxs-lookup"><span data-stu-id="2a03e-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="2a03e-150">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a03e-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a03e-151">Alla riga di comando eseguire il cmdlet seguente per modificare i criteri conferenza:</span><span class="sxs-lookup"><span data-stu-id="2a03e-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="2a03e-152">Per modificare la configurazione multimediale per i client legacy</span><span class="sxs-lookup"><span data-stu-id="2a03e-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="2a03e-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a03e-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a03e-154">Alla riga di comando eseguire il cmdlet seguente per modificare la configurazione multimediale:</span><span class="sxs-lookup"><span data-stu-id="2a03e-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

