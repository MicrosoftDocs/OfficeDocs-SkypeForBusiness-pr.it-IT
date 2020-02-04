---
title: 'Lync Server 2013: Preparazione di un ambiente Servizi di dominio Active Directory bloccato'
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
ms.openlocfilehash: 5d589fbc6b7d31b38bc788ba9851edf4386294ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="c801d-102">Preparazione di un ambiente Servizi di dominio Active Directory bloccato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c801d-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c801d-103">_**Argomento Ultima modifica:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="c801d-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="c801d-104">Le organizzazioni spesso bloccano i servizi di dominio Active Directory per alleviare i rischi per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c801d-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="c801d-105">Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni necessarie per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c801d-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="c801d-106">La preparazione corretta di un ambiente Active Directory bloccato per Lync Server 2013 include alcune considerazioni e passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c801d-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="c801d-107">Di seguito sono riportati due modi comuni in cui le autorizzazioni sono limitate in un ambiente Active Directory bloccato:</span><span class="sxs-lookup"><span data-stu-id="c801d-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="c801d-108">Le voci di controllo di accesso utente autenticate vengono rimosse dai contenitori.</span><span class="sxs-lookup"><span data-stu-id="c801d-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="c801d-109">L'ereditarietà delle autorizzazioni è disabilitata nei contenitori di oggetti utente, contatto, InetOrgPerson o computer.</span><span class="sxs-lookup"><span data-stu-id="c801d-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c801d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c801d-110">In This Section</span></span>

  - [<span data-ttu-id="c801d-111">Rimozione delle autorizzazioni degli utenti autenticati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c801d-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="c801d-112">Ereditarietà delle autorizzazioni disabilitata nei contenitori di oggetti Computer, User o InetOrgPerson in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c801d-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

