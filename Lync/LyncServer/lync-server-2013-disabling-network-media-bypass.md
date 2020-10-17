---
title: 'Lync Server 2013: disattivazione del bypass multimediale di rete'
description: 'Lync Server 2013: disattivazione del bypass multimediale di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1472711417218aa87936a3ccabe1bb465dd07c20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568142"
---
# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d3624-103">Disabilitazione del bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3624-103">Disabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3624-104">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d3624-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d3624-105">Le impostazioni di bypass multimediale vengono applicate a livello globale in una distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3624-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="d3624-106">Il bypass multimediale consente alle chiamate di bypassare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d3624-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="d3624-107">Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione Planning. È possibile disabilitare il bypass multimediale dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3624-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="d3624-108">Per informazioni dettagliate sull'abilitazione e sulla configurazione del bypass mediale, vedere [Abilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="d3624-108">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="d3624-109">Per disabilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="d3624-109">To disable media bypass</span></span>

1.  <span data-ttu-id="d3624-110">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d3624-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d3624-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3624-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d3624-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d3624-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d3624-113">Sulla barra di spostamento sinistra fare clic su  \*\*Configurazione di rete \*\* e quindi su  \*\*Globale \*\*.</span><span class="sxs-lookup"><span data-stu-id="d3624-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="d3624-p103">Nella pagina  \*\*Globale \*\* fare clic sulla scheda della configurazione  \*\*Globale \*\*. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="d3624-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="d3624-116">Scegliere  \*\*Mostra dettagli \*\* dal menu  \*\*Modifica \*\*.</span><span class="sxs-lookup"><span data-stu-id="d3624-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="d3624-117">Nella pagina  \*\*Modifica impostazioni globali \*\* deselezionare la casella di controllo  \*\*Abilita bypass multimediale \*\*.</span><span class="sxs-lookup"><span data-stu-id="d3624-117">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="d3624-118">Fare clic su  \*\*Commit \*\* per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d3624-118">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3624-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3624-119">See Also</span></span>


[<span data-ttu-id="d3624-120">Abilitazione del bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3624-120">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

