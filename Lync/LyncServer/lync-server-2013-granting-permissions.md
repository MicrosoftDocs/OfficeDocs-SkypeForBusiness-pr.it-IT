---
title: 'Lync Server 2013: concessione di autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="c0578-102">Concessione di autorizzazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0578-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0578-103">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="c0578-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="c0578-104">Per il programma di installazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specifica, consentendo ai membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa di installare Lync Server 2013 nel dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="c0578-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="c0578-105">Quando si assegnano le autorizzazioni per un'unità organizzativa, vengono concesse le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0578-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="c0578-106">Lettura</span><span class="sxs-lookup"><span data-stu-id="c0578-106">Read</span></span>

  - <span data-ttu-id="c0578-107">Scrittura</span><span class="sxs-lookup"><span data-stu-id="c0578-107">Write</span></span>

  - <span data-ttu-id="c0578-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="c0578-108">ReadSPN</span></span>

  - <span data-ttu-id="c0578-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="c0578-109">WriteSPN</span></span>

<span data-ttu-id="c0578-110">Per l'amministrazione, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza dover essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="c0578-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="c0578-111">Le autorizzazioni aggiunte all'unità organizzativa specificata sono le stesse autorizzazioni che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori dell'unità organizzativa computer e utenti.</span><span class="sxs-lookup"><span data-stu-id="c0578-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0578-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c0578-112">In This Section</span></span>

  - [<span data-ttu-id="c0578-113">Concessione di autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0578-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="c0578-114">Concessione di autorizzazioni per le unità organizzative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0578-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

