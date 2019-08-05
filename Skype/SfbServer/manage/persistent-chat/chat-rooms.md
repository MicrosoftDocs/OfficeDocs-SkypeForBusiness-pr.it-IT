---
title: Gestire le chat room nel server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Riepilogo: informazioni su come gestire le chat room del server di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 5b7345626a42073bf7ebd0cb5f9900c6e15f0e2b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195928"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="40fe2-103">Gestire le chat room nel server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="40fe2-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="40fe2-104">**Riepilogo:** Informazioni su come gestire le chat room del server di chat persistenti in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="40fe2-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="40fe2-105">La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="40fe2-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="40fe2-106">Una categoria definisce chi può creare o partecipare alle chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="40fe2-107">Prima di tentare di gestire le chat room, leggere le categorie di chat [persistenti, le chat room e i ruoli utente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gestire le categorie nel server di chat persistente in Skype for Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="40fe2-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="40fe2-108">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="40fe2-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="40fe2-109">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="40fe2-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="40fe2-110">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="40fe2-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="40fe2-111">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="40fe2-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="40fe2-112">È possibile configurare e gestire le chat room usando l'interfaccia della riga di comando di Windows PowerShell oppure usando il client Skype for business se si è membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="40fe2-113">Questo argomento descrive come gestire le chat room usando l'interfaccia della riga di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40fe2-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="40fe2-114">Se si vuole gestire le chat room usando il client Skype for business, vedere la guida del client.</span><span class="sxs-lookup"><span data-stu-id="40fe2-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="40fe2-115">Le chat room possono essere uno dei due tipi seguenti: Normal e Auditorium.</span><span class="sxs-lookup"><span data-stu-id="40fe2-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="40fe2-116">Una chat room normale consente a tutti i membri di inserire e leggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="40fe2-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="40fe2-117">Un auditorium è un tipo di chat room in cui possono essere pubblicati solo relatori, ma tutti possono leggere.</span><span class="sxs-lookup"><span data-stu-id="40fe2-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="40fe2-118">Chi può accedere e gestire le chat room dipende dai ruoli degli utenti come segue:</span><span class="sxs-lookup"><span data-stu-id="40fe2-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="40fe2-119">Gli utenti devono essere membri di una chat room per poter pubblicare e leggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="40fe2-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="40fe2-120">I relatori possono inserire le camere in Auditorium.</span><span class="sxs-lookup"><span data-stu-id="40fe2-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="40fe2-121">Gli amministratori possono eliminare il contenuto precedente, ad esempio il contenuto postato prima di una determinata data, da qualsiasi chat room per evitare che il database cresca troppo grande.</span><span class="sxs-lookup"><span data-stu-id="40fe2-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="40fe2-122">Gli amministratori possono anche rimuovere o sostituire i messaggi considerati inappropriati per una particolare chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="40fe2-123">Gli utenti finali, inclusi gli autori dei messaggi, non possono eliminare il contenuto da qualsiasi chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="40fe2-124">I responsabili delle chat room possono apportare modifiche a tutte le proprietà della chat room, incluse le camere disabilitate.</span><span class="sxs-lookup"><span data-stu-id="40fe2-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="40fe2-125">I responsabili non possono tuttavia eliminare una chat room o modificare la categoria di una chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="40fe2-126">Solo gli amministratori possono eliminare una chat room dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="40fe2-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="40fe2-127">È possibile configurare e gestire le chat room usando i cmdlet di Windows PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="40fe2-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="40fe2-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="40fe2-128">**Cmdlet**</span></span>|<span data-ttu-id="40fe2-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="40fe2-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40fe2-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="40fe2-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="40fe2-131">Creare una nuova chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="40fe2-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="40fe2-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="40fe2-133">Configurare le impostazioni per una sala esistente; assegnare gli utenti e i gruppi di utenti alla chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="40fe2-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="40fe2-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="40fe2-135">Recuperare informazioni sulle sale</span><span class="sxs-lookup"><span data-stu-id="40fe2-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="40fe2-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="40fe2-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="40fe2-137">Cancellare una chat room o i messaggi da una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="40fe2-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="40fe2-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="40fe2-139">Rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="40fe2-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="40fe2-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="40fe2-141">Rimuovere i messaggi da una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="40fe2-142">Puoi usare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat room esistente, incluso l'aggiunta di utenti alla chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="40fe2-143">È possibile configurare i parametri seguenti per le chat room:</span><span class="sxs-lookup"><span data-stu-id="40fe2-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="40fe2-144">Disabilitato.</span><span class="sxs-lookup"><span data-stu-id="40fe2-144">Disabled.</span></span> <span data-ttu-id="40fe2-145">Consente di disabilitare o abilitare una chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="40fe2-146">Inviti.</span><span class="sxs-lookup"><span data-stu-id="40fe2-146">Invitations.</span></span> <span data-ttu-id="40fe2-147">Consente di abilitare o disabilitare gli inviti alle chat room, che vengono usati per avvisare gli utenti quando sono stati aggiunti come membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="40fe2-148">L'impostazione predefinita per gli inviti in Inherit, che ha causato la chat room ad adottare l'impostazione dell'invito configurata nella categoria a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="40fe2-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="40fe2-149">La configurazione degli inviti impostato su false a livello di chat room consente di eseguire l'override dell'impostazione Category.</span><span class="sxs-lookup"><span data-stu-id="40fe2-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="40fe2-150">Privacy.</span><span class="sxs-lookup"><span data-stu-id="40fe2-150">Privacy.</span></span> <span data-ttu-id="40fe2-151">Consente di specificare se una chat room è aperta, chiusa o segreta.</span><span class="sxs-lookup"><span data-stu-id="40fe2-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="40fe2-152">Le sale aperte possono essere cercate e accessibili da chiunque.</span><span class="sxs-lookup"><span data-stu-id="40fe2-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="40fe2-153">Le sale chiuse possono essere cercate da chiunque, ma è possibile accedervi solo dai membri.</span><span class="sxs-lookup"><span data-stu-id="40fe2-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="40fe2-154">Le camere segrete possono essere cercate e accessibili solo dai membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="40fe2-155">Per impostazione predefinita, ogni nuova sala viene inizialmente configurata come chiusa.</span><span class="sxs-lookup"><span data-stu-id="40fe2-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="40fe2-156">Tipo.</span><span class="sxs-lookup"><span data-stu-id="40fe2-156">Type.</span></span> <span data-ttu-id="40fe2-157">Consente di specificare se una chat room è una sala normale, che accetta i messaggi inviati da qualsiasi membro o una sala auditorium, che accetta i messaggi inviati solo da un relatore.</span><span class="sxs-lookup"><span data-stu-id="40fe2-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="40fe2-158">AddIn.</span><span class="sxs-lookup"><span data-stu-id="40fe2-158">Addin.</span></span> <span data-ttu-id="40fe2-159">Consente di associare un componente aggiuntivo configurato in precedenza con una chat room, che consente di visualizzare il contenuto dell'URL per i membri durante la partecipazione.</span><span class="sxs-lookup"><span data-stu-id="40fe2-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="40fe2-160">Oltre ai parametri descritti sopra, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare utenti alla chat room come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="40fe2-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="40fe2-161">Membri.</span><span class="sxs-lookup"><span data-stu-id="40fe2-161">Members.</span></span> <span data-ttu-id="40fe2-162">Configura l'appartenenza per la chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-162">Configures membership for the chat room.</span></span> <span data-ttu-id="40fe2-163">È possibile aggiungere o rimuovere singoli o più membri usando un singolo cmdlet specificando l'indirizzo SIP degli utenti.</span><span class="sxs-lookup"><span data-stu-id="40fe2-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="40fe2-164">Per consentire l'aggiunta di utenti in blocco, è anche possibile specificare unità organizzative o gruppi di distribuzione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="40fe2-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="40fe2-165">Manager.</span><span class="sxs-lookup"><span data-stu-id="40fe2-165">Managers.</span></span> <span data-ttu-id="40fe2-166">Consente di assegnare i responsabili alla chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="40fe2-167">I manager hanno le autorizzazioni per definire l'appartenenza a una chat room insieme ad altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="40fe2-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="40fe2-168">Relatori.</span><span class="sxs-lookup"><span data-stu-id="40fe2-168">Presenters.</span></span> <span data-ttu-id="40fe2-169">Consente di assegnare relatori a una chat room dell'Auditorium.</span><span class="sxs-lookup"><span data-stu-id="40fe2-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="40fe2-170">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="40fe2-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="40fe2-171">Creare una nuova sala</span><span class="sxs-lookup"><span data-stu-id="40fe2-171">Create a new room</span></span>

<span data-ttu-id="40fe2-172">È possibile creare una nuova sala usando il cmdlet **New-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="40fe2-173">Ad esempio, il comando seguente crea una nuova chat room denominata room ITChatRoom nel pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="40fe2-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="40fe2-174">In questo esempio, la chat room viene aggiunta alla categoria IT:</span><span class="sxs-lookup"><span data-stu-id="40fe2-174">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="40fe2-175">**Nota:** PersistentChatPoolFqdn non è necessario se una delle operazioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="40fe2-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="40fe2-176">Esiste un solo pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="40fe2-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="40fe2-177">Fornisci un nome di dominio completo del pool alla categoria.</span><span class="sxs-lookup"><span data-stu-id="40fe2-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="40fe2-178">Puoi specificare un nome di dominio completo del pool per l'aggiunta della chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="40fe2-179">Configurare una sala esistente</span><span class="sxs-lookup"><span data-stu-id="40fe2-179">Configure an existing room</span></span>

<span data-ttu-id="40fe2-180">È possibile configurare una sala esistente usando il cmdlet **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="40fe2-181">Ad esempio, il comando seguente assegna User1 come membro e relatore e User2 come Manager della sala testCat Auditorium:</span><span class="sxs-lookup"><span data-stu-id="40fe2-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="40fe2-182">Nell'esempio seguente vengono aggiunti tutti gli utenti dell'unità organizzativa NorthAmericaUsers in Active Directory alla chat room di NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="40fe2-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="40fe2-183">Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:</span><span class="sxs-lookup"><span data-stu-id="40fe2-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="40fe2-184">Disabilitare o abilitare una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-184">Disable or enable a room</span></span>

<span data-ttu-id="40fe2-185">Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitando il problema.</span><span class="sxs-lookup"><span data-stu-id="40fe2-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="40fe2-186">Quando una chat room è disabilitata, tutti i membri vengono immediatamente disconnessi dalla sala.</span><span class="sxs-lookup"><span data-stu-id="40fe2-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="40fe2-187">Dopo la disattivazione di una chat room, gli utenti non possono raggiungerla o trovarla nelle ricerche in chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="40fe2-188">Se la cronologia della chat room persiste, il contenuto viene mantenuto quando la chat room è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="40fe2-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="40fe2-189">Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo di permanenza della chat room in uno stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="40fe2-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="40fe2-190">Se in seguito si Abilita la chat room, gli utenti possono cercare i messaggi inviati prima della disattivazione della chat room.</span><span class="sxs-lookup"><span data-stu-id="40fe2-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="40fe2-191">Per informazioni sulla configurazione della cronologia delle chat room, vedere [gestire le categorie nel server di chat persistente in Skype for Business server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="40fe2-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="40fe2-192">Se una chat room è disabilitata, viene mantenuta l'elenco di appartenenza e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="40fe2-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="40fe2-193">Come amministratore, puoi abilitare una chat room disattivata e non devi ricreare manualmente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="40fe2-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="40fe2-194">È possibile disabilitare una chat room usando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro disabled su true:</span><span class="sxs-lookup"><span data-stu-id="40fe2-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="40fe2-195">Per abilitare una chat room, imposta il parametro disabled su false:</span><span class="sxs-lookup"><span data-stu-id="40fe2-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="40fe2-196">Ottenere informazioni sulle sale</span><span class="sxs-lookup"><span data-stu-id="40fe2-196">Get information about rooms</span></span>

<span data-ttu-id="40fe2-197">Per ottenere informazioni sulle sale configurate per l'uso nell'organizzazione, è possibile usare il cmdlet **Get-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="40fe2-198">Il comando seguente restituisce informazioni su tutte le chat room configurate per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="40fe2-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="40fe2-199">Rimuovere tutto il contenuto da una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-199">Remove all content from a room</span></span>

<span data-ttu-id="40fe2-200">È possibile rimuovere il contenuto da una chat room usando il cmdlet **Clear-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="40fe2-201">Ad esempio, con il comando seguente viene rimosso tutto il contenuto della chat room room ITChatRoom che è stato aggiunto alla sala prima o prima del 1 ° marzo 2015:</span><span class="sxs-lookup"><span data-stu-id="40fe2-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="40fe2-202">Rimuovere un messaggio da una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-202">Remove a message from a room</span></span>

<span data-ttu-id="40fe2-203">È possibile rimuovere uno o più messaggi nel database della chat persistente e, facoltativamente, sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore usando il cmdlet **Remove-CsPersistentChatMessage** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="40fe2-204">Ad esempio, il comando seguente rimuove tutti i messaggi della chat room di room ITChatRoom inviati dall'utente kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="40fe2-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="40fe2-205">L'esempio seguente sostituisce i messaggi rimossi con la nota che il messaggio non è più disponibile:</span><span class="sxs-lookup"><span data-stu-id="40fe2-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="40fe2-206">Rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="40fe2-206">Remove a room</span></span>

<span data-ttu-id="40fe2-207">Per rimuovere una chat room, è possibile usare il cmdlet **Remove-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="40fe2-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="40fe2-208">Ad esempio, il comando seguente rimuove la chat room RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="40fe2-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="40fe2-209">Trasferire una sala da una categoria a un'altra</span><span class="sxs-lookup"><span data-stu-id="40fe2-209">Move a room from one category to another</span></span>

<span data-ttu-id="40fe2-210">Se un Manager di chat room ha privilegi di **autore** in un'altra categoria, può trasferire la sala da una categoria a un'altra.</span><span class="sxs-lookup"><span data-stu-id="40fe2-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="40fe2-211">La sala non viene eliminata e ricreata.</span><span class="sxs-lookup"><span data-stu-id="40fe2-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="40fe2-212">Si tratta di un cambiamento di associazione all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="40fe2-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="40fe2-213">La modifica di una categoria di chat room deve essere eseguita raramente e con cautela.</span><span class="sxs-lookup"><span data-stu-id="40fe2-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="40fe2-214">Una categoria determina l'appartenenza consentita per la chat room, quindi quando una chat room viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso di sistema (SACL) che non sono più supportati dalla nuova categoria vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="40fe2-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="40fe2-215">Ad esempio, se un utente è stato un membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.</span><span class="sxs-lookup"><span data-stu-id="40fe2-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

