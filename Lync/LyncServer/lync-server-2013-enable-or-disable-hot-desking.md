---
title: 'Lync Server 2013: attivazione o disattivazione della scrivania calda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd0378ee0aead4529b61be5f71aa37a64faf86c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="c5ab1-102">Abilitare o disabilitare l'hot desking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5ab1-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5ab1-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c5ab1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c5ab1-104">È possibile configurare i telefoni delle aree comuni come *telefoni da tavolo caldo*.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="c5ab1-105">Con i telefoni Hot-Desk, gli utenti possono accedere al proprio account utente e, dopo aver effettuato l'accesso, utilizzare le funzionalità di Lync Server e le proprie impostazioni del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="c5ab1-106">La gestione delle chiamate a caldo è gestita utilizzando i criteri client: per abilitare o disabilitare la scrivania calda, è necessario modificare i criteri client utilizzati dai telefoni delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="c5ab1-107">Per informazioni dettagliate su come determinare i criteri di conferenza assegnati ai telefoni delle aree comuni, vedere [View common area Phone Information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="c5ab1-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="c5ab1-108">È possibile utilizzare il parametro EnableHotdesking del cmdlet **New-CsClientPolicy** o il cmdlet **Set-CsClientPolicy** per abilitare o disabilitare la scrivania calda su un telefono, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="c5ab1-109">Eseguire questi cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c5ab1-110">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="c5ab1-111">Abilitazione di Hot desking</span><span class="sxs-lookup"><span data-stu-id="c5ab1-111">Enabling hot desking</span></span>

  - <span data-ttu-id="c5ab1-112">Per abilitare il servizio di desktop attivo per un telefono di area comune, è necessario modificare il criterio client assegnato al telefono (o all'insieme di telefoni).</span><span class="sxs-lookup"><span data-stu-id="c5ab1-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="c5ab1-113">Dopo aver identificato il criterio che deve essere modificato, il passaggio successivo consiste nell'utilizzare il cmdlet **Set-CsClientPolicy** per impostare il parametro EnableHotdesking su true.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="c5ab1-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5ab1-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="c5ab1-115">In alternativa, è possibile utilizzare il cmdlet **New-CsClientPolicy** per creare un nuovo criterio client che consenta l'utilizzo di Hot Desk.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="c5ab1-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5ab1-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5ab1-117">Dopo aver creato questo criterio, è necessario assegnarlo ai telefoni delle aree comuni appropriate.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="c5ab1-118">Per ulteriori informazioni, vedere <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">assegnare criteri in Lync Server 2013 a un telefono di area comune</A>.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="c5ab1-119">Disabilitazione di Hot desking</span><span class="sxs-lookup"><span data-stu-id="c5ab1-119">Disabling hot desking</span></span>

  - <span data-ttu-id="c5ab1-120">Per disabilitare l'hot desking per un telefono di area comune, reimpostare il parametro EnableHotdesking del cmdlet **Set-CsClientPolicy** sul valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="c5ab1-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="c5ab1-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5ab1-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="c5ab1-122">Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="c5ab1-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

