---
title: "Lync Server 2013: abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language)"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8aac965a375520ac46534846a65b67e6d9f92c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="ed0ae-102">Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed0ae-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ed0ae-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ed0ae-104">È possibile utilizzare il pannello di controllo di Lync Server per abilitare o disabilitare le applicazioni server MSPL (Microsoft SIP Processing Language) eseguite nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="ed0ae-105">Si tratta di applicazioni script che utilizzano un linguaggio di script anziché l'API Microsoft Lync 2013 Preview.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="ed0ae-p102">Non tutti gli script possono essere abilitati o disabilitati. Ad esempio, lo script DefaultRouting è abilitato e tale opzione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="ed0ae-108">Per abilitare o disabilitare un'applicazione server MSPL</span><span class="sxs-lookup"><span data-stu-id="ed0ae-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="ed0ae-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ed0ae-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed0ae-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed0ae-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed0ae-112">Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Applicazione server**.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="ed0ae-113">Nella pagina **Applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, quindi fare clic sul'applicazione server che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="ed0ae-114">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-114">Click **Action**.</span></span>

6.  <span data-ttu-id="ed0ae-115">Fare clic su **Abilita applicazione** o **Disabilita applicazione**, se lo script supporta tale opzione.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed0ae-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0ae-116">See Also</span></span>


[<span data-ttu-id="ed0ae-117">Contrassegnare un'applicazione Microsoft SIP Processing Language (MSPL) come critica o non critica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="ed0ae-118">Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="ed0ae-119">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

