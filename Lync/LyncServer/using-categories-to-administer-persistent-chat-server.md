---
title: Utilizzo di categorie per l'amministrazione del server Chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73801c006f7ef5487960628d0f981809cdfd2d38
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="a7c58-102">Utilizzo di categorie per l'amministrazione del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="a7c58-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7c58-103">_**Ultimo argomento modificato:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="a7c58-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="a7c58-104">La distribuzione del server Chat persistente può ospitare molte chat room persistenti simultanee.</span><span class="sxs-lookup"><span data-stu-id="a7c58-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="a7c58-105">Le chat room possono essere organizzate in una serie di categorie sul server.</span><span class="sxs-lookup"><span data-stu-id="a7c58-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="a7c58-106">Ogni chat room appartiene a una categoria, da cui eredita alcune impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a7c58-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="a7c58-107">In questo modo viene creata una struttura che consente di identificare le conversazioni in base alle esigenze aziendali e di facilitare l'amministrazione delegata e la gestione semplificata.</span><span class="sxs-lookup"><span data-stu-id="a7c58-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7c58-108">Anche se molte delle funzionalità di gestione delle chat room sono disponibili nei computer che eseguono la chat persistente (client Lync) per l'utente, gli amministratori di chat persistente (nel ruolo <STRONG>ruolo CsPersistentChatAdministrator</STRONG> ) devono utilizzare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare o gestire le categorie.</span><span class="sxs-lookup"><span data-stu-id="a7c58-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="a7c58-109">Gli amministratori di chat persistente utilizzano i cmdlet del pannello di controllo di Lync Server o di Windows PowerShell per creare e gestire categorie e per progettare l'accesso per le chat room per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a7c58-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="a7c58-110">I responsabili delle chat room permanenti, che hanno la possibilità di gestire una o più chat room, possono utilizzare il client Lync per avviare un'applicazione Web di gestione sala per creare e gestire le sale (oppure i clienti possono creare soluzioni e flussi di lavoro personalizzati per essere richiamati).</span><span class="sxs-lookup"><span data-stu-id="a7c58-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="a7c58-111">Gli amministratori di chat persistente possono anche utilizzare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare e gestire le sale.</span><span class="sxs-lookup"><span data-stu-id="a7c58-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7c58-112">Una chat room persistente non può avere lo stesso nome di una categoria di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a7c58-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="a7c58-113">Chat room managers can make changes to all chat room properties, except for changing the category of the room.</span><span class="sxs-lookup"><span data-stu-id="a7c58-113">Chat room managers can make changes to all chat room properties, except for changing the category of the room.</span></span> <span data-ttu-id="a7c58-114">They cannot be restricted from performing the following actions:</span><span class="sxs-lookup"><span data-stu-id="a7c58-114">They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="a7c58-115">Disabilitazione di una chat room</span><span class="sxs-lookup"><span data-stu-id="a7c58-115">Disabling a chat room</span></span>

  - <span data-ttu-id="a7c58-116">Modifica del nome di una chat room</span><span class="sxs-lookup"><span data-stu-id="a7c58-116">Changing a chat room name</span></span>

  - <span data-ttu-id="a7c58-117">Modifica della descrizione di una chat room</span><span class="sxs-lookup"><span data-stu-id="a7c58-117">Changing a chat room description</span></span>

  - <span data-ttu-id="a7c58-118">Modifica del tipo di chat room (Auditorium o Normale)</span><span class="sxs-lookup"><span data-stu-id="a7c58-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="a7c58-119">Modifica della privacy di una chat (aperta, chiusa o segreta)</span><span class="sxs-lookup"><span data-stu-id="a7c58-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="a7c58-120">Aggiunta o rimozione di membri</span><span class="sxs-lookup"><span data-stu-id="a7c58-120">Adding or removing members</span></span>

  - <span data-ttu-id="a7c58-121">Aggiunta o rimozione di responsabili della chat room</span><span class="sxs-lookup"><span data-stu-id="a7c58-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="a7c58-122">Aggiunta o rimozione di componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="a7c58-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="a7c58-123">Modificare impostazioni come gli inviti (a seconda di quanto consentito dalla categoria)</span><span class="sxs-lookup"><span data-stu-id="a7c58-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="a7c58-124">Amministrazione delegata</span><span class="sxs-lookup"><span data-stu-id="a7c58-124">Delegated Administration</span></span>

<span data-ttu-id="a7c58-125">La creazione e la gestione di chat room permanenti è molto più facile con il corretto utilizzo delle categorie.</span><span class="sxs-lookup"><span data-stu-id="a7c58-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="a7c58-126">Un amministratore di chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti per le chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="a7c58-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="a7c58-127">Gli amministratori di chat persistente creano e gestiscono le categorie utilizzando i cmdlet di Lync Server Control Panel o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7c58-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="a7c58-128">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span><span class="sxs-lookup"><span data-stu-id="a7c58-128">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="a7c58-129">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span><span class="sxs-lookup"><span data-stu-id="a7c58-129">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="a7c58-130">Le chat room create in una categoria sono soggette ai criteri e alle impostazioni applicati dalla categoria, ad esempio i membri autorizzati, gli utenti che possono gestire la chat room, se sono consentiti caricamenti di file, se è previsto l'invio di inviti e così via.</span><span class="sxs-lookup"><span data-stu-id="a7c58-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

