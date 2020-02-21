---
title: Configurare le regole del PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16b56e1809f9ffefa37065a208340e1143e38487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="fb5fc-102">Configurare le regole del PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5fc-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5fc-103">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="fb5fc-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="fb5fc-104">Gli utenti di Lync Server 2013 che dispongono di credenziali di servizi di dominio Active Directory nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati tramite un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="fb5fc-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="fb5fc-105">Il criterio PIN definisce le regole per il funzionamento dei PIN per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="fb5fc-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="fb5fc-p102">È possibile creare un nuovo criterio PIN se si desidera un criterio specifico da applicare a un sito o a un determinato gruppo di utenti. Se si desidera utilizzare lo stesso criterio PIN per l'intera organizzazione, è possibile utilizzare il criterio PIN globale e modificarlo in base alle esigenze. I criteri PIN si applicano agli utenti partendo dall'ambito più limitato fino all'ambito più esteso. Se si assegna a un utente un criterio PIN a livello utente, tali impostazioni avranno la priorità. Se invece non si assegna un criterio utente, si applicherà il criterio PIN a livello di sito, se esistente. Se non si applica alcun criterio utente o sito, le impostazioni predefinite verranno fornite dal criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="fb5fc-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb5fc-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fb5fc-112">In This Section</span></span>

  - [<span data-ttu-id="fb5fc-113">Modificare le impostazioni predefinite dei PIN per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5fc-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="fb5fc-114">Creare o modificare le impostazioni del PIN per le conferenze telefoniche con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="fb5fc-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="fb5fc-115">Eliminare le impostazioni del PIN per le conferenze telefoniche con accesso esterno per un sito o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5fc-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

