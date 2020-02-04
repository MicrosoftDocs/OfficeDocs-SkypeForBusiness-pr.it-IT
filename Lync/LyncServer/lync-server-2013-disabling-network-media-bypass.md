---
title: 'Lync Server 2013: disabilitare il bypass multimediale di rete'
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
ms.openlocfilehash: 0457281a743d317e17a5fd0728e1a747b4d88271
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="1e9b6-102">Disabilitare il bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9b6-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e9b6-103">_**Argomento Ultima modifica:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="1e9b6-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1e9b6-104">Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="1e9b6-105">Il bypass multimediale consente alle chiamate di aggirare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="1e9b6-106">Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione pianificazione. È possibile disabilitare il bypass multimediale dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="1e9b6-107">Per informazioni dettagliate sull'abilitazione e la configurazione del bypass mediale, vedere [Abilitazione del bypass multimediale di rete in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="1e9b6-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="1e9b6-108">Per disabilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="1e9b6-108">To disable media bypass</span></span>

1.  <span data-ttu-id="1e9b6-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e9b6-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e9b6-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e9b6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e9b6-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1e9b6-113">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="1e9b6-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="1e9b6-114">Esiste sempre una sola configurazione ed è sempre denominata globale.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="1e9b6-115">Nel menu **modifica** fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="1e9b6-116">Nella pagina **Modifica impostazioni globali** deselezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="1e9b6-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="1e9b6-117">Fare clic su **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1e9b6-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e9b6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e9b6-118">See Also</span></span>


[<span data-ttu-id="1e9b6-119">Abilitare il bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9b6-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

