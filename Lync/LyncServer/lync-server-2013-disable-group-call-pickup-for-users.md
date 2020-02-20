---
title: 'Lync Server 2013: disabilitare il prelievo delle chiamate di gruppo per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e015fd7fc3be36439fb240e2f3f50ed7bc8ec1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="af03a-102">Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af03a-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af03a-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="af03a-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="af03a-104">Per disabilitare il prelievo delle chiamate di gruppo per un utente, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="af03a-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af03a-105">Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero del gruppo di prelievo delle chiamate assegnato all'utente non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="af03a-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="af03a-106">Se successivamente si desidera riabilitare il prelievo delle chiamate di gruppo per tale utente, è necessario assegnare di nuovo il numero del gruppo di prelievo delle chiamate con il parametro/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="af03a-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="af03a-107">Per disabilitare il prelievo delle chiamate di gruppo per un utente</span><span class="sxs-lookup"><span data-stu-id="af03a-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="af03a-108">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="af03a-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="af03a-109">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="af03a-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="af03a-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="af03a-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af03a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af03a-111">See Also</span></span>


[<span data-ttu-id="af03a-112">Assegnare numeri di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af03a-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="af03a-113">Abilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af03a-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

