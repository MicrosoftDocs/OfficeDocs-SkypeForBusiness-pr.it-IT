---
title: 'Lync Server 2013: Modificare o configurare URL semplici'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="859a4-102">Modificare o configurare URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="859a4-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="859a4-103">_**Argomento Ultima modifica:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="859a4-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="859a4-104">Questa procedura non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati.</span><span class="sxs-lookup"><span data-stu-id="859a4-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="859a4-105">È necessario accedere a un computer come utente standard.</span><span class="sxs-lookup"><span data-stu-id="859a4-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="859a4-106">Lync Server 2013 usa URL semplici per indirizzare chiamate interne ed esterne ai servizi nel server front-end o nel Director, se uno è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="859a4-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="859a4-107">Per altre informazioni sugli URL semplici, vedere [pianificazione di URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="859a4-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="859a4-108">Puoi selezionare il formato per i tuoi URL semplici da diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="859a4-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="859a4-109">Per informazioni dettagliate su queste opzioni, vedere [requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="859a4-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="859a4-110">Per impostazione predefinita, gli URL semplici verranno configurati in forma di (ad esempio, l'URL semplice in accesso esterno https://dialin.\<SIP ): Domain\></span><span class="sxs-lookup"><span data-stu-id="859a4-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="859a4-111">Per configurare gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="859a4-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="859a4-112">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="859a4-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="859a4-113">Nel riquadro **URL semplici** selezionare **URL di accesso telefonico:** (chiamata in ingresso) o URL delle **riunioni: (riunione** ) per modificare e quindi fare clic su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="859a4-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="859a4-114">Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="859a4-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="859a4-115">L'esempio illustrato in questo articolo ha modificato l'URL di accesso https://pool01.contoso.net/dialinesterno a.</span><span class="sxs-lookup"><span data-stu-id="859a4-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="859a4-116">Modificare l'URL di riunione usando la stessa procedura, se necessario.</span><span class="sxs-lookup"><span data-stu-id="859a4-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="859a4-117">Per definire l'URL semplice amministratore facoltativo</span><span class="sxs-lookup"><span data-stu-id="859a4-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="859a4-118">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="859a4-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="859a4-119">Nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="859a4-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="859a4-120">È consigliabile usare l'URL più semplice possibile per l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="859a4-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="859a4-121">L'opzione più semplice è <STRONG> https://admin.</STRONG> &lt;domain&gt;.</span><span class="sxs-lookup"><span data-stu-id="859a4-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="859a4-122">Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli delle modifiche che incidono sui record DNS (Domain Name System) e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="859a4-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="859a4-123">Se la modifica ha un impatto sulla base di un URL semplice, è necessario modificare anche i record DNS e i certificati.</span><span class="sxs-lookup"><span data-stu-id="859a4-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="859a4-124">Ad esempio, passando da https://lync.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="859a4-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="859a4-125">Se è stato modificato l'URL https://lync.contoso.com/Meet semplice https://lync.contoso.com/Meetings, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato.</span><span class="sxs-lookup"><span data-stu-id="859a4-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="859a4-126">Ogni volta che si modifica un nome di URL semplice, è necessario eseguire il cmdlet <STRONG>Enable-CsComputer</STRONG> su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="859a4-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="859a4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="859a4-127">See Also</span></span>


[<span data-ttu-id="859a4-128">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="859a4-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

