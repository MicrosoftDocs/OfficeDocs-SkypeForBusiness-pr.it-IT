---
title: 'Lync Server 2013: modificare o configurare URL semplici'
description: 'Lync Server 2013: modificare o configurare URL semplici.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551632"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="7b3cb-103">Modificare o configurare URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b3cb-103">Edit or configure simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b3cb-104">_**Ultimo argomento modificato:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="7b3cb-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="7b3cb-p101">Per questa procedura non è necessaria l'appartenenza a un gruppo di amministratori locali o di dominio privilegiato, ma è consigliabile accedere a un computer come utente standard.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="7b3cb-107">Lync Server 2013 utilizza URL semplici per indirizzare le chiamate interne ed esterne ai servizi nel front end server o nel Director, se ne è stata distribuita una.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-107">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="7b3cb-108">Per ulteriori informazioni sugli URL semplici, vedere [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-108">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="7b3cb-109">È possibile selezionare il formato per gli URL semplici da diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-109">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="7b3cb-110">Per informazioni dettagliate su queste opzioni, vedere [DNS requirements for Simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-110">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="7b3cb-111">Per impostazione predefinita, gli URL semplici verranno configurati nel formato (ad esempio, l'URL semplice in accesso esterno): https://dialin .\<SIP Domain\></span><span class="sxs-lookup"><span data-stu-id="7b3cb-111">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="7b3cb-112">Per configurare gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="7b3cb-112">To configure simple URLs</span></span>

1.  <span data-ttu-id="7b3cb-113">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-113">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7b3cb-114">Nel riquadro **URL semplici** selezionare URL di **accesso telefonico:** (chiamata in ingresso) o URL di **riunione:** (Meet) per modificare e quindi fare clic su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-114">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="7b3cb-115">Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-115">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="7b3cb-116">Nell'esempio riportato di seguito è stato modificato l'URL di accesso esterno in https://pool01.contoso.net/dialin .</span><span class="sxs-lookup"><span data-stu-id="7b3cb-116">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="7b3cb-117">Se necessario, modificare l'URL riunione eseguendo la stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-117">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="7b3cb-118">Per definire l'URL semplice facoltativo per l'accesso amministrativo</span><span class="sxs-lookup"><span data-stu-id="7b3cb-118">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="7b3cb-119">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-119">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7b3cb-120">Nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-120">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7b3cb-121">È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-121">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="7b3cb-122">L'opzione più semplice è <STRONG> https://admin .</STRONG> &lt; dominio &gt; .</span><span class="sxs-lookup"><span data-stu-id="7b3cb-122">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7b3cb-123">Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario considerare quali modifiche influiscono sui record DNS (Domain Name System) e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-123">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="7b3cb-124">Se la modifica influisce sulla base di un URL semplice, sarà necessario modificare anche i record DNS e i certificati.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-124">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="7b3cb-125">Ad esempio, https://lync.contoso.com/Meet se si cambia da per cambiare https://meet.contoso.com l'URL di base da lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-125">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="7b3cb-126">Se l'URL semplice è stato modificato da https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings , l'URL di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-126">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="7b3cb-127">Ogni volta che si modifica un nome URL semplice, è necessario eseguire il cmdlet <STRONG>Enable-CsComputer</STRONG> su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="7b3cb-127">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b3cb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3cb-128">See Also</span></span>


[<span data-ttu-id="7b3cb-129">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b3cb-129">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

