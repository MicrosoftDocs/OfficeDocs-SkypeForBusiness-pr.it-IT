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
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="bb867-102">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb867-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb867-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="bb867-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="bb867-104">Un gruppo di agenti è costituito da un gruppo di persone designate per rispondere alle chiamate a un gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="bb867-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="bb867-105">Quando si crea un gruppo di agenti, si selezionano gli agenti assegnati al gruppo e si specificano altre impostazioni di gruppo, ad esempio il metodo di routing, e se un agente può accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="bb867-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb867-106">Gli utenti devono essere abilitati per VoIP aziendale prima di poterli aggiungere ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="bb867-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="bb867-107">Per informazioni dettagliate su come abilitare un utente per VoIP aziendale, vedere <A href="lync-server-2013-enable-users-for-enterprise-voice.md">abilitare gli utenti per VoIP aziendale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bb867-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bb867-108">Solo gli utenti locali possono essere agenti.</span><span class="sxs-lookup"><span data-stu-id="bb867-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="bb867-109">Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.</span><span class="sxs-lookup"><span data-stu-id="bb867-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="bb867-110">Un agente che deve accedere e disconnettersi dal gruppo, che è diverso dall'accesso o dall'esterno di Lync Server, viene chiamato *agente formale*.</span><span class="sxs-lookup"><span data-stu-id="bb867-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="bb867-111">Gli agenti formali devono essere connessi al gruppo prima che possano ricevere le chiamate instradate al gruppo.</span><span class="sxs-lookup"><span data-stu-id="bb867-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="bb867-112">Può essere utile per gli agenti che rispondono alle chiamate dal gruppo in base a tempo parziale.</span><span class="sxs-lookup"><span data-stu-id="bb867-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="bb867-113">Gli agenti formali entrano e espongono i gruppi facendo clic su una voce di menu in Lync 2013 per aprire il browser Internet di Windows Internet Explorer e visualizzare una console della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="bb867-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="bb867-114">Un agente che non esegue l'accesso o fuori dal gruppo viene chiamato *agente informale*.</span><span class="sxs-lookup"><span data-stu-id="bb867-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="bb867-115">Gli agenti informali vengono automaticamente connessi al gruppo quando accedono a Lync Server e non possono disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="bb867-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb867-116">Quando si assegnano gli utenti come agenti del gruppo di risposta, informarli che, se la modalità di privacy è abilitata, devono cercare i contatti "RGS Presence Watcher" e aggiungerli al proprio elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="bb867-116">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="bb867-117">Gli agenti che hanno abilitato la modalità privacy, ma che non hanno "Watcher presenza RGS" nell'elenco contatti, non possono ricevere chiamate al Response Group.</span><span class="sxs-lookup"><span data-stu-id="bb867-117">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="bb867-118">Gli agenti che non hanno la modalità di privacy abilitata non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="bb867-118">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb867-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bb867-119">In This Section</span></span>

  - [<span data-ttu-id="bb867-120">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb867-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="bb867-121">Eliminare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb867-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

