---
title: 'Lync Server 2013: assegnare i numeri di prelievo delle chiamate di gruppo agli utenti'
description: 'Lync Server 2013: assegnare i numeri di prelievo delle chiamate di gruppo agli utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566132"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="51d64-103">Assegnare numeri di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51d64-103">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51d64-104">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="51d64-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="51d64-105">Dopo aver aggiunto i numeri del gruppo di prelievo delle chiamate di gruppo alla tabella orbit del parcheggio di chiamata, è possibile assegnare i gruppi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="51d64-105">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="51d64-106">Utilizzare lo strumento Resource Kit di attivazione delle funzionalità di SEFAUtil (Secondary Extension feature Activation) per assegnare i gruppi di prelievo delle chiamate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="51d64-106">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51d64-107">In una distribuzione ibrida, non assegnare un gruppo di prelievo di chiamata di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="51d64-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="51d64-108">Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="51d64-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="51d64-109">Vale a fare che le chiamate non possono rispondere ad altri utenti e che non rispondono alle chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="51d64-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="51d64-110">Per assegnare un gruppo di prelievo di chiamata di gruppo a un utente</span><span class="sxs-lookup"><span data-stu-id="51d64-110">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="51d64-111">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="51d64-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="51d64-112">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="51d64-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="51d64-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51d64-113">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51d64-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51d64-114">See Also</span></span>


[<span data-ttu-id="51d64-115">Abilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51d64-115">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="51d64-116">Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51d64-116">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

