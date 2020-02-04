---
title: 'Lync Server 2013: configurazione della visualizzazione raccolta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="3ed3d-102">Configurazione della visualizzazione raccolta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ed3d-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ed3d-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3ed3d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3ed3d-104">In Lync Server 2013 configurare le videoconferenze per la visualizzazione raccolta in criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="3ed3d-105">La visualizzazione raccolta è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="3ed3d-106">Se non si vuole consentire la visualizzazione raccolta o se si vuole consentire solo ad alcuni utenti, è necessario disattivare la caratteristica dei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="3ed3d-107">Quando il video di un partecipante a una conferenza non è disponibile, è possibile migliorare l'esperienza della visualizzazione raccolta degli utenti se si distribuiscono foto ad alta risoluzione, una nuova funzionalità in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="3ed3d-108">Le foto ad alta risoluzione rappresentano un'alternativa alle foto di contatto più piccole e limitate archiviate in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="3ed3d-109">Le foto ad alta risoluzione sono archiviate nella cassetta postale di Exchange 2013 dell'utente e, pertanto, richiedono l'integrazione di Lync Server 2013 con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="3ed3d-110">Per informazioni dettagliate, vedere l'articolo su Blog di NextHop "integrazione di [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Exchange 2013 e Lync Server 2013".</span><span class="sxs-lookup"><span data-stu-id="3ed3d-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ed3d-111">Il contenuto di ogni blog e il relativo URL sono soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="3ed3d-112">È possibile visualizzare o modificare i parametri della visualizzazione raccolta usando il pannello di controllo di Lync Server 2013 o usando uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed3d-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="3ed3d-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="3ed3d-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="3ed3d-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="3ed3d-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="3ed3d-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="3ed3d-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="3ed3d-116">Configurare la visualizzazione raccolta con le impostazioni dei criteri di conferenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed3d-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="3ed3d-117">**AllowMultiview**   questo parametro controlla se un utente può organizzare conferenze video per la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="3ed3d-118">Questo parametro si applica alle riunioni pianificate e ad-hoc create dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="3ed3d-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="3ed3d-119">Examples:</span></span>
    
      - <span data-ttu-id="3ed3d-120">Questo parametro è impostato su true per l'utente A, che è ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="3ed3d-121">Riunioni organizzate dall'utente A consentire agli utenti di partecipare e ricevere più flussi video.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="3ed3d-122">Questo parametro è impostato su false per l'utente B, che è ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="3ed3d-123">Le riunioni organizzate dall'utente B hanno un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="3ed3d-124">Questo parametro determina chi può organizzare riunioni che consentano più flussi video.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="3ed3d-125">I partecipanti alle riunioni che consentono a più flussi video possono o meno essere autorizzati a ricevere più flussi video, in base alle singole autorizzazioni (vedere la descrizione del parametro EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="3ed3d-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="3ed3d-126">**EnableMultiviewJoin**   questo parametro controlla se un partecipante a una riunione riceve l'esperienza video della visualizzazione raccolta in riunioni che lo consentono.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="3ed3d-127">Questo parametro controlla l'esperienza dell'utente in qualsiasi riunione in cui partecipa.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="3ed3d-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="3ed3d-128">Examples:</span></span>
    
      - <span data-ttu-id="3ed3d-129">Questo parametro è impostato su true per l'utente C. l'utente c può ricevere più flussi video durante la partecipazione a una riunione organizzata o avviata dall'utente A. l'utente C riceve un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipare a una riunione organizzata o avviata dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="3ed3d-130">Questo parametro è impostato su false per l'utente D. l'utente D riceve un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipa a una riunione organizzata dall'utente A o dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="3ed3d-131">La procedura seguente è un esempio di utilizzo di Lync Server Management Shell per abilitare la visualizzazione della raccolta di videoconferenze.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="3ed3d-132">Per modificare i criteri di conferenza per le videoconferenze per la visualizzazione raccolta</span><span class="sxs-lookup"><span data-stu-id="3ed3d-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="3ed3d-133">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3ed3d-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3ed3d-134">Nella riga di comando eseguire il cmdlet seguente per modificare i criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="3ed3d-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

