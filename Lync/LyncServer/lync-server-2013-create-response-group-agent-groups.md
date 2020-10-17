---
title: 'Lync Server 2013: creare gruppi di agenti di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3df5b191abea7aea75c2ad55afa586479d6e89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514703"
---
# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="c706c-102">Creare gruppi di agenti di Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c706c-102">Create Response Group agent groups Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c706c-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c706c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c706c-104">Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare impostazioni aggiuntive per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettervisi.</span><span class="sxs-lookup"><span data-stu-id="c706c-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="c706c-105">Un agente che deve accedere e uscire dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, è definito *agente formale*.</span><span class="sxs-lookup"><span data-stu-id="c706c-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="c706c-106">Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="c706c-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="c706c-107">Questo requisito può rivelarsi utile per gli agenti che rispondono alle chiamate provenienti dal gruppo a tempo parziale.</span><span class="sxs-lookup"><span data-stu-id="c706c-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="c706c-108">Gli agenti formali si configurano ed escono dai rispettivi gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console di pagina Web.</span><span class="sxs-lookup"><span data-stu-id="c706c-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="c706c-109">Un agente che non accede o esce dal gruppo è definito *agente informale*.</span><span class="sxs-lookup"><span data-stu-id="c706c-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="c706c-110">Gli agenti informali vengono automaticamente sottoscritti al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="c706c-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c706c-p103">Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.</span><span class="sxs-lookup"><span data-stu-id="c706c-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c706c-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c706c-113">In This Section</span></span>

[<span data-ttu-id="c706c-114">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c706c-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

