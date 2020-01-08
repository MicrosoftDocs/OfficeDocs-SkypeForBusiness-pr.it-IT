---
title: "Lync Server 2013: contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="b5428-102">Contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5428-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5428-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b5428-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b5428-104">Le applicazioni server MSPL (Microsoft SIP Processing Language) sono applicazioni solo script che usano il linguaggio di scripting MSPL invece dell'API Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b5428-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="b5428-105">Alcune applicazioni server MSPL sono specificate come critiche.</span><span class="sxs-lookup"><span data-stu-id="b5428-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="b5428-106">Se uno script è critico, lo script deve iniziare durante l'avvio del sistema per consentire l'avvio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5428-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="b5428-107">Se lo script non riesce mentre Lync Server è in esecuzione, il server non si arresta, ma smette di inviare il traffico allo script e scrive gli errori nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="b5428-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="b5428-108">È possibile usare il pannello di controllo di Lync Server per contrassegnare le applicazioni server MSPL (Microsoft SIP Processing Language) come critiche o deselezionarle.</span><span class="sxs-lookup"><span data-stu-id="b5428-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="b5428-109">Non tutti gli script supportano questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b5428-109">Not all scripts support this option.</span></span> <span data-ttu-id="b5428-110">Ad esempio, lo script DefaultRouting è contrassegnato come critico e questa opzione non può essere modificata per DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="b5428-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="b5428-111">Per contrassegnare o decontrassegnare un'applicazione server MSPL come critica</span><span class="sxs-lookup"><span data-stu-id="b5428-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="b5428-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5428-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b5428-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5428-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5428-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5428-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5428-115">Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **applicazione server**.</span><span class="sxs-lookup"><span data-stu-id="b5428-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="b5428-116">Nella pagina **applicazione server** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario, e quindi fare clic sull'applicazione server che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b5428-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="b5428-117">Fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="b5428-117">Click **Action**.</span></span>

6.  <span data-ttu-id="b5428-118">Fare clic su **Segna come critico** o **deselezionare come critica** , ovvero se lo script supporta questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b5428-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5428-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5428-119">See Also</span></span>


[<span data-ttu-id="b5428-120">Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5428-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="b5428-121">Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5428-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="b5428-122">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5428-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

