---
title: Gestire le chat room nel server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Riepilogo: informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815106"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="6a6ec-103">Gestire le chat room nel server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a6ec-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6a6ec-104">**Riepilogo:** Informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6a6ec-105">La creazione e la gestione delle chat room è molto più semplice con il corretto utilizzo delle categorie.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="6a6ec-106">Una categoria definisce gli utenti che possono creare o partecipare alle chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="6a6ec-107">Prima di tentare di gestire le chat room, leggere categorie di chat [persistente, chat room e ruoli utente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gestire le categorie nel server Chat persistente in Skype for Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="6a6ec-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a6ec-108">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6a6ec-109">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="6a6ec-110">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="6a6ec-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6a6ec-111">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="6a6ec-112">È possibile configurare e gestire le chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell oppure utilizzando il client Skype for business, se si è membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="6a6ec-113">In questo argomento viene descritto come gestire le chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="6a6ec-114">Se si desidera gestire le chat room utilizzando il client Skype for business, vedere la guida del client.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="6a6ec-115">Le chat room possono essere tra due tipi: Normal e Auditorium.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="6a6ec-116">Una chat room normale consente a tutti i membri di inserire e leggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="6a6ec-117">Un auditorium è un tipo di chat room in cui possono essere pubblicati solo i relatori, ma ognuno può leggere.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="6a6ec-118">Gli utenti che possono accedere e gestire le chat room dipendono dai ruoli degli utenti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="6a6ec-119">Gli utenti devono essere membri di una chat room per poter postare e leggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="6a6ec-120">I relatori sono autorizzati a pubblicare nelle sale Auditorium.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="6a6ec-121">Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="6a6ec-122">Gli amministratori possono anche rimuovere o sostituire i messaggi considerati inadeguati per una chat room specifica.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="6a6ec-123">Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="6a6ec-124">I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, tra cui la disattivazione delle sale.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="6a6ec-125">Tuttavia, i Manager non possono eliminare una chat room o modificare la categoria di una chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="6a6ec-126">Solo gli amministratori possono eliminare una chat room dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="6a6ec-127">È possibile configurare e gestire le chat room utilizzando i cmdlet di Windows PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="6a6ec-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6a6ec-128">**Cmdlet**</span></span>|<span data-ttu-id="6a6ec-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6a6ec-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a6ec-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6a6ec-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6a6ec-131">Creare una nuova chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="6a6ec-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6a6ec-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6a6ec-133">Configurare le impostazioni per una sala esistente. assegnare gli utenti e i gruppi di utenti alla sala</span><span class="sxs-lookup"><span data-stu-id="6a6ec-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="6a6ec-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6a6ec-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6a6ec-135">Recuperare informazioni sulle sale</span><span class="sxs-lookup"><span data-stu-id="6a6ec-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="6a6ec-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6a6ec-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6a6ec-137">Cancellare una chat room o i messaggi da una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="6a6ec-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6a6ec-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6a6ec-139">Rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="6a6ec-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="6a6ec-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="6a6ec-141">Rimuovere i messaggi da una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="6a6ec-142">È possibile utilizzare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat room esistente, inclusa l'aggiunta di utenti alla chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="6a6ec-143">È possibile configurare i seguenti parametri per le chat room:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="6a6ec-144">Disabili.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-144">Disabled.</span></span> <span data-ttu-id="6a6ec-145">Consente di disabilitare o abilitare una chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="6a6ec-146">Inviti.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-146">Invitations.</span></span> <span data-ttu-id="6a6ec-147">Consente di abilitare o disabilitare gli inviti delle chat room, che vengono utilizzati per informare gli utenti quando sono stati aggiunti come membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="6a6ec-148">L'impostazione predefinita per gli inviti in Inherit, che ha causato l'impostazione dell'invito configurata dalla chat room per la categoria a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="6a6ec-149">Configurando l'impostazione inviti su false a livello di chat room è possibile ignorare l'impostazione di categoria.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="6a6ec-150">Privacy.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-150">Privacy.</span></span> <span data-ttu-id="6a6ec-151">Consente di specificare se una chat room è aperta, chiusa o segreta.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="6a6ec-152">Le sale aperte possono essere cercate e accessibili da chiunque.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="6a6ec-153">Le sale chiuse possono essere cercate da chiunque, ma possono essere accessibili solo dai membri.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="6a6ec-154">Le sale segrete possono essere ricercate e accessibili solo dai membri della chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="6a6ec-155">Per impostazione predefinita, ogni nuova sala viene inizialmente configurata come chiusa.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="6a6ec-156">Tipo.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-156">Type.</span></span> <span data-ttu-id="6a6ec-157">Consente di specificare se una chat room è una sala normale, che accetta i messaggi inviati da qualsiasi membro o una sala auditorium, che accetta i messaggi inviati solo da un relatore.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="6a6ec-158">AddIn.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-158">Addin.</span></span> <span data-ttu-id="6a6ec-159">Consente di associare un componente aggiuntivo configurato in precedenza a una chat room, che consente ai membri di visualizzare il contenuto degli URL durante la partecipazione.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="6a6ec-160">Oltre ai parametri sopra riportati, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare gli utenti alla chat come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="6a6ec-161">Membri.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-161">Members.</span></span> <span data-ttu-id="6a6ec-162">Configura l'appartenenza per la chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-162">Configures membership for the chat room.</span></span> <span data-ttu-id="6a6ec-163">È possibile aggiungere o rimuovere singoli o più membri utilizzando un singolo cmdlet specificando l'indirizzo SIP degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="6a6ec-164">Per consentire l'aggiunta di utenti in blocco, è possibile specificare anche le unità organizzative o i gruppi di distribuzione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="6a6ec-165">Manager.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-165">Managers.</span></span> <span data-ttu-id="6a6ec-166">Consente di assegnare Manager alla chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="6a6ec-167">I Manager dispongono delle autorizzazioni per definire l'appartenenza di una chat room insieme ad altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="6a6ec-168">Relatori.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-168">Presenters.</span></span> <span data-ttu-id="6a6ec-169">Consente di assegnare i relatori a una chat room dell'Auditorium.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="6a6ec-170">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6a6ec-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="6a6ec-171">Creare una nuova sala</span><span class="sxs-lookup"><span data-stu-id="6a6ec-171">Create a new room</span></span>

