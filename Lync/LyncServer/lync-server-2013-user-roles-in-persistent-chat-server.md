---
title: 'Lync Server 2013: ruoli utente nel server Chat persistente'
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
ms.openlocfilehash: 34087f83a53fd1e52c3d67df4ef50411d6517160
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2eb68-102">Ruoli utente nel server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eb68-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eb68-103">_**Ultimo argomento modificato:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="2eb68-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="2eb68-104">Il server Chat persistente fornisce il concetto di membri consentiti/negati, che si applica alle categorie di chat persistente e ai controlli che possono accedere alle sale di una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="2eb68-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2eb68-105">I membri consentiti/negati in una categoria non sono uguali a quelli di un ruolo <STRONG>membro</STRONG> , che si applica a una chat room persistente.</span><span class="sxs-lookup"><span data-stu-id="2eb68-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="2eb68-p101">Le ricerche visualizzano tutte le chat room aperte e chiuse per le quali l'utente che esegue la ricerca si trova nell'elenco dei membri consentiti/non consentiti. Le chat segrete non vengono visualizzate, a meno che l'utente che esegue la ricerca non ne sia membro. L'utente può eseguire la ricerca solo delle chat di cui è già membro o di quelle per le quali può richiedere l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="2eb68-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="2eb68-p102">L'aspetto principale del concetto di membri consentiti/non consentiti sono gli ethical wall. Ad esempio è frequente negli istituti bancari e finanziari la presenza di vincoli etici che impediscono ai commercianti e agli analisti di condividere le comunicazioni quando implementano criteri e convenzioni. Per ovviare a questo problema, un amministratore può creare le categorie in modo che una categoria consenta la creazione e l'uso delle chat ai commercianti e un'altra agli analisti. Questo vincolo, se progettato nel sistema, non consente di aggiungere un utente come membro della chat se la categoria principale lo impedisce.</span><span class="sxs-lookup"><span data-stu-id="2eb68-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="2eb68-113">Di seguito sono riportati i quattro server di chat persistente dei ruoli utente:</span><span class="sxs-lookup"><span data-stu-id="2eb68-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="2eb68-114">**Creatore:** Utenti che dispongono delle autorizzazioni per la creazione di chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="2eb68-115">Tali utenti sono inclusi nell'elenco Creatori di determinate categorie: possono creare chat room in tali categorie, assegnare l'appartenenza in base alla categoria e affidare la gestione delle chat room a responsabili.</span><span class="sxs-lookup"><span data-stu-id="2eb68-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="2eb68-116">L'utente che crea una chat room viene aggiunto automaticamente all'elenco dei responsabili della chat.</span><span class="sxs-lookup"><span data-stu-id="2eb68-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eb68-p104">Agli utenti con ruolo di Creatore vengono semplicemente concessi i diritti per la creazione di chat room. La promozione automatica al ruolo di Responsabile consente al Creatore di assegnare appartenenze, specificare responsabili ed eseguire altre operazioni per i servizi chat creati.</span><span class="sxs-lookup"><span data-stu-id="2eb68-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="2eb68-119">Questo ruolo ha lo scopo di controllare chi crea le chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e delegare la gestione delle chat room ad altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2eb68-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="2eb68-120">**Responsabile:** Utenti che gestiscono le proprietà di una chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="2eb68-121">I responsabili delle chat room possono modificare l'elenco dei membri (aggiungere o rimuovere membri) e l'elenco dei responsabili delle chat room (aggiungere e rimuovere responsabili).</span><span class="sxs-lookup"><span data-stu-id="2eb68-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="2eb68-122">I responsabili delle chat room possono inoltre aggiungere se stessi all'elenco dei membri o dei relatori (per le chat in modalità auditorium) per poter partecipare alla chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="2eb68-123">Possono inoltre disabilitare le chat room (gli amministratori possono eseguire la ricerca delle chat room disabilitate ed eliminarle in modo permanente).</span><span class="sxs-lookup"><span data-stu-id="2eb68-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="2eb68-124">I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria.</span><span class="sxs-lookup"><span data-stu-id="2eb68-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="2eb68-125">Solo l'amministratore di chat persistente può modificare la categoria dopo che è stata creata la chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2eb68-126">Se il responsabile è anche Creatore per un'altra categoria, potrà cambiare la categoria in una categoria per la quale è autorizzato a creare chat.</span><span class="sxs-lookup"><span data-stu-id="2eb68-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="2eb68-127">**Membro:** Utenti che sono membri di una chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="2eb68-128">Questi utenti possono visualizzare le chat room nella directory (anche se la chat room è segreta), nonché sottoscrivere la chat room (incluse le opzioni per i metadati, ad esempio i messaggi non letti, i filtri ego e i filtri per le parole chiave) e partecipare alla chat room (può postare, a meno che la sala è una sala auditorium in cui solo i relatori possono inserire, ottenere contenuto e ricerca.</span><span class="sxs-lookup"><span data-stu-id="2eb68-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="2eb68-129">Gli utenti che non sono membri della chat room possono cercare la chat room se sono inclusi nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="2eb68-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="2eb68-130">(Non vi è alcuna richiesta di accesso o approvazioni incorporate nel sistema; queste vengono eseguite esternamente tramite posta elettronica, telefono o altre forme di contatto).</span><span class="sxs-lookup"><span data-stu-id="2eb68-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="2eb68-131">**Relatore:** Utenti che possono inviare messaggi a una sala auditorium.</span><span class="sxs-lookup"><span data-stu-id="2eb68-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eb68-132">Il server Chat persistente consente agli utenti di creare e gestire la chat room per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="2eb68-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="2eb68-133">Tuttavia, gli utenti non possono creare o gestire chat room su altri siti all'interno della stessa topologia.</span><span class="sxs-lookup"><span data-stu-id="2eb68-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="2eb68-134">Assicurarsi di specificare i creatori e i responsabili delle chat room per tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2eb68-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="2eb68-135">I ruoli seguenti sono i ruoli di amministratore per il server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="2eb68-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="2eb68-136">**Amministratore di chat persistente (ruolo CsPersistentChatAdministrator):** Si tratta di un nuovo ruolo di controllo di accesso basato sui ruoli (RBAC) per l'amministrazione e la gestione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2eb68-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="2eb68-137">Gli utenti o i gruppi di sicurezza designati come ruolo CsPersistentChatAdministrator sono in grado di amministrare il server Chat persistente utilizzando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2eb68-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="2eb68-138">Il server Chat persistente verifica che l'amministratore di Persistent Chat sia membro del gruppo locale dell'amministratore locale RTC nel server front end server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2eb68-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="2eb68-139">Il ruolo CsPersistentChatAdministrator consente di gestire le chat room (modificare tutte le proprietà inclusi l'appartenenza, i responsabili, le categorie e contrassegnare le chat come disabilitate), nonché creare e gestire le categorie di chat room che stabiliscono chi può creare le chat room e chi può accedervi.</span><span class="sxs-lookup"><span data-stu-id="2eb68-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="2eb68-140">Gli amministratori possono inoltre contrassegnare le chat room come disabilitate e cancellare le chat room che non sono più attive.</span><span class="sxs-lookup"><span data-stu-id="2eb68-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="2eb68-141">Gli amministratori non sono soggetti alle limitazioni previste per i ruoli Creatore o Membri consentiti.</span><span class="sxs-lookup"><span data-stu-id="2eb68-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="2eb68-142">Possono infatti creare qualsiasi tipo di chat room e aggiungere se stessi come membro di qualsiasi chat room.</span><span class="sxs-lookup"><span data-stu-id="2eb68-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="2eb68-143">Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione di Group Chat Server precedente a Lync Server 2013 Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="2eb68-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="2eb68-144">**Amministratore di Lync:** Amministratore globale dell'organizzazione per Lync Server 2013 responsabile della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2eb68-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="2eb68-145">**Operations Manager:** Utente responsabile della gestione delle operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="2eb68-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="2eb68-146">**Sviluppatori e partner di terze parti:** Gli sviluppatori di terze parti estendono il sistema, in particolare fornendo una soluzione ethical wall per le conversazioni di gruppo, il supporto per la conformità e gli strumenti, i client Web/mobili e un Framework per lo sviluppo di bot.</span><span class="sxs-lookup"><span data-stu-id="2eb68-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

