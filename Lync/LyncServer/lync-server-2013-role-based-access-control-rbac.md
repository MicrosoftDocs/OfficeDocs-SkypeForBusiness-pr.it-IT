---
title: 'Lync Server 2013: controllo di accesso basato sui ruoli (RBAC)'
description: 'Lync Server 2013: controllo di accesso basato sui ruoli (RBAC).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576582"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="e96a0-103">Controllo dell'accesso basato sui ruoli (RBAC) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e96a0-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e96a0-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e96a0-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e96a0-105">Microsoft Lync Server 2013 include i gruppi di controllo di accesso Role-Based (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e96a0-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="e96a0-106">Tali gruppi vengono creati durante la preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="e96a0-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="e96a0-107">Per informazioni dettagliate sulla preparazione della foresta, vedere [servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="e96a0-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="e96a0-108">Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere [changes made by Forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e96a0-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e96a0-109">Con RBAC, i privilegi amministrativi vengono concessi assegnando gli utenti ai ruoli amministrativi predefiniti, inclusi i 11 ruoli predefiniti che coprono molte attività amministrative comuni.</span><span class="sxs-lookup"><span data-stu-id="e96a0-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="e96a0-110">Ogni ruolo è associato a un elenco specifico di cmdlet di Lync Server Management Shell che gli utenti di quel ruolo sono autorizzati a eseguire.</span><span class="sxs-lookup"><span data-stu-id="e96a0-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="e96a0-111">È possibile utilizzare RBAC per seguire il principio "privilegio minimo", in cui agli utenti vengono fornite solo le abilità amministrative richieste dai loro processi.</span><span class="sxs-lookup"><span data-stu-id="e96a0-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="e96a0-112">Per informazioni dettagliate, vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e96a0-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

