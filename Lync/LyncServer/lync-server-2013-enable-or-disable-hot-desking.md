---
title: 'Lync Server 2013: abilitare o disabilitare la scrivania a caldo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="be150-102">Abilitare o disabilitare le scrivanie a caldo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be150-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be150-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="be150-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="be150-104">È possibile configurare telefoni per l'area comune come *telefoni da tavolo caldo*.</span><span class="sxs-lookup"><span data-stu-id="be150-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="be150-105">Con i telefoni da tavolo caldo, gli utenti possono accedere al proprio account utente e, dopo aver effettuato l'accesso, usare le caratteristiche di Lync Server e le proprie impostazioni del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="be150-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="be150-106">L'uso di scrivanie a caldo viene gestito con i criteri client: per abilitare o disabilitare il servizio di desktop caldo, è necessario modificare i criteri client usati dai telefoni delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="be150-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="be150-107">Per informazioni dettagliate su come determinare i criteri di conferenza assegnati ai telefoni delle aree comuni, vedere visualizzare le [informazioni sul telefono per le aree comuni in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="be150-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="be150-108">Puoi usare il parametro EnableHotdesking del cmdlet **New-CsClientPolicy** o il cmdlet **Set-CsClientPolicy** per abilitare o disabilitare il servizio di desktop a caldo in un telefono, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="be150-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="be150-109">Eseguire questi cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be150-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="be150-110">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="be150-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="be150-111">Abilitazione del desktop a caldo</span><span class="sxs-lookup"><span data-stu-id="be150-111">Enabling hot desking</span></span>

  - <span data-ttu-id="be150-112">Per abilitare il desktop a caldo per un telefono con area comune, è necessario modificare i criteri client assegnati al telefono o alla raccolta di telefoni.</span><span class="sxs-lookup"><span data-stu-id="be150-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="be150-113">Dopo aver identificato i criteri che devono essere modificati, il passaggio successivo consiste nell'usare il cmdlet **Set-CsClientPolicy** per impostare il parametro EnableHotdesking su true.</span><span class="sxs-lookup"><span data-stu-id="be150-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="be150-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be150-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="be150-115">In alternativa, puoi usare il cmdlet **New-CsClientPolicy** per creare un nuovo criterio client che consente la creazione di scrivanie a caldo.</span><span class="sxs-lookup"><span data-stu-id="be150-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="be150-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be150-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be150-117">Dopo aver creato questo criterio, è necessario assegnarlo ai telefoni dell'area comune appropriati.</span><span class="sxs-lookup"><span data-stu-id="be150-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="be150-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">assegnare criteri in Lync Server 2013 a un telefono con area comune</A>.</span><span class="sxs-lookup"><span data-stu-id="be150-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="be150-119">Disabilitazione della scrivania calda</span><span class="sxs-lookup"><span data-stu-id="be150-119">Disabling hot desking</span></span>

  - <span data-ttu-id="be150-120">Per disabilitare il desktop caldo per un telefono con area comune, reimpostare il parametro EnableHotdesking del cmdlet **Set-CsClientPolicy** sul valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="be150-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="be150-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be150-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="be150-122">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="be150-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

