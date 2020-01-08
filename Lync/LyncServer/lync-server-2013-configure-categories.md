---
title: 'Lync Server 2013: Configurare le categorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="247d0-102">Configurare le categorie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="247d0-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="247d0-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="247d0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="247d0-104">Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione **categoria** della pagina della **chat persistente** per configurare le categorie.</span><span class="sxs-lookup"><span data-stu-id="247d0-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="247d0-105">Una categoria di chat room persistente è una struttura logica per l'organizzazione di chat room.</span><span class="sxs-lookup"><span data-stu-id="247d0-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="247d0-106">Una categoria definisce un insieme predefinito di elenchi di controllo di accesso (ACL) per controllare gli utenti e i gruppi di utenti che possono creare o unirsi alle chat room.</span><span class="sxs-lookup"><span data-stu-id="247d0-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="247d0-107">È possibile usare le categorie per applicare ethical wall tra diverse suddivisioni delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="247d0-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="247d0-108">Le categorie di chat room possono contenere chat room, ma non altre categorie.</span><span class="sxs-lookup"><span data-stu-id="247d0-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="247d0-109">Ogni categoria descrive il relativo contenuto con metadati, come Name e Description.</span><span class="sxs-lookup"><span data-stu-id="247d0-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="247d0-110">La categoria presenta inoltre proprietà che possono essere impostate per controllare il comportamento delle chat room ad essa appartenenti, ad esempio se consentono Invitations o File Uploads oppure contengono Chat History.</span><span class="sxs-lookup"><span data-stu-id="247d0-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="247d0-111">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="247d0-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="247d0-112">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="247d0-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="247d0-113">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="247d0-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="247d0-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="247d0-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="247d0-115">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="247d0-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="247d0-116">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="247d0-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="247d0-117">Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="247d0-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="247d0-118">Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="247d0-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="247d0-119">Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="247d0-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="247d0-120">In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui deve essere creata la categoria.</span><span class="sxs-lookup"><span data-stu-id="247d0-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="247d0-121">Il servizio è il pool di server di chat persistente usato dalla chat persistente (client) per identificare a quale pool appartiene la categoria.</span><span class="sxs-lookup"><span data-stu-id="247d0-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="247d0-122">Una categoria può appartenere a un solo pool di server di chat persistente e non può essere spostata in un'altra o condivisa con un altro pool.</span><span class="sxs-lookup"><span data-stu-id="247d0-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="247d0-123">In **Nuova categoria** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="247d0-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="247d0-124">In **Nome** specificare un nome per la nuova categoria di chat.</span><span class="sxs-lookup"><span data-stu-id="247d0-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="247d0-125">In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.</span><span class="sxs-lookup"><span data-stu-id="247d0-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="247d0-126">Per controllare se gli inviti possono essere abilitati per le chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita invito** .</span><span class="sxs-lookup"><span data-stu-id="247d0-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="247d0-127">Se selezionata, le camere di questa categoria possono avere inviti o disattivarli; Se deselezionata, le camere di questa categoria non possono avere inviti.</span><span class="sxs-lookup"><span data-stu-id="247d0-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="247d0-128">Se una sala contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="247d0-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="247d0-p107">Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.</span><span class="sxs-lookup"><span data-stu-id="247d0-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="247d0-131">Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che usano Office Communications Server 2007&nbsp;R2 Group Chat Server o Lync Server 2010, Group Chat possono pubblicare file in una sala.</span><span class="sxs-lookup"><span data-stu-id="247d0-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="247d0-132">Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="247d0-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="247d0-133">Per controllare la cronologia chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat** .</span><span class="sxs-lookup"><span data-stu-id="247d0-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="247d0-134">Se selezionata, le chat room diventano permanenti; in caso contrario, i messaggi di chat non vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="247d0-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="247d0-135">Se è abilitata la conformità, le chat room verranno salvate in conformità, ma gli utenti non potranno accedere ai messaggi meno recenti.</span><span class="sxs-lookup"><span data-stu-id="247d0-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="247d0-136">Questa opzione può essere usata per le sale designate per le collaborazioni ad hoc in tempo reale che non richiedono la cronologia della chat per essere rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="247d0-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="247d0-137">In **Modifica categoria** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="247d0-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="247d0-138">In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria.</span><span class="sxs-lookup"><span data-stu-id="247d0-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="247d0-139">Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).</span><span class="sxs-lookup"><span data-stu-id="247d0-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="247d0-140">In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri negati dalla sala.</span><span class="sxs-lookup"><span data-stu-id="247d0-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="247d0-141">In **appartenenza**, nella sezione **Creators** , aggiungere o rimuovere utenti e altre entità Active Directory associate agli autori per la categoria.</span><span class="sxs-lookup"><span data-stu-id="247d0-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="247d0-142">Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.</span><span class="sxs-lookup"><span data-stu-id="247d0-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="247d0-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="247d0-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

