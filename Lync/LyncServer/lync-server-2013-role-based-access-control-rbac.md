---
title: 'Lync Server 2013: controllo di accesso basato sui ruoli (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75287cd418d22418f8de2c1a1b018eab8cca4e49
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="d6034-102">Controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6034-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6034-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d6034-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d6034-104">Microsoft Lync Server 2013 include i gruppi di controllo di accesso basati sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d6034-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="d6034-105">Questi gruppi vengono creati durante la preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="d6034-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="d6034-106">Per informazioni dettagliate sulla preparazione della foresta, vedere [servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="d6034-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="d6034-107">Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d6034-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d6034-108">Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti i ruoli amministrativi predefiniti, inclusi i 11 ruoli predefiniti che coprono molte attività amministrative comuni.</span><span class="sxs-lookup"><span data-stu-id="d6034-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="d6034-109">Ogni ruolo è associato a un elenco specifico dei cmdlet di Lync Server Management Shell che gli utenti possono eseguire in tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="d6034-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="d6034-110">Puoi usare RBAC per seguire il principio "privilegio minimo", in cui gli utenti ricevono solo le abilità amministrative necessarie per i loro processi.</span><span class="sxs-lookup"><span data-stu-id="d6034-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="d6034-111">Per informazioni dettagliate, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d6034-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

