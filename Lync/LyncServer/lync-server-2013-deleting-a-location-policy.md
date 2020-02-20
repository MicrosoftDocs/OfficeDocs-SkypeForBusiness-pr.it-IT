---
title: 'Lync Server 2013: eliminazione di un criterio percorso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70f56f2a33ef92769a129e8fd9f84fe467c93e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="435f9-102">Eliminazione di un criterio percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="435f9-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="435f9-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="435f9-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="435f9-104">In Lync Server 2013, è possibile utilizzare i criteri percorso per applicare le impostazioni relative alla funzionalità Enhanced 9-1-1 (E9-1-1) e alle impostazioni di posizione per utenti o contatti.</span><span class="sxs-lookup"><span data-stu-id="435f9-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="435f9-105">I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="435f9-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="435f9-106">Ad esempio, è possibile usare i criteri di posizione per definire il numero di emergenza (ad esempio il 113 in Italia), se la sicurezza aziendale deve essere automaticamente notificata e come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="435f9-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="435f9-107">È possibile configurare i criteri percorso dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="435f9-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="435f9-108">Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="435f9-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="435f9-109">Usare le procedure seguenti per eliminare un criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="435f9-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="435f9-110">Per informazioni dettagliate sulla creazione o la modifica dei criteri percorso, vedere [creazione o modifica di un criterio percorso in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="435f9-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="435f9-111">Per eliminare un criterio di posizione</span><span class="sxs-lookup"><span data-stu-id="435f9-111">To delete a location policy</span></span>

1.  <span data-ttu-id="435f9-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="435f9-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="435f9-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="435f9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="435f9-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="435f9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="435f9-115">Nella barra di spostamento sinistra fare clic su  \*\*Configurazione di rete \*\* e quindi su  \*\*Criteri percorso \*\*.</span><span class="sxs-lookup"><span data-stu-id="435f9-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="435f9-116">Nella pagina  \*\*Criteri percorso \*\* selezionare il criterio percorso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="435f9-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="435f9-p104">È possibile eliminare più criteri percorso contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi criteri. In alternativa, per selezionare tutti i criteri, scegliere  <STRONG>Seleziona tutto </STRONG> dal menu  <STRONG>Modifica </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="435f9-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="435f9-120">Scegliere  \*\*Elimina \*\* dal menu  \*\*Modifica \*\*.</span><span class="sxs-lookup"><span data-stu-id="435f9-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="435f9-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="435f9-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="435f9-p105">Non è possibile eliminare il criterio percorso Globale. Se si tenta di eliminare tale criterio, verrà visualizzato un messaggio di avviso e il criterio verrà reimpostato sui relativi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="435f9-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="435f9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="435f9-124">See Also</span></span>


[<span data-ttu-id="435f9-125">Creazione o modifica di un criterio percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="435f9-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="435f9-126">Visualizzazione delle informazioni sui criteri percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="435f9-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

