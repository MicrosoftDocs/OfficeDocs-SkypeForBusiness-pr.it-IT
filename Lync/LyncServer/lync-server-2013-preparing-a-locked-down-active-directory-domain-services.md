---
title: 'Lync Server 2013: preparazione di servizi di dominio Active Directory bloccati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8ea746ba8ea2ddea8d696d42865324da60ecbc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="5b098-102">Preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b098-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b098-103">_**Ultimo argomento modificato:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="5b098-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="5b098-104">Le organizzazioni spesso bloccano i servizi di dominio Active Directory per attenuare i rischi per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5b098-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="5b098-105">Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b098-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="5b098-106">La preparazione corretta di un ambiente Active Directory bloccato per Lync Server 2013 prevede alcune considerazioni e passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5b098-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="5b098-107">Due metodi frequenti utilizzati per limitare le autorizzazioni in un ambiente Active Directory bloccato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b098-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="5b098-108">Rimozione delle voci di controllo di accesso degli utenti autenticati dai contenitori.</span><span class="sxs-lookup"><span data-stu-id="5b098-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="5b098-109">Disabilitazione dell'ereditarietà delle autorizzazioni nei contenitori di oggetti User, Contact, InetOrgPerson o Computer.</span><span class="sxs-lookup"><span data-stu-id="5b098-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b098-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5b098-110">In This Section</span></span>

  - [<span data-ttu-id="5b098-111">Le autorizzazioni degli utenti autenticati sono state rimosse in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b098-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="5b098-112">L'ereditarietà delle autorizzazioni è disabilitata su computer, utenti o contenitori InetOrgPerson in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b098-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

