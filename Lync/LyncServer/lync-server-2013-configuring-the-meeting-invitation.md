---
title: "Lync Server 2013: configurazione dell'invito alla riunione"
description: "Lync Server 2013: configurazione dell'invito alla riunione."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64438d7a451cb794c125207fa594e1c00b534c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564332"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="c0792-103">Configurazione dell'invito alla riunione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0792-103">Configuring the meeting invitation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0792-104">_**Ultimo argomento modificato:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="c0792-104">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="c0792-105">È possibile personalizzare gli inviti alle riunioni inviati dal componente aggiuntivo per riunioni online per Lync 2013 includendo i seguenti elementi facoltativi nel corpo dell'invito alla riunione:</span><span class="sxs-lookup"><span data-stu-id="c0792-105">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="c0792-106">**Logo dell'organizzazione** Aggiungere il logo dell'organizzazione agli inviti alle riunioni utilizzando l'opzione URL logo.</span><span class="sxs-lookup"><span data-stu-id="c0792-106">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="c0792-107">Se gli inviti alle riunioni vengono inviati a utenti esterni all'organizzazione, l'immagine deve trovarsi in un URL disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="c0792-107">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="c0792-108">I formati di immagine supportati sono GIF e JPG.</span><span class="sxs-lookup"><span data-stu-id="c0792-108">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="c0792-109">Anche se Lync Server 2013 archivia l'URL senza restrizioni di dimensione per l'immagine, per ottenere risultati ottimali, le dimensioni massime dell'immagine devono essere alte 30 pixel di 188 pixel di larghezza.</span><span class="sxs-lookup"><span data-stu-id="c0792-109">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="c0792-110">**Un collegamento di supporto o assistenza personalizzato** Aggiungere un URL per la guida o il sito Web del team di supporto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0792-110">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="c0792-111">Se gli inviti alle riunioni verranno inviati agli utenti esterni all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="c0792-111">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="c0792-112">La lunghezza massima dell'URL è pari a 1 KB.</span><span class="sxs-lookup"><span data-stu-id="c0792-112">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="c0792-113">**Testo della dichiarazione di non responsabilità legale** Aggiungere un URL per il testo legale o una dichiarazione di non responsabilità che verrà visualizzata in tutti gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c0792-113">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="c0792-114">Se gli inviti alle riunioni verranno inviati agli utenti esterni all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="c0792-114">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="c0792-115">La lunghezza massima dell'URL è pari a 1 KB.</span><span class="sxs-lookup"><span data-stu-id="c0792-115">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="c0792-116">**Testo del piè** di pagina personalizzato Aggiungere del testo di cui verrà eseguito il rendering come piè di pagina personalizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="c0792-116">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="c0792-117">La lunghezza massima del testo che è possibile aggiungere è 2 KB.</span><span class="sxs-lookup"><span data-stu-id="c0792-117">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="c0792-118">È possibile configurare queste opzioni utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c0792-118">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="c0792-119">**Per personalizzare l'invito alla riunione utilizzando il pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="c0792-119">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="c0792-120">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0792-120">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c0792-121">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0792-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c0792-122">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0792-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c0792-123">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="c0792-123">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="c0792-124">Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0792-124">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c0792-p106">Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0792-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c0792-p107">Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0792-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="c0792-131">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0792-131">Do any of the following:</span></span>
    
      - <span data-ttu-id="c0792-132">Nel campo **URL logo** Digitare l'URL dell'immagine del logo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0792-132">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="c0792-133">Nel campo **URL della Guida** Digitare l'URL del sito di supporto o della Guida dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0792-133">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="c0792-134">Nel campo **testo legale** Digitare l'URL del testo legale o della dichiarazione di non responsabilità che si desidera includere negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c0792-134">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="c0792-135">Nel campo di **testo del piè** di pagina personalizzato digitare il testo del piè di pagina, fino a 2 KB.</span><span class="sxs-lookup"><span data-stu-id="c0792-135">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="c0792-136">**Per personalizzare l'invito alla riunione mediante Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="c0792-136">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="c0792-137">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c0792-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c0792-138">Eseguire il cmdlet **New-CsMeetingConfiguration** o **Set-CsMeetingConfiguration** per creare o configurare le opzioni di invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c0792-138">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="c0792-139">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c0792-139">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

