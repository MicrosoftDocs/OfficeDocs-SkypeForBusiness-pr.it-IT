---
title: 'Lync Server 2013: assegnare numeri di raccolta chiamate di gruppo agli utenti'
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
ms.openlocfilehash: e65eef9fcf425ad8ea9f36dc57899bb6af924bf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="3d1dd-102">Assegnare numeri di raccolta chiamate di gruppo agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1dd-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d1dd-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="3d1dd-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="3d1dd-104">Dopo aver aggiunto i numeri dei gruppi di prelievo delle chiamate di gruppo alla tabella Orbit di Call Park, è possibile assegnare i gruppi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="3d1dd-105">Usare lo strumento Resource Kit di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare gruppi di prelievo delle chiamate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d1dd-106">In una distribuzione ibrida non assegnare un gruppo di raccolta chiamate di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="3d1dd-107">Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="3d1dd-108">Ossia, non è possibile rispondere alle chiamate di altri utenti, e non possono ricevere risposte ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="3d1dd-109">Per assegnare un gruppo di raccolta chiamate di gruppo a un utente</span><span class="sxs-lookup"><span data-stu-id="3d1dd-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="3d1dd-110">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3d1dd-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="3d1dd-111">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="3d1dd-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="3d1dd-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3d1dd-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d1dd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d1dd-113">See Also</span></span>


[<span data-ttu-id="3d1dd-114">Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1dd-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="3d1dd-115">Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1dd-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

