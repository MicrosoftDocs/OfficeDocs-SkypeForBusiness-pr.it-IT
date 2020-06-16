---
title: Eseguire la compatibilità con le versioni precedenti del server Chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5308d39e4edcfeddf494aa364f6b7ed43b9822dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="e1498-102">Eseguire la compatibilità con le versioni precedenti del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="e1498-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1498-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e1498-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e1498-104">Lync Server 2013, endpoint del server Chat persistente, consente di creare un URL semplice che punta a un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1498-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="e1498-105">Questa operazione è utile per i client legacy (Microsoft Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat) perché gli utenti possono immettere un URL semplice nella configurazione manuale quando si tenta di puntare il client legacy a un computer che esegue Lync 2013, Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="e1498-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="e1498-106">Questo endpoint non viene utilizzato da Chat persistente ed è necessario solo per i client legacy.</span><span class="sxs-lookup"><span data-stu-id="e1498-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="e1498-107">Questa operazione è utile per il periodo interinale in cui è possibile eseguire la migrazione delle sale, ma i client di Lync 2013 non sono stati distribuiti nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1498-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="e1498-108">Gli utenti che eseguono Lync 2010 Group Chat (client) possono comunque connettersi al server back-end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1498-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="e1498-109">Non è necessario creare più endpoint del server Chat persistente. serve solo una per ogni pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1498-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="e1498-110">Gli amministratori possono creare più endpoint (uno per pool), ma i client legacy possono essere configurati per la connessione a un solo pool alla volta.</span><span class="sxs-lookup"><span data-stu-id="e1498-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="e1498-111">Nello scenario usuale o mainstream, la distribuzione legacy è solo un pool.</span><span class="sxs-lookup"><span data-stu-id="e1498-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="e1498-112">Una nuova distribuzione generalmente esegue la migrazione del pool a un nuovo Lync Server 2013 e potrebbe aggiungere alcuni nuovi pool di server Chat persistente aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e1498-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="e1498-113">Uno scenario di questo tipo in genere segue questo schema:</span><span class="sxs-lookup"><span data-stu-id="e1498-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="e1498-114">È possibile amministrare gli utenti con un solo Lync Server 2010, un pool di chat di gruppo e i client di chat di gruppo di Lync 2010 che si connettono al pool utilizzando un utente noto (SIP predefinito: ocschat@ \<domainName\> . com o uno simile).</span><span class="sxs-lookup"><span data-stu-id="e1498-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="e1498-115">Gli utenti sono servizi di dominio Active Directory abilitati per SIP e il servizio di ricerca esegue la registrazione per ricevere le richieste in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e1498-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="e1498-116">Successivamente, si installa un server di chat persistente di Lync Server 2013 e un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1498-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="e1498-117">In un momento in cui gli utenti sono in genere offline, ad esempio durante il weekend:</span><span class="sxs-lookup"><span data-stu-id="e1498-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="e1498-118">Disattivare Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="e1498-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="e1498-119">Eseguire la migrazione dei dati dal pool di chat di gruppo di Lync Server 2010 al pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1498-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="e1498-120">Eliminare l'utente noto da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1498-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="e1498-121">Creare un nuovo *endpoint legacy* con lo stesso URI SIP dell'utente noto eliminato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e1498-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="e1498-122">Avviare Lync Server 2013, server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1498-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="e1498-123">Gli utenti eseguono l'accesso utilizzando la propria chat di gruppo di Lync 2010 (client) e si connettono ai dati senza dover modificare alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="e1498-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="e1498-124">In un secondo momento, è possibile rimuovere le autorizzazioni di Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="e1498-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="e1498-125">Successivamente, è possibile distribuire Lync Server 2013, il server Chat persistente e installare nuovi pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1498-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="e1498-126">Per informazioni dettagliate sulla migrazione da Lync Server 2010, Group Chat a Lync Server 2013, server Chat persistente, vedere [migrazione da Lync server 2010, Group Chat o Office Communications server 2007 R2 Group Chat a Lync server 2013, server Chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1498-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="e1498-127">Per eseguire la compatibilità con le versioni precedenti (per creare un endpoint del server Chat persistente che punta a un pool di server Chat persistente, che può essere utilizzato dai client del pool di chat di gruppo legacy):</span><span class="sxs-lookup"><span data-stu-id="e1498-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="e1498-128">Successivamente, configurare i client di chat persistente per utilizzare quell'indirizzo SIP come loro oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="e1498-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="e1498-129">L'indirizzo SIP viene creato con il cmdlet **New-CsPersistentChatEndpoint** per un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="e1498-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="e1498-130">Per aggiungere l'endpoint del server Chat persistente utilizzando l'interfaccia della riga di comando di Windows PowerShell, prendere in considerazione l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e1498-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="e1498-131">In questo caso si configura l'oggetto contatto con il nome "persistentchat" nella topologia "contoso.com", dove il nome di dominio completo (FQDN) del pool è "pcpool.contoso.com":</span><span class="sxs-lookup"><span data-stu-id="e1498-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="e1498-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1498-132">See Also</span></span>


[<span data-ttu-id="e1498-133">Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1498-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

