---
title: 'Lync Server 2013: abilitare il prelievo delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo'
description: 'Lync Server 2013: abilitare il prelievo delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo.'
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
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559642"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="a6e93-103">Abilitazione del prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnazione di un numero di gruppo</span><span class="sxs-lookup"><span data-stu-id="a6e93-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6e93-104">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a6e93-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a6e93-105">Dopo aver aggiunto i numeri del gruppo di prelievo delle chiamate alla tabella di orbit del parcheggio di chiamata, è necessario assegnare i numeri di gruppo agli utenti e attivare il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a6e93-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="a6e93-106">Utilizzare lo strumento Resource Kit di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare i numeri di gruppo e abilitare il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a6e93-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6e93-107">In una distribuzione ibrida, non assegnare un gruppo di prelievo di chiamata di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="a6e93-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="a6e93-108">Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a6e93-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a6e93-109">Vale a fare che le chiamate non possono rispondere ad altri utenti e che non rispondono alle chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a6e93-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="a6e93-110">Per assegnare un numero di gruppo e abilitare il prelievo delle chiamate di gruppo per un utente</span><span class="sxs-lookup"><span data-stu-id="a6e93-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="a6e93-111">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a6e93-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="a6e93-112">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a6e93-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="a6e93-113">Ad esempio, per assegnare il numero di gruppo 199 a un utente:</span><span class="sxs-lookup"><span data-stu-id="a6e93-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6e93-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e93-114">See Also</span></span>


[<span data-ttu-id="a6e93-115">Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6e93-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

