---
title: 'Lync Server 2013: visualizzazione di un elenco di applicazioni attendibili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16f1e202c1d7e60202b76d42f0104f372213597f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="35c87-102">Visualizzare un elenco di applicazioni attendibili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35c87-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35c87-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="35c87-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="35c87-104">È possibile utilizzare il pannello di controllo di Lync Server 2013 per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35c87-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="35c87-105">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è considerato attendibile da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35c87-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="35c87-106">Questa relazione di trust è riepilogata nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="35c87-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="35c87-107">Le applicazioni attendibili non sono contestate per l'autenticazione da parte di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35c87-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="35c87-108">Le applicazioni attendibili non vengono limitate da Lync Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.</span><span class="sxs-lookup"><span data-stu-id="35c87-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="35c87-109">Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza essere inserite negli elenchi dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="35c87-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="35c87-110">Le applicazioni attendibili sono resilienti e a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="35c87-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="35c87-111">Nel pannello di controllo di Lync Server, è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguite e la porta utilizzata.</span><span class="sxs-lookup"><span data-stu-id="35c87-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="35c87-112">Per visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="35c87-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="35c87-113">Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a un computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="35c87-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="35c87-114">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione del controllo di accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="35c87-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="35c87-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35c87-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35c87-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35c87-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35c87-117">Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="35c87-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="35c87-118">Nella pagina **Applicazione attendibile** fare clic sull'intestazione di una colonna per ordinare le applicazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="35c87-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35c87-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35c87-119">See Also</span></span>


[<span data-ttu-id="35c87-120">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35c87-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

