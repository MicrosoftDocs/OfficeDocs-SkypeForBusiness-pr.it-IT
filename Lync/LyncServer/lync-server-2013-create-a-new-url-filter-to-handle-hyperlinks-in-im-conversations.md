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
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="98c6a-102">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe</span><span class="sxs-lookup"><span data-stu-id="98c6a-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c6a-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="98c6a-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="98c6a-104">Oltre a modificare il filtro URL globale, è possibile configurare filtri URL personalizzati per singoli siti all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c6a-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="98c6a-105">Per informazioni dettagliate sul filtro degli URL, vedere [configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="98c6a-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="98c6a-106">Per creare un nuovo filtro URL</span><span class="sxs-lookup"><span data-stu-id="98c6a-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="98c6a-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="98c6a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98c6a-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98c6a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="98c6a-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="98c6a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="98c6a-110">Nella barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza**, quindi fare clic su **filtro URL**.</span><span class="sxs-lookup"><span data-stu-id="98c6a-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="98c6a-111">Nella pagina **filtro URL** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="98c6a-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="98c6a-112">In **Seleziona un sito**fare clic sul sito per il quale si vuole creare il filtro URL e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c6a-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="98c6a-113">Nella finestra di dialogo **filtro URL nuovo** selezionare la casella di controllo **Abilita filtro URL** per abilitare il filtro URL per il sito.</span><span class="sxs-lookup"><span data-stu-id="98c6a-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="98c6a-114">Per bloccare qualsiasi URL attivo che contiene un file con un'estensione elencata in **estensioni di tipo file da bloccare** in **Modifica filtro file**, selezionare la casella di controllo **Blocca URL con estensione di file** .</span><span class="sxs-lookup"><span data-stu-id="98c6a-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="98c6a-115">Nella casella di riepilogo a discesa **prefisso collegamento ipertestuale** fare clic sull'opzione corrispondente al modo in cui si vogliono gestire gli URL nelle conversazioni istantanee dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="98c6a-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="98c6a-116">La casella **Consenti messaggio** consente di inviare un messaggio di avviso all'utente durante l'invio di collegamenti ipertestuali che possono essere inviati.</span><span class="sxs-lookup"><span data-stu-id="98c6a-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="98c6a-117">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="98c6a-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98c6a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c6a-118">See Also</span></span>


[<span data-ttu-id="98c6a-119">Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c6a-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="98c6a-120">Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="98c6a-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="98c6a-121">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c6a-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="98c6a-122">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c6a-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

