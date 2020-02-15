---
title: 'Lync Server 2013: account utente abilitati per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d51f72f586ab6d5b5094c61ae09d8ac316350b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="9dcbe-102">Account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dcbe-103">_**Ultimo argomento modificato:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="9dcbe-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="9dcbe-104">Negli argomenti di questa sezione vengono fornite procedure dettagliate per la configurazione delle impostazioni utente che è possibile eseguire utilizzando il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9dcbe-105">Non è possibile utilizzare il pannello di controllo di Lync Server per gestire gli utenti membri del gruppo Domain Admins di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="9dcbe-106">Per gli utenti di Domain Admins, è possibile utilizzare solo il pannello di controllo di Lync Server per eseguire le operazioni di ricerca di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="9dcbe-107">Per eseguire operazioni di scrittura sugli utenti degli amministratori di dominio (ad esempio, abilitare o disabilitare il pannello di controllo di Lync Server, modificare le assegnazioni del pool o dei criteri, le impostazioni di telefonia, l'indirizzo SIP), è necessario utilizzare i cmdlet di Windows PowerShell durante l'accesso come utente Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="9dcbe-108">Per informazioni dettagliate sull'utilizzo dei cmdlet di Windows PowerShell per la gestione degli utenti, vedere <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="9dcbe-109">Quando si esegue qualsiasi attività amministrativa di Lync Server 2013 che implica la ricerca di un utente o il filtro dei risultati di ricerca degli utenti, esistono proprietà utente che esistono come attributi in servizi di dominio Active Directory, ma non vengono replicate nel catalogo globale. fino alla distribuzione di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9dcbe-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="9dcbe-110">Microsoft Exchange, non Lync Server, contrassegna gli attributi seguenti per la replica nel catalogo globale al momento dell'installazione:</span><span class="sxs-lookup"><span data-stu-id="9dcbe-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dcbe-111">Informazioni utente</span><span class="sxs-lookup"><span data-stu-id="9dcbe-111">User Information</span></span></th>
<th><span data-ttu-id="9dcbe-112">Indirizzo e telefono</span><span class="sxs-lookup"><span data-stu-id="9dcbe-112">Address and Phone</span></span></th>
<th><span data-ttu-id="9dcbe-113">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="9dcbe-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dcbe-114">Iniziali</span><span class="sxs-lookup"><span data-stu-id="9dcbe-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="9dcbe-115">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="9dcbe-115">Street address</span></span></p>
<p><span data-ttu-id="9dcbe-116">Paese</span><span class="sxs-lookup"><span data-stu-id="9dcbe-116">Country/region</span></span></p>
<p><span data-ttu-id="9dcbe-117">Del cercapersone</span><span class="sxs-lookup"><span data-stu-id="9dcbe-117">Pager</span></span></p>
<p><span data-ttu-id="9dcbe-118">Fax</span><span class="sxs-lookup"><span data-stu-id="9dcbe-118">Fax</span></span></p>
<p><span data-ttu-id="9dcbe-119">Cellulare</span><span class="sxs-lookup"><span data-stu-id="9dcbe-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="9dcbe-120">Titolo</span><span class="sxs-lookup"><span data-stu-id="9dcbe-120">Title</span></span></p>
<p><span data-ttu-id="9dcbe-121">Company</span><span class="sxs-lookup"><span data-stu-id="9dcbe-121">Company</span></span></p>
<p><span data-ttu-id="9dcbe-122">Reparto</span><span class="sxs-lookup"><span data-stu-id="9dcbe-122">Department</span></span></p>
<p><span data-ttu-id="9dcbe-123">Ufficio</span><span class="sxs-lookup"><span data-stu-id="9dcbe-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="9dcbe-124">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="9dcbe-124">In This Section</span></span>

  - [<span data-ttu-id="9dcbe-125">Visualizzazione delle informazioni sugli account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="9dcbe-126">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="9dcbe-127">Gestione di VoIP aziendale per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="9dcbe-128">Modifica delle proprietà degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="9dcbe-129">Gestire i criteri di accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="9dcbe-130">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9dcbe-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dcbe-131">See Also</span></span>


[<span data-ttu-id="9dcbe-132">Cmdlet per la gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="9dcbe-133">Gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcbe-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

