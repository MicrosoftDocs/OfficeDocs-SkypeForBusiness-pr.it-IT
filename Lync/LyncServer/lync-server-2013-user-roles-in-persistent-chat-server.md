---
title: 'Lync Server 2013: ruoli utente nel server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ca7cb-102">Ruoli utente nel server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca7cb-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca7cb-103">_**Argomento Ultima modifica:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="ca7cb-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="ca7cb-104">Il server di chat persistente fornisce il concetto di membri consentiti/negati, che si applica alle categorie di chat persistenti e ai controlli che possono accedere alle camere in una specifica categoria.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca7cb-105">I membri consentiti/negati in una categoria non corrispondono a quelli di un ruolo <STRONG>membro</STRONG> , che si applica a una chat room persistente.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="ca7cb-106">Le ricerche visualizzano tutte le chat room aperte e chiuse per cui l'utente che esegue la ricerca si trova nell'elenco dei membri allowed/denied.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="ca7cb-107">Le sale segrete non vengono visualizzate a meno che l'utente che esegue la ricerca non sia un membro della sala segreta.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="ca7cb-108">L'utente può cercare solo le sale di cui è già membro o quelle per cui può richiedere l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="ca7cb-109">La logica principale per il concetto di membri consentiti/negati è l'ethical wall.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="ca7cb-110">Ad esempio, è comune negli istituti bancari e finanziari avere confini etici che impediscono agli operatori commerciali e agli analisti di condividere comunicazioni durante l'implementazione di criteri e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="ca7cb-111">Per risolvere questo requisito, un amministratore può creare categorie in modo che una categoria consenta la creazione e l'uso di sale dagli operatori commerciali, mentre un'altra categoria consente la creazione e l'uso di sale dagli analisti.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="ca7cb-112">Con questo vincolo è progettato nel sistema impedisce l'aggiunta di un utente come membro della sala se la categoria padre lo impedisce.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="ca7cb-113">Di seguito sono riportati i quattro ruoli utente server di chat persistente:</span><span class="sxs-lookup"><span data-stu-id="ca7cb-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="ca7cb-114">**Creatore:** Utenti che dispongono delle autorizzazioni per creare chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="ca7cb-115">Questi utenti si trovano nell'elenco Creators di alcune categorie: possono creare chat room in quella categoria e possono anche assegnare l'appartenenza in base alla categoria e assegnare i Manager per gestire la chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="ca7cb-116">L'utente che crea una chat room viene automaticamente aggiunto come Manager della sala.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca7cb-117">Essere un creatore fornisce semplicemente i diritti per la creazione di chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-117">Being a Creator simply provides rights for creating chat rooms.</span></span> <span data-ttu-id="ca7cb-118">È la promozione automatica di Manager che consente al creatore di perfezionare ulteriormente le appartenenze, i Manager e così via, nei servizi di chat creati.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-118">It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="ca7cb-119">Questo ruolo esiste per darvi la possibilità di controllare chi crea chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e quindi delegare la gestione delle chat room ad altri utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="ca7cb-120">**Manager:** Utenti che gestiscono le proprietà di una chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="ca7cb-121">I responsabili della chat room possono modificare l'elenco dei membri (aggiungere e rimuovere membri) e modificare l'elenco dei responsabili della chat room (Aggiungi e Rimuovi Manager).</span><span class="sxs-lookup"><span data-stu-id="ca7cb-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="ca7cb-122">I responsabili della chat room possono aggiungersi all'elenco membri o relatori (per le sale Auditorium) in modo che possano partecipare alla chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="ca7cb-123">I responsabili delle chat room possono anche disabilitare le chat room (gli amministratori possono eseguire query per le chat room disabilitate e possono eliminarle definitivamente).</span><span class="sxs-lookup"><span data-stu-id="ca7cb-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="ca7cb-124">I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria della chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="ca7cb-125">Solo l'amministratore della chat persistente può modificare la categoria dopo la creazione della chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ca7cb-126">Se il responsabile è anche un creatore in un'altra categoria, può modificare la categoria in uno dei casi in cui è autorizzato a creare sale.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="ca7cb-127">**Member:** Utenti membri di una chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="ca7cb-128">Questi utenti possono vedere le chat room nella directory (anche se la chat room è segreta), nonché abbonarsi alla chat room (incluse le opzioni per i metadati, ad esempio i messaggi non letti, i filtri ego e i filtri per le parole chiave), e partecipare alla chat room (può pubblicare, a meno che la sala è una sala auditorium in cui possono essere pubblicati solo relatori, ottenere contenuti e cercare.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="ca7cb-129">Gli utenti che non sono membri della chat room possono cercare la chat room se si trovano nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="ca7cb-130">(Non esiste alcuna richiesta di accesso o approvazione incorporata nel sistema; questi vengono eseguiti esternamente tramite posta elettronica, telefono o altre forme di contatto).</span><span class="sxs-lookup"><span data-stu-id="ca7cb-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="ca7cb-131">**Relatore:** Utenti che possono inserire un post in una sala auditorium.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca7cb-132">Il server di chat persistente consente agli utenti di creare e gestire chat room per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="ca7cb-133">Gli utenti non possono tuttavia creare o gestire chat room in altri siti all'interno della stessa topologia.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="ca7cb-134">Assicurati di specificare i creatori e i responsabili della chat room per tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="ca7cb-135">I ruoli seguenti sono ruoli di amministratore per il server di chat persistente:</span><span class="sxs-lookup"><span data-stu-id="ca7cb-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="ca7cb-136">**Amministratore della chat persistente (CsPersistentChatAdministrator):** Questo è un nuovo ruolo di controllo di accesso basato sui ruoli (RBAC) per amministrare e gestire il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="ca7cb-137">Gli utenti o i gruppi di sicurezza designati come CsPersistentChatAdministrator possono amministrare il server di chat persistente usando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="ca7cb-138">Il server di chat persistente controlla che l'amministratore della chat persistente sia membro del gruppo locale dell'amministratore locale RTC nel server front end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="ca7cb-139">Il ruolo CsPersistentChatAdministrator può gestire le chat room (modifica tutte le proprietà, inclusi l'appartenenza, i Manager, le categorie, le camere contrassegnate come disabilitate), nonché la creazione e la gestione di categorie di chat che definiscono chi può creare e accedere alle chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="ca7cb-140">Gli amministratori possono anche contrassegnare le chat room come disattivate e pulire le chat room non più attive.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="ca7cb-141">Gli amministratori non sono soggetti alle restrizioni per i creatori o i membri consentiti.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="ca7cb-142">Gli amministratori possono creare qualsiasi tipo di chat room e aggiungersi come membri di una chat room.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="ca7cb-143">Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione di Group Chat Server meno recente alla chat persistente di Lync Server 2013 Server.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="ca7cb-144">**Amministratore di Lync:** Amministratore globale dell'organizzazione per Lync Server 2013 responsabile della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="ca7cb-145">**Operations Manager:** Utente responsabile della gestione delle operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="ca7cb-146">**Sviluppatori e partner di terze parti:** Gli sviluppatori di terze parti estendono il sistema, in particolare fornendo una soluzione di Wall Ethical per le conversazioni di gruppo, il supporto della conformità e gli strumenti, i client Web/mobili e un Framework per lo sviluppo di bot.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

