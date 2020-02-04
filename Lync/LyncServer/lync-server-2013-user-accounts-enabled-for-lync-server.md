---
title: 'Lync Server 2013: account utente abilitato per Lync Server'
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
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="5f76b-102">Account utente abilitato per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f76b-103">_**Argomento Ultima modifica:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="5f76b-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="5f76b-104">Gli argomenti di questa sezione includono procedure dettagliate per la configurazione delle impostazioni utente che è possibile eseguire tramite il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f76b-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f76b-105">Non è possibile usare il pannello di controllo di Lync Server per gestire gli utenti membri del gruppo Domain Admins di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f76b-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="5f76b-106">Per gli utenti di Domain Admins, puoi usare solo il pannello di controllo di Lync Server per eseguire operazioni di ricerca di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5f76b-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="5f76b-107">Per eseguire operazioni di scrittura sugli utenti di Domain Admins, ad esempio abilitare o disabilitare il pannello di controllo di Lync Server, modificare le assegnazioni di pool o criteri, le impostazioni di telefonia, l'indirizzo SIP, è necessario usare i cmdlet di Windows PowerShell durante l'accesso come utente di Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="5f76b-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="5f76b-108">Per informazioni dettagliate sull'uso dei cmdlet di Windows PowerShell per gestire gli utenti, vedere <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="5f76b-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="5f76b-109">Quando si esegue un'attività amministrativa di Lync Server 2013 che include la ricerca di un utente o il filtro dei risultati della ricerca degli utenti, esistono alcune proprietà utente che esistono come attributi in servizi di dominio Active Directory, ma non vengono replicate nel catalogo globale fino alla distribuzione di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5f76b-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="5f76b-110">Microsoft Exchange, non Lync Server, contrassegna gli attributi seguenti per la replica nel catalogo globale al momento dell'installazione:</span><span class="sxs-lookup"><span data-stu-id="5f76b-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f76b-111">Informazioni utente</span><span class="sxs-lookup"><span data-stu-id="5f76b-111">User Information</span></span></th>
<th><span data-ttu-id="5f76b-112">Indirizzo e telefono</span><span class="sxs-lookup"><span data-stu-id="5f76b-112">Address and Phone</span></span></th>
<th><span data-ttu-id="5f76b-113">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="5f76b-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f76b-114">Iniziali</span><span class="sxs-lookup"><span data-stu-id="5f76b-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="5f76b-115">Indirizzo di strada</span><span class="sxs-lookup"><span data-stu-id="5f76b-115">Street address</span></span></p>
<p><span data-ttu-id="5f76b-116">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="5f76b-116">Country/region</span></span></p>
<p><span data-ttu-id="5f76b-117">Cercapersone</span><span class="sxs-lookup"><span data-stu-id="5f76b-117">Pager</span></span></p>
<p><span data-ttu-id="5f76b-118">Fax</span><span class="sxs-lookup"><span data-stu-id="5f76b-118">Fax</span></span></p>
<p><span data-ttu-id="5f76b-119">Dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5f76b-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="5f76b-120">Titolo</span><span class="sxs-lookup"><span data-stu-id="5f76b-120">Title</span></span></p>
<p><span data-ttu-id="5f76b-121">Società</span><span class="sxs-lookup"><span data-stu-id="5f76b-121">Company</span></span></p>
<p><span data-ttu-id="5f76b-122">Dipartimento</span><span class="sxs-lookup"><span data-stu-id="5f76b-122">Department</span></span></p>
<p><span data-ttu-id="5f76b-123">Office</span><span class="sxs-lookup"><span data-stu-id="5f76b-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="5f76b-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5f76b-124">In This Section</span></span>

  - [<span data-ttu-id="5f76b-125">Visualizzazione di informazioni sugli account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="5f76b-126">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="5f76b-127">Gestione di VoIP aziendale per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="5f76b-128">Modifica delle proprietà dell'account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="5f76b-129">Gestire i criteri di accesso esterno per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="5f76b-130">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f76b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f76b-131">See Also</span></span>


[<span data-ttu-id="5f76b-132">Cmdlet per la gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="5f76b-133">Gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f76b-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