<span data-ttu-id="6a6ec-172">È possibile creare una nuova sala utilizzando il cmdlet **New-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6a6ec-173">Ad esempio, il comando seguente crea una nuova chat room denominata room ITChatRoom nel pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="6a6ec-174">In questo esempio viene aggiunta la chat room alla categoria IT:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="6a6ec-175">**Nota:** PersistentChatPoolFqdn non è necessario se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="6a6ec-176">È presente un solo pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="6a6ec-177">Si specifica l'FQDN di un pool per la categoria.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="6a6ec-178">Si specifica l'FQDN di un pool per l'aggiunta della chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="6a6ec-179">Configurare una sala esistente</span><span class="sxs-lookup"><span data-stu-id="6a6ec-179">Configure an existing room</span></span>

<span data-ttu-id="6a6ec-180">È possibile configurare una sala esistente utilizzando il cmdlet **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6a6ec-181">Ad esempio, il comando seguente assegna User1 come membro e relatore e User2 come Manager della sala testCat Auditorium:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="6a6ec-182">Nell'esempio seguente vengono aggiunti tutti gli utenti dall'unità organizzativa NorthAmericaUsers in Active Directory alla chat room di NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="6a6ec-183">Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="6a6ec-184">Disabilitazione o abilitazione di una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-184">Disable or enable a room</span></span>

<span data-ttu-id="6a6ec-185">Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="6a6ec-186">Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="6a6ec-187">Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="6a6ec-188">Se la cronologia della chat persiste, il contenuto viene mantenuto quando la chat room è disattivata.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="6a6ec-189">Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo in cui la chat rimane in uno stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="6a6ec-190">Se in seguito si attiva la chat room, gli utenti possono cercare i messaggi che sono stati inviati prima che la chat room fosse disattivata.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="6a6ec-191">Per informazioni sulla configurazione della cronologia delle chat room, vedere [Manage Categories in Persistent Chat Server in Skype for Business server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="6a6ec-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="6a6ec-192">Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="6a6ec-193">Come amministratore, è possibile abilitare una sala disattivata e non è necessario ricreare le impostazioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="6a6ec-194">È possibile disabilitare una chat room utilizzando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro disabled su true:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="6a6ec-195">Per abilitare una chat room, impostare il parametro disabled su false:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="6a6ec-196">Ottenere informazioni sulle sale</span><span class="sxs-lookup"><span data-stu-id="6a6ec-196">Get information about rooms</span></span>

<span data-ttu-id="6a6ec-197">Per ottenere informazioni sulle sale configurate per l'utilizzo nell'organizzazione, è possibile utilizzare il cmdlet **Get-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6a6ec-198">Il comando seguente restituisce informazioni su tutte le chat room configurate per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="6a6ec-199">Rimuovere tutto il contenuto da una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-199">Remove all content from a room</span></span>

<span data-ttu-id="6a6ec-200">È possibile rimuovere il contenuto da una sala utilizzando il cmdlet **Clear-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6a6ec-201">Ad esempio, il comando seguente consente di rimuovere tutto il contenuto dalla chat room room ITChatRoom persistente che è stato aggiunto alla sala entro il 1 ° marzo 2015:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="6a6ec-202">Rimozione di un messaggio da una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-202">Remove a message from a room</span></span>

<span data-ttu-id="6a6ec-203">È possibile rimuovere uno o più messaggi nel database di Persistent Chat e, facoltativamente, sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore, utilizzando il cmdlet **Remove-CsPersistentChatMessage** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="6a6ec-204">Ad esempio, il comando seguente consente di rimuovere tutti i messaggi dalla chat room di room ITChatRoom che sono stati pubblicati dall'utente kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="6a6ec-205">Nell'esempio seguente vengono sostituiti tutti i messaggi rimossi con la nota che il messaggio non è più disponibile:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="6a6ec-206">Rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="6a6ec-206">Remove a room</span></span>

<span data-ttu-id="6a6ec-207">È possibile rimuovere una sala utilizzando il cmdlet **Remove-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6a6ec-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6a6ec-208">Ad esempio, il comando seguente consente di rimuovere la chat room RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="6a6ec-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="6a6ec-209">Spostare una chat room da una categoria all'altra</span><span class="sxs-lookup"><span data-stu-id="6a6ec-209">Move a room from one category to another</span></span>

<span data-ttu-id="6a6ec-210">Se un responsabile della chat room ha privilegi di **creatore** in un'altra categoria, può spostare la sala da una categoria all'altra.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="6a6ec-211">La sala non viene eliminata e ricreata.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="6a6ec-212">Si tratta di un cambiamento di associazione all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="6a6ec-213">La modifica di una categoria di chat room deve essere svolta raramente e con cautela.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="6a6ec-214">Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="6a6ec-215">Ad esempio, se un utente è membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.</span><span class="sxs-lookup"><span data-stu-id="6a6ec-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

