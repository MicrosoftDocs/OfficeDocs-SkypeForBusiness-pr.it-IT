---
title: "Lync Server 2013: configurazione dell'ambiente per il portale Web amministrativo di Lync room System"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5198416e3c06dfd83cf7d1cf5bf3c6002ebe72ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="dada1-102">Configurazione dell'ambiente Lync Server 2013 per il portale Web amministrativo di Lync room System</span><span class="sxs-lookup"><span data-stu-id="dada1-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dada1-103">_**Ultimo argomento modificato:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="dada1-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="dada1-104">Per utilizzare il portale Web amministrativo di Lync room System (LRS), sarà necessario installare o configurare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="dada1-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dada1-105">Se il server è configurato con l'autenticazione Kerberos e NTLM e LRS è in esecuzione in un computer che non è stato aggiunto al dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non visualizzerà lo stato di LRS nel portale amministrativo.</span><span class="sxs-lookup"><span data-stu-id="dada1-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="dada1-106">Per risolvere il problema, configurare il server con l'autenticazione NTLM o sia l'autenticazione NTLM che TLS-DSK (senza Kerberos) oppure aggiungere il computer LRS al dominio.</span><span class="sxs-lookup"><span data-stu-id="dada1-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="dada1-107">Installare gli aggiornamenti cumulativi di Lync Server 2013: luglio 2013 nella topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dada1-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="dada1-108">Per ottenere l'aggiornamento o vedere cosa è incluso in esso, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="dada1-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="dada1-109">Creare un utente di Active Directory abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="dada1-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="dada1-110">Il portale Web amministrativo di LRS utilizza queste credenziali per eseguire query sulle informazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dada1-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="dada1-111">Il nome utente consigliato è LRSApp.</span><span class="sxs-lookup"><span data-stu-id="dada1-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="dada1-112">Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="dada1-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="dada1-113">Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione.</span><span class="sxs-lookup"><span data-stu-id="dada1-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="dada1-114">Gli utenti abilitati per SIP che sono stati aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire alcuni comandi, ad esempio la raccolta di registri.</span><span class="sxs-lookup"><span data-stu-id="dada1-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="dada1-115">Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="dada1-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="dada1-116">Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="dada1-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="dada1-117">![Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza")</span><span class="sxs-lookup"><span data-stu-id="dada1-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="dada1-118">Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="dada1-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="dada1-119">![Pagina membri proprietà LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Pagina membri proprietà LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="dada1-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="dada1-120">Creare un utente di Active Directory SIP abilitato con nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="dada1-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="dada1-121">Aggiungere l'utente a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="dada1-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="dada1-122">![Pagina membri proprietà LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Pagina membri proprietà LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="dada1-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="dada1-123">Installare ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1, disponibile nell'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span><span class="sxs-lookup"><span data-stu-id="dada1-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

