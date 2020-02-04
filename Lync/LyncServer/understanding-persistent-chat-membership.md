---
title: Informazioni sull'appartenenza di Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="a235c-102">Informazioni sull'appartenenza di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="a235c-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a235c-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a235c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a235c-104">L'accesso degli utenti alle chat room permanenti viene gestito dall'appartenenza; Gli utenti devono essere membri di una chat room per poter pubblicare e leggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a235c-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="a235c-105">Solo i **relatori** con un'affiliazione designata con chat room possono usare la **registrazione nelle sale dell'Auditorium**.</span><span class="sxs-lookup"><span data-stu-id="a235c-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="a235c-106">Un auditorium è un tipo di chat room (l'altro è **normale**), dove possono essere pubblicati solo relatori e tutti possono leggere.</span><span class="sxs-lookup"><span data-stu-id="a235c-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="a235c-107">Inoltre, le chat room permanenti funzionano in base alle regole di una categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="a235c-108">Per informazioni dettagliate sulle categorie, vedere [gestione di categorie, sale e componenti aggiuntivi in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e anche le sezioni "come funziona l'ambito della categoria" e "strategie per la categoria della sala" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a235c-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="a235c-109">Un amministratore della chat persistente può creare e gestire le categorie delle chat room.</span><span class="sxs-lookup"><span data-stu-id="a235c-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="a235c-110">Nell'ambito della creazione e della gestione delle categorie di chat room, l'amministratore della chat persistente può configurare le entità (gruppi, contenitori e utenti di servizi di dominio Active Directory) che hanno accesso a membri o creatori di chat room di una specifica categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="a235c-111">Servizi di dominio Active Directory e chat persistenti</span><span class="sxs-lookup"><span data-stu-id="a235c-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="a235c-112">Il server di chat persistente si basa su Active Directory per il pool di utenti di chat permanenti interni.</span><span class="sxs-lookup"><span data-stu-id="a235c-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="a235c-113">Dopo aver installato la chat persistente (client), è possibile aggiungere i domini di utenti e gruppi utenti alla categoria sala.</span><span class="sxs-lookup"><span data-stu-id="a235c-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="a235c-114">È quindi possibile aggiungere questi utenti e gruppi all'appartenenza delle categorie della sala.</span><span class="sxs-lookup"><span data-stu-id="a235c-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a235c-115">Devi assicurarti che non ci siano nomi duplicati per gli utenti che vogliono apportare modifiche alle chat room persistenti.</span><span class="sxs-lookup"><span data-stu-id="a235c-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="a235c-116">Se sono presenti nomi utente duplicati, modificarli in nomi diversi per sbloccare gli utenti da apportare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="a235c-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="a235c-117">Se un utente ha nomi duplicati in Active Directory e prova a apportare modifiche nelle rispettive sale, viene visualizzato un messaggio di errore che chiede all'utente di contattare l'amministratore per la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="a235c-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="a235c-118">Funzionamento dell'ambito delle categorie</span><span class="sxs-lookup"><span data-stu-id="a235c-118">How Category Scoping Works</span></span>

<span data-ttu-id="a235c-119">Una categoria specifica tutti gli utenti e i gruppi che possono essere membri in un elenco di appartenenza di una chat room persistente in quella categoria, in base alla relativa proprietà **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="a235c-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="a235c-120">Se ad esempio si imposta la **AllowedMembers** della categoria su contoso.com, è possibile aggiungere un gruppo o un utente a *Contoso* come membro delle chat room della categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="a235c-121">Se si imposta **AllowedMembers** su una categoria per le *vendite*, solo i gruppi e gli utenti della lista di distribuzione possono essere aggiunti come membri alle chat room della categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="a235c-122">Analogamente, la proprietà **Creators** consente di controllare chi può creare chat room in quella categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="a235c-123">Dopo la creazione della chat room, tutti i membri del gruppo **AllowedMembers** possono essere designati come **Manager** per le operazioni di gestione in corso nelle sale, ad esempio per le modifiche e le approvazioni.</span><span class="sxs-lookup"><span data-stu-id="a235c-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="a235c-124">La definizione di **AllowedMembers** e **Creators** per una categoria ha i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a235c-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="a235c-125">Tutte le chat room di questa categoria sono associate alle restrizioni impostate a livello di categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="a235c-126">Puoi usare questa funzione per separare le chat room in base alle esigenze aziendali e ai criteri di accesso.</span><span class="sxs-lookup"><span data-stu-id="a235c-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="a235c-127">Un utente nell'elenco **Creators** può creare nuove chat room in quella categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="a235c-128">Se vuoi implementare un sistema in cui un numero limitato di personale dell'organizzazione può creare chat room, questo controllo può essere usato per soddisfare tale requisito.</span><span class="sxs-lookup"><span data-stu-id="a235c-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="a235c-129">Strategie per le categorie di camere</span><span class="sxs-lookup"><span data-stu-id="a235c-129">Room Category Strategies</span></span>

<span data-ttu-id="a235c-130">Il **AllowedMembers** di una categoria deve includere tutti gli utenti che useranno qualsiasi chat room persistente in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="a235c-131">A seconda dei requisiti per proteggere i dati aziendali e garantire il livello di accesso appropriato, è consigliabile definire una o più categorie per specificare chi può cercare e partecipare alle sale.</span><span class="sxs-lookup"><span data-stu-id="a235c-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="a235c-132">Se si vuole consentire solo un determinato set di utenti (helpdesk centrale o solo dipendenti a tempo pieno) per la creazione di sale, è possibile applicare l'ambito agli **autori** di una categoria per soddisfare tale requisito.</span><span class="sxs-lookup"><span data-stu-id="a235c-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="a235c-133">Le categorie possono essere usate anche per creare muri etici.</span><span class="sxs-lookup"><span data-stu-id="a235c-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="a235c-134">I muri etici impediscono qualsiasi conflitto di interessi in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a235c-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="a235c-135">Ad esempio, un amministratore può creare chat room in una categoria solo per gli operatori commerciali, mentre le chat room in un'altra categoria possono essere usate solo dagli analisti.</span><span class="sxs-lookup"><span data-stu-id="a235c-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a235c-136">In Lync Server 2013, Persistent Chat Server, non è supportato l'accesso agli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="a235c-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="a235c-137">Se sono presenti chat provenienti da utenti federati nelle versioni precedenti del server di chat persistente, verranno migrati.</span><span class="sxs-lookup"><span data-stu-id="a235c-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="a235c-138">Gli utenti federati vengono aggiunti come entità disabilitate.</span><span class="sxs-lookup"><span data-stu-id="a235c-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="a235c-139">Restringere i membri ai gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="a235c-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="a235c-140">Quando si aggiunge un dominio a una categoria, i gruppi di utenti il cui oggetto gruppo è contenuto in tale dominio sono disponibili in modo che sia possibile specificarli come membri di sale della categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="a235c-141">Come regola generale, è consigliabile usare i contenitori di Active Directory, ad esempio i domini e le unità organizzative, per definire i **AllowedMembers** e i **creatori**di una categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="a235c-142">Puoi aggiungere oggetti da qualsiasi dominio a un elenco **AllowedMembers** o **Creators** .</span><span class="sxs-lookup"><span data-stu-id="a235c-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="a235c-143">Solo gli oggetti inclusi nell'elenco **AllowedMembers** o **Creators** possono essere aggiunti alle sale di tale categoria.</span><span class="sxs-lookup"><span data-stu-id="a235c-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

