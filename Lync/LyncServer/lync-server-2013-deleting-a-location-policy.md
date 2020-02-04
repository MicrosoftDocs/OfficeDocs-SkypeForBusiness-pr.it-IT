---
title: 'Lync Server 2013: eliminazione di un criterio di posizione'
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
ms.openlocfilehash: 2ea7f585e42164c8387853c7525cd0478eeb4db4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="41965-102">Eliminazione di un criterio di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41965-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41965-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="41965-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="41965-104">In Lync Server 2013 è possibile usare i criteri di posizione per applicare le impostazioni relative alle funzionalità avanzate di 9-1-1 (E9-1-1) e alle impostazioni della posizione per gli utenti o i contatti.</span><span class="sxs-lookup"><span data-stu-id="41965-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="41965-105">I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, in caso affermativo, qual è il comportamento di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="41965-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="41965-106">Ad esempio, è possibile usare i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti, se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="41965-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="41965-107">È possibile configurare i criteri di posizione dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41965-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="41965-108">Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="41965-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="41965-109">Usare le procedure seguenti per eliminare un criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="41965-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="41965-110">Per informazioni dettagliate sulla creazione o la modifica dei criteri di posizione, vedere [creazione o modifica di un criterio di posizione in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="41965-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="41965-111">Per eliminare un criterio di posizione</span><span class="sxs-lookup"><span data-stu-id="41965-111">To delete a location policy</span></span>

1.  <span data-ttu-id="41965-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="41965-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41965-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41965-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="41965-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41965-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="41965-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri posizione**.</span><span class="sxs-lookup"><span data-stu-id="41965-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="41965-116">Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="41965-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41965-117">È possibile eliminare più criteri di posizione alla volta.</span><span class="sxs-lookup"><span data-stu-id="41965-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="41965-118">Per eseguire questa operazione, premere CTRL e selezionare più criteri tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="41965-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="41965-119">In alternativa, per selezionare tutti i criteri, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="41965-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="41965-120">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="41965-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="41965-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="41965-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41965-122">Non è possibile eliminare i criteri di posizione globale.</span><span class="sxs-lookup"><span data-stu-id="41965-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="41965-123">Se si tenta di eliminare il criterio globale si riceverà un messaggio di avviso e il criterio verrà reimpostato sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="41965-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41965-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41965-124">See Also</span></span>


[<span data-ttu-id="41965-125">Creazione o modifica di un criterio di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41965-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="41965-126">Visualizzazione delle informazioni sui criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41965-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

