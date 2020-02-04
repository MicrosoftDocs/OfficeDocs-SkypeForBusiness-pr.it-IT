---
title: 'Lync Server 2013: visualizzare un elenco di applicazioni attendibili'
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
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="8e224-102">Visualizzare un elenco di applicazioni attendibili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e224-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e224-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8e224-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8e224-104">È possibile usare il pannello di controllo di Lync Server 2013 per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e224-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="8e224-105">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK attendibile per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e224-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="8e224-106">Questa relazione di trust viene riepilogata nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="8e224-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="8e224-107">Le applicazioni attendibili non vengono contestate per l'autenticazione da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e224-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="8e224-108">Le applicazioni attendibili non vengono limitate da Lync Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.</span><span class="sxs-lookup"><span data-stu-id="8e224-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="8e224-109">Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza comparire in roster.</span><span class="sxs-lookup"><span data-stu-id="8e224-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="8e224-110">Le applicazioni attendibili sono altamente disponibili e resilienti.</span><span class="sxs-lookup"><span data-stu-id="8e224-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="8e224-111">Nel pannello di controllo di Lync Server è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguiti e la porta che usano.</span><span class="sxs-lookup"><span data-stu-id="8e224-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="8e224-112">Per visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="8e224-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="8e224-113">Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8e224-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="8e224-114">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="8e224-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="8e224-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e224-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8e224-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8e224-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8e224-117">Nella barra di spostamento sinistra fare clic su **topologia** e fare clic su **applicazione attendibile**.</span><span class="sxs-lookup"><span data-stu-id="8e224-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="8e224-118">Nella pagina dell' **applicazione attendibile** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8e224-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e224-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e224-119">See Also</span></span>


[<span data-ttu-id="8e224-120">Gestione della topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e224-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

