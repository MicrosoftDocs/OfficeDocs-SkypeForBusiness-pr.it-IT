---
title: "Lync Server 2013: configurazione dell'invito alla riunione"
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
ms.openlocfilehash: 14e0614ecdaa73a886429e89618cac568d620938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="528d5-102">Configurazione dell'invito alla riunione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="528d5-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="528d5-103">_**Argomento Ultima modifica:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="528d5-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="528d5-104">È possibile personalizzare gli inviti alle riunioni inviati dal componente aggiuntivo riunione online per Lync 2013 includendo gli elementi facoltativi seguenti nel corpo dell'invito alla riunione:</span><span class="sxs-lookup"><span data-stu-id="528d5-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="528d5-105">**Logo dell'organizzazione** Aggiungere il logo dell'organizzazione agli inviti alla riunione usando l'opzione URL logo.</span><span class="sxs-lookup"><span data-stu-id="528d5-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="528d5-106">Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'immagine deve trovarsi in un URL disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="528d5-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="528d5-107">I formati di immagine supportati sono GIF e JPG.</span><span class="sxs-lookup"><span data-stu-id="528d5-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="528d5-108">Sebbene Lync Server 2013 memorizzi l'URL senza restrizioni di dimensione per l'immagine, per ottenere risultati ottimali, le dimensioni massime dell'immagine devono essere alte 30 pixel per 188 pixel di larghezza.</span><span class="sxs-lookup"><span data-stu-id="528d5-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="528d5-109">**Collegamento Guida o supporto personalizzato** Aggiungere un URL per la guida o il sito Web del team di supporto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="528d5-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="528d5-110">Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="528d5-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="528d5-111">La lunghezza massima dell'URL è di 1 KB.</span><span class="sxs-lookup"><span data-stu-id="528d5-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="528d5-112">**Testo della dichiarazione di non responsabilità legale** Aggiungere un URL per il testo legale o una dichiarazione di non responsabilità che verrà visualizzata in tutti gli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="528d5-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="528d5-113">Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="528d5-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="528d5-114">La lunghezza massima dell'URL è di 1 KB.</span><span class="sxs-lookup"><span data-stu-id="528d5-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="528d5-115">**Testo del piè** di pagina personalizzato Aggiungere il testo di cui verrà eseguito il rendering come piè di pagina personalizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="528d5-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="528d5-116">La lunghezza massima del testo che può essere aggiunta è 2 KB.</span><span class="sxs-lookup"><span data-stu-id="528d5-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="528d5-117">Le opzioni possono essere configurate tramite il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="528d5-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="528d5-118">**Per personalizzare l'invito alla riunione usando il pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="528d5-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="528d5-119">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="528d5-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="528d5-120">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="528d5-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="528d5-121">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="528d5-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="528d5-122">Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="528d5-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="528d5-123">Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="528d5-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="528d5-124">Per creare un criterio a livello di sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="528d5-124">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="528d5-125">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="528d5-125">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="528d5-126">Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="528d5-126">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="528d5-127">Per creare criteri a livello di pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="528d5-127">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="528d5-128">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="528d5-128">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="528d5-129">Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="528d5-129">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="528d5-130">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="528d5-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="528d5-131">Nel campo **URL logo** Digitare l'URL per l'immagine del logo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="528d5-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="528d5-132">Nel campo **URL della Guida** Digitare l'URL del sito della guida o del supporto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="528d5-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="528d5-133">Nel campo **testo legale** Digitare l'URL del testo legale o della dichiarazione di non responsabilità che si desidera includere negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="528d5-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="528d5-134">Nel campo **testo piè** di pagina personalizzato digitare il testo del piè di pagina, fino a 2 KB.</span><span class="sxs-lookup"><span data-stu-id="528d5-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="528d5-135">**Per personalizzare l'invito alla riunione tramite Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="528d5-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="528d5-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="528d5-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="528d5-137">Eseguire il cmdlet **New-CsMeetingConfiguration** o **Set-CsMeetingConfiguration** per creare o configurare le opzioni dell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="528d5-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="528d5-138">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="528d5-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

