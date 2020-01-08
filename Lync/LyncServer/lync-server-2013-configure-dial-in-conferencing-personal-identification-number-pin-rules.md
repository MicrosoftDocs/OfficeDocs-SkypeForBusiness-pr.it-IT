---
title: Configurare le regole del PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9269bb53a463bf439aef8fda87cbae5bdf17b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="92f09-102">Configurare le regole PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f09-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f09-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="92f09-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="92f09-104">Lync Server 2013 gli utenti che hanno credenziali Active Directory Domain Services (AD DS) nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati usando un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="92f09-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="92f09-105">I criteri PIN definiscono le regole per il funzionamento dei pin di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="92f09-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="92f09-106">Se si vuole applicare un criterio specifico a un sito o a un determinato gruppo di utenti, è possibile creare un nuovo criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="92f09-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="92f09-107">Se si vogliono usare gli stessi criteri PIN per l'intera organizzazione, è possibile usare il criterio PIN globale e modificarlo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="92f09-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="92f09-108">I criteri PIN si applicano agli utenti dall'ambito più limitato all'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="92f09-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="92f09-109">Se si assegna un criterio PIN a livello di utente a un utente, queste impostazioni hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="92f09-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="92f09-110">Se non si assegna un criterio utente, il criterio PIN a livello di sito si applica, se esistente.</span><span class="sxs-lookup"><span data-stu-id="92f09-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="92f09-111">Se non si applicano criteri per l'utente o il sito, il criterio PIN globale fornisce le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="92f09-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92f09-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="92f09-112">In This Section</span></span>

  - [<span data-ttu-id="92f09-113">Modifica delle impostazioni predefinite dei PIN per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f09-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="92f09-114">Creare o modificare le impostazioni del PIN di conferenza telefonica con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="92f09-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="92f09-115">Eliminare le impostazioni dei PIN per i servizi di conferenza telefonica con accesso esterno per un sito o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f09-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

