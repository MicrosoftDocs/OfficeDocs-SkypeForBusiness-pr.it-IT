---
title: 'Lync Server 2013: Gestire i criteri di segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="0c40b-102">Gestire i criteri di segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c40b-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c40b-103">_**Argomento Ultima modifica:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="0c40b-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="0c40b-104">Un criterio di segreteria *telefonica ospitata* fornisce informazioni all'applicazione di routing di Lync Server 2013 ExUM su dove instradare le chiamate per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="0c40b-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c40b-105">In genere è necessario un solo criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="0c40b-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="0c40b-106">In molti casi è possibile modificare il criterio globale per soddisfare tutte le esigenze.</span><span class="sxs-lookup"><span data-stu-id="0c40b-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="0c40b-107">Se si crea un criterio con l'ambito del sito, viene assegnato automaticamente a tutti gli utenti ospitati nel sito specificato.</span><span class="sxs-lookup"><span data-stu-id="0c40b-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="0c40b-108">Se crei un criterio con ambito per utente, devi assegnarlo esplicitamente a utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="0c40b-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="0c40b-109">È possibile distribuire più criteri per la segreteria telefonica ospitata, ma in questo caso i criteri devono essere assegnati per singolo utente.</span><span class="sxs-lookup"><span data-stu-id="0c40b-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="0c40b-110">Per informazioni dettagliate sulla pianificazione dei criteri per la segreteria telefonica ospitata, vedere Criteri di segreteria [telefonica ospitati in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0c40b-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c40b-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0c40b-111">In This Section</span></span>

  - [<span data-ttu-id="0c40b-112">Modificare i criteri di segreteria telefonica ospitata globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c40b-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="0c40b-113">Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c40b-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="0c40b-114">Creare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c40b-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="0c40b-115">Assegnare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c40b-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

