---
title: 'Lync Server 2013: visualizzazione delle informazioni sui criteri percorso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f22f5f218f3b9b97b90b26e1f74ec80cd0572e93
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="d5fe8-102">Visualizzazione delle informazioni sui criteri percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5fe8-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5fe8-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5fe8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5fe8-104">In Lync Server 2013, è possibile utilizzare i criteri percorso per applicare le impostazioni relative alla funzionalità Enhanced 9-1-1 (E9-1-1) e alle impostazioni di posizione per utenti o contatti.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="d5fe8-105">I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="d5fe8-106">Ad esempio, è possibile usare i criteri di posizione per definire il numero di emergenza (ad esempio il 113 in Italia), se la sicurezza aziendale deve essere automaticamente notificata e come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="d5fe8-107">È possibile configurare i criteri percorso dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d5fe8-108">Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="d5fe8-109">Utilizzare la seguente procedura per visualizzare informazioni sui criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="d5fe8-110">Per informazioni dettagliate sulla creazione o la modifica dei criteri percorso, vedere [creazione o modifica di un criterio percorso in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d5fe8-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="d5fe8-111">Per visualizzare informazioni sui criteri percorso</span><span class="sxs-lookup"><span data-stu-id="d5fe8-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="d5fe8-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d5fe8-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5fe8-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d5fe8-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5fe8-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri percorso**.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="d5fe8-116">Nella pagina **Criteri percorso** selezionare il criterio percorso che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="d5fe8-117">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5fe8-118">È possibile visualizzare le informazioni su un solo criterio percorso alla volta.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="d5fe8-p104">Per impostazione predefinita, esiste un solo criterio, denominato Globale, e non può essere eliminato o rinominato. È tuttavia possibile modificarlo. Tale criterio verrà applicato a tutti gli utenti e i contatti, a meno che non vengano creati criteri sito o criteri utente. I criteri utente devono essere applicati a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="d5fe8-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5fe8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5fe8-123">See Also</span></span>


[<span data-ttu-id="d5fe8-124">Creazione o modifica di un criterio percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5fe8-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="d5fe8-125">Creare criteri percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5fe8-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="d5fe8-126">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5fe8-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="d5fe8-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d5fe8-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="d5fe8-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d5fe8-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="d5fe8-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d5fe8-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="d5fe8-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d5fe8-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

