---
title: Eseguire la compatibilità con le versioni precedenti del server Chat persistente
description: Eseguire la compatibilità con le versioni precedenti per il server Chat persistente.
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
ms.openlocfilehash: b0486992d44e6385559d3e9df9f9ffc2125120da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570152"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="9a272-103">Eseguire la compatibilità con le versioni precedenti del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9a272-103">Run backward compatibility for Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a272-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9a272-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9a272-105">Lync Server 2013, endpoint del server Chat persistente, consente di creare un URL semplice che punta a un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a272-105">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="9a272-106">Questa operazione è utile per i client legacy (Microsoft Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat) perché gli utenti possono immettere un URL semplice nella configurazione manuale quando si tenta di puntare il client legacy a un computer che esegue Lync 2013, Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="9a272-106">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="9a272-107">Questo endpoint non viene utilizzato da Chat persistente ed è necessario solo per i client legacy.</span><span class="sxs-lookup"><span data-stu-id="9a272-107">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="9a272-108">Questa operazione è utile per il periodo interinale in cui è possibile eseguire la migrazione delle sale, ma i client di Lync 2013 non sono stati distribuiti nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a272-108">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="9a272-109">Gli utenti che eseguono Lync 2010 Group Chat (client) possono comunque connettersi al server back-end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a272-109">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="9a272-110">Non è necessario creare più endpoint del server Chat persistente. serve solo una per ogni pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a272-110">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="9a272-111">Gli amministratori possono creare più endpoint (uno per pool), ma i client legacy possono essere configurati per la connessione a un solo pool alla volta.</span><span class="sxs-lookup"><span data-stu-id="9a272-111">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="9a272-112">Nello scenario usuale o mainstream, la distribuzione legacy è solo un pool.</span><span class="sxs-lookup"><span data-stu-id="9a272-112">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="9a272-113">Una nuova distribuzione generalmente esegue la migrazione del pool a un nuovo Lync Server 2013 e potrebbe aggiungere alcuni nuovi pool di server Chat persistente aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9a272-113">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="9a272-114">Uno scenario di questo tipo in genere segue questo schema:</span><span class="sxs-lookup"><span data-stu-id="9a272-114">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="9a272-115">È possibile amministrare gli utenti con un solo Lync Server 2010, un pool di chat di gruppo e i client di chat di gruppo di Lync 2010 che si connettono al pool utilizzando un utente noto (SIP predefinito: ocschat@ \<domainName\> . com o uno simile).</span><span class="sxs-lookup"><span data-stu-id="9a272-115">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="9a272-116">Gli utenti sono servizi di dominio Active Directory abilitati per SIP e il servizio di ricerca esegue la registrazione per ricevere le richieste in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9a272-116">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="9a272-117">Successivamente, si installa un server di chat persistente di Lync Server 2013 e un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a272-117">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="9a272-118">In un momento in cui gli utenti sono in genere offline, ad esempio durante il weekend:</span><span class="sxs-lookup"><span data-stu-id="9a272-118">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="9a272-119">Disattivare Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="9a272-119">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="9a272-120">Eseguire la migrazione dei dati dal pool di chat di gruppo di Lync Server 2010 al pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a272-120">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="9a272-121">Eliminare l'utente noto da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a272-121">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="9a272-122">Creare un nuovo *endpoint legacy* con lo stesso URI SIP dell'utente noto eliminato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9a272-122">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="9a272-123">Avviare Lync Server 2013, server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a272-123">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="9a272-124">Gli utenti eseguono l'accesso utilizzando la propria chat di gruppo di Lync 2010 (client) e si connettono ai dati senza dover modificare alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a272-124">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="9a272-125">In un secondo momento, è possibile rimuovere le autorizzazioni di Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="9a272-125">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="9a272-126">Successivamente, è possibile distribuire Lync Server 2013, il server Chat persistente e installare nuovi pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a272-126">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="9a272-127">Per informazioni dettagliate sulla migrazione da Lync Server 2010, Group Chat a Lync Server 2013, server Chat persistente, vedere [migrazione da Lync server 2010, Group Chat o Office Communications server 2007 R2 Group Chat a Lync server 2013, server Chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a272-127">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="9a272-128">Per eseguire la compatibilità con le versioni precedenti (per creare un endpoint del server Chat persistente che punta a un pool di server Chat persistente, che può essere utilizzato dai client del pool di chat di gruppo legacy):</span><span class="sxs-lookup"><span data-stu-id="9a272-128">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="9a272-129">Successivamente, configurare i client di chat persistente per utilizzare quell'indirizzo SIP come loro oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="9a272-129">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="9a272-130">L'indirizzo SIP viene creato con il cmdlet **New-CsPersistentChatEndpoint** per un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="9a272-130">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="9a272-131">Per aggiungere l'endpoint del server Chat persistente utilizzando l'interfaccia della riga di comando di Windows PowerShell, prendere in considerazione l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9a272-131">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="9a272-132">In questo caso si configura l'oggetto contatto con il nome "persistentchat" nella topologia "contoso.com", dove il nome di dominio completo (FQDN) del pool è "pcpool.contoso.com":</span><span class="sxs-lookup"><span data-stu-id="9a272-132">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="9a272-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a272-133">See Also</span></span>


[<span data-ttu-id="9a272-134">Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a272-134">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

