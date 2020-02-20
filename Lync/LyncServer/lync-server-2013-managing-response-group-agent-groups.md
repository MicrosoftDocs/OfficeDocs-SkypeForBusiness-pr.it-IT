---
title: 'Lync Server 2013: gestione dei gruppi di agenti di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34fab5d046aa11435aff5be416e281e5848fe4d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="6967b-102">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6967b-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6967b-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6967b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6967b-p101">Un gruppo di agenti è un gruppo di persone che hanno il compito di rispondere alle chiamate di un Response Group. Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare ulteriori impostazioni per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettersi da esso.</span><span class="sxs-lookup"><span data-stu-id="6967b-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6967b-106">Gli utenti devono essere abilitati per VoIP aziendale prima di poterli aggiungere ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="6967b-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="6967b-107">Per informazioni dettagliate sull'abilitazione di un utente per VoIP aziendale, vedere <A href="lync-server-2013-enable-users-for-enterprise-voice.md">abilitare gli utenti per VoIP aziendale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6967b-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6967b-p103">Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.</span><span class="sxs-lookup"><span data-stu-id="6967b-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="6967b-110">Un agente che deve accedere e uscire dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, è definito *agente formale*.</span><span class="sxs-lookup"><span data-stu-id="6967b-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="6967b-111">Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="6967b-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="6967b-112">Questo requisito può rivelarsi utile per gli agenti che rispondono solo a tempo parziale alle chiamate provenienti dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="6967b-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="6967b-113">Gli agenti formali si configurano ed escono dai rispettivi gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console di pagina Web.</span><span class="sxs-lookup"><span data-stu-id="6967b-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="6967b-114">Un agente che non accede o esce dal gruppo è definito *agente informale*.</span><span class="sxs-lookup"><span data-stu-id="6967b-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="6967b-115">Gli agenti informali vengono automaticamente sottoscritti al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="6967b-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6967b-p106">Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy.</span><span class="sxs-lookup"><span data-stu-id="6967b-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6967b-119">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="6967b-119">In This Section</span></span>

  - [<span data-ttu-id="6967b-120">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6967b-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="6967b-121">Eliminare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6967b-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

