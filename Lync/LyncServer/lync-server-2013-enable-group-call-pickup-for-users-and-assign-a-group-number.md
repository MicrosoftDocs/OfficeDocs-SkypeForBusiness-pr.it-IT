---
title: 'Lync Server 2013: abilitare il ritiro delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5ad9bbc6f5505e5778872a568bdbc80b3f7bf91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="cc141-102">Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnare un numero di gruppo</span><span class="sxs-lookup"><span data-stu-id="cc141-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc141-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="cc141-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="cc141-104">Dopo aver aggiunto numeri di gruppo di prelievo chiamate alla tabella Orbit di Call Park, assegnare i numeri di gruppo agli utenti e abilitare il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc141-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="cc141-105">Usare lo strumento Resource Kit di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare numeri di gruppo e consentire il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc141-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc141-106">In una distribuzione ibrida non assegnare un gruppo di raccolta chiamate di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="cc141-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="cc141-107">Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc141-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="cc141-108">Ossia, non è possibile rispondere alle chiamate di altri utenti, e non possono ricevere risposte ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="cc141-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="cc141-109">Per assegnare un numero di gruppo e abilitare il ritiro delle chiamate di gruppo per un utente</span><span class="sxs-lookup"><span data-stu-id="cc141-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="cc141-110">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="cc141-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="cc141-111">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="cc141-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="cc141-112">Ad esempio, per assegnare un numero di gruppo 199 a un utente:</span><span class="sxs-lookup"><span data-stu-id="cc141-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc141-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc141-113">See Also</span></span>


[<span data-ttu-id="cc141-114">Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc141-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

