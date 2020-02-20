---
title: Creare un nuovo filtro URL per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 250533f8de89eb1cd5aaa72d8f66cfd0800a1bc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="9af35-102">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="9af35-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9af35-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9af35-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9af35-104">Oltre a modificare il filtro URL globale, è possibile configurare filtri URL personalizzati per singoli siti all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af35-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="9af35-105">Per informazioni dettagliate sul filtro degli URL, vedere [Configuring file transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="9af35-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="9af35-106">Per creare un nuovo filtro URL</span><span class="sxs-lookup"><span data-stu-id="9af35-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="9af35-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9af35-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9af35-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9af35-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9af35-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9af35-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9af35-110">Sulla barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza**e quindi su **filtro URL**.</span><span class="sxs-lookup"><span data-stu-id="9af35-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="9af35-111">Nella pagina **filtro URL** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9af35-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="9af35-112">In **Seleziona un sito**fare clic sul sito per il quale si desidera creare il filtro URL e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9af35-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="9af35-113">Nella finestra di dialogo **nuovo filtro URL** selezionare la casella di controllo **Abilita filtro URL** per abilitare il filtro URL per il sito.</span><span class="sxs-lookup"><span data-stu-id="9af35-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="9af35-114">Per bloccare qualsiasi URL attivo contenente un file con un'estensione elencata in **estensioni di file da bloccare** in **Modifica filtro file**, selezionare la casella di controllo **Blocca URL con estensione di file** .</span><span class="sxs-lookup"><span data-stu-id="9af35-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="9af35-115">Nella casella di riepilogo a discesa **prefisso collegamento ipertestuale** fare clic sull'opzione corrispondente al modo in cui si desidera gestire gli URL nelle conversazioni istantanee dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9af35-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="9af35-116">La casella **Consenti messaggio** consente di inviare all'utente un messaggio di avviso per l'invio di collegamenti ipertestuali autorizzati a essere inviati.</span><span class="sxs-lookup"><span data-stu-id="9af35-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="9af35-117">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9af35-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9af35-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9af35-118">See Also</span></span>


[<span data-ttu-id="9af35-119">Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af35-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="9af35-120">Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="9af35-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="9af35-121">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af35-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="9af35-122">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af35-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

