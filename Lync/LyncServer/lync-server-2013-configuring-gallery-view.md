---
title: 'Lync Server 2013: configurazione della visualizzazione raccolta'
description: 'Lync Server 2013: configurazione della visualizzazione raccolta.'
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
ms.openlocfilehash: 2aec2f1e3c7bff9a3736f40584a29880978b9daa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575922"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="5f184-103">Configurazione della visualizzazione raccolta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f184-103">Configuring Gallery View in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f184-104">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5f184-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5f184-105">In Lync Server 2013, è possibile configurare le conferenze video della visualizzazione raccolta nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5f184-105">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="5f184-106">La visualizzazione Raccolta è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5f184-106">Gallery View is turned on by default.</span></span> <span data-ttu-id="5f184-107">Se non si vuole consentire la visualizzazione Raccolta o la si vuole consentire solo per alcuni utenti, è necessario disattivarla nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5f184-107">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="5f184-108">Quando il video di un partecipante a una conferenza non è disponibile, è possibile migliorare l'esperienza di visualizzazione della raccolta degli utenti se si distribuiscono foto ad alta risoluzione, una nuova funzionalità di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f184-108">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="5f184-109">Le foto ad alta risoluzione offrono un'alternativa alle foto dei contatti a risoluzione limitata più piccole e limitate archiviate in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f184-109">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="5f184-110">Le foto ad alta risoluzione sono archiviate nella cassetta postale di Exchange 2013 di un utente e, pertanto, richiedono l'integrazione di Lync Server 2013 con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5f184-110">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="5f184-111">Per informazioni dettagliate, vedere l'articolo del Blog di NextHop "integrazione di Exchange 2013 e Lync Server 2013" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) .</span><span class="sxs-lookup"><span data-stu-id="5f184-111">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f184-112">Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="5f184-112">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="5f184-113">È possibile visualizzare o modificare i parametri della visualizzazione raccolta mediante il pannello di controllo di Lync Server 2013 oppure utilizzando uno dei seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5f184-113">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="5f184-114">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="5f184-114">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="5f184-115">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="5f184-115">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="5f184-116">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="5f184-116">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="5f184-117">Configurare la visualizzazione Raccolta con le impostazioni dei criteri di conferenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f184-117">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="5f184-118">**AllowMultiview**     Questo parametro consente di controllare se un utente può organizzare conferenze video della visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="5f184-118">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="5f184-119">Si applica a riunioni programmate e ad hoc create dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5f184-119">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="5f184-120">Esempi:</span><span class="sxs-lookup"><span data-stu-id="5f184-120">Examples:</span></span>
    
      - <span data-ttu-id="5f184-121">Questo parametro è impostato su true per l'utente A, che è ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f184-121">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="5f184-122">Le riunioni organizzate dall'utente A consentono agli utenti di partecipare e ricevere più flussi video.</span><span class="sxs-lookup"><span data-stu-id="5f184-122">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="5f184-123">Questo parametro è impostato su false per l'utente B, che è ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f184-123">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="5f184-124">Le riunioni organizzate dall'utente B dispongono di un unico flusso video analogo all'esperienza di conferenza video fornita da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5f184-124">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="5f184-p106">Questo parametro determina chi può organizzare riunioni con più flussi video. I partecipanti di riunioni che consentono più flussi video possono o non possono ricevere più flussi video, a seconda delle autorizzazioni individuali. Vedere la descrizione del parametro EnableMultiviewJoin.</span><span class="sxs-lookup"><span data-stu-id="5f184-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="5f184-127">**EnableMultiviewJoin**     Questo parametro consente di controllare se un partecipante a una riunione riceve la visualizzazione della raccolta video in riunioni che lo consentono.</span><span class="sxs-lookup"><span data-stu-id="5f184-127">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="5f184-128">Il parametro controlla l'esperienza utente per tutte le riunioni a cui gli utenti partecipano.</span><span class="sxs-lookup"><span data-stu-id="5f184-128">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="5f184-129">Esempi:</span><span class="sxs-lookup"><span data-stu-id="5f184-129">Examples:</span></span>
    
      - <span data-ttu-id="5f184-130">Questo parametro è impostato su true per l'utente C. gli utenti possono ricevere più flussi video quando partecipano a una riunione organizzata o avviata dall'utente A. User C riceve un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipa a una riunione organizzata o avviata dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="5f184-130">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="5f184-131">Questo parametro è impostato su false per l'utente D. utente D riceve un singolo flusso video analogo all'esperienza di conferenza video fornita da Lync Server 2010 quando si partecipa a una riunione organizzata dall'utente A o dall'utente B.</span><span class="sxs-lookup"><span data-stu-id="5f184-131">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="5f184-132">La procedura seguente è un esempio di utilizzo di Lync Server Management Shell per abilitare le conferenze video della visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="5f184-132">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="5f184-133">Per modificare i criteri di conferenza per le conferenze video della visualizzazione Raccolta</span><span class="sxs-lookup"><span data-stu-id="5f184-133">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="5f184-134">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5f184-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f184-135">Per modificare i criteri di conferenza, dalla riga di comando eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5f184-135">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

