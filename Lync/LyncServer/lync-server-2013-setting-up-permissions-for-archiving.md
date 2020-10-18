---
title: "Lync Server 2013: configurazione delle autorizzazioni per l'archiviazione"
description: "Lync Server 2013: configurazione delle autorizzazioni per l'archiviazione."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up permissions for Archiving
ms:assetid: 67f97c94-52f5-4a83-a35c-8c307d5de9a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204961(v=OCS.15)
ms:contentKeyID: 48184364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f06c4fb48772a41621ece765dcc90555f0cd2d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574832"
---
# <a name="setting-up-permissions-for-archiving-in-lync-server-2013"></a><span data-ttu-id="f93f3-103">Configurazione delle autorizzazioni per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f93f3-103">Setting up permissions for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f93f3-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f93f3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f93f3-105">In Lync Server 2013, le attività specifiche richiedono ancora che gli utenti che eseguono tali attività siano membri di uno o più gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="f93f3-105">In Lync Server 2013, specific tasks still require that users who perform those tasks be members of one or more specific groups.</span></span> <span data-ttu-id="f93f3-106">Tuttavia, è anche possibile utilizzare il controllo di accesso basato sui ruoli (RBAC) per concedere privilegi assegnando gli utenti ai ruoli amministrativi predefiniti di Lync Server. Prima di distribuire l'archiviazione, verificare che siano disponibili i diritti utente e le autorizzazioni appropriate e che tutti gli utenti a cui si desidera assegnare uno specifico ruolo RBAC siano stati assegnati a tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="f93f3-106">However, you can also use role-based access control (RBAC) to grant privileges by assigning users to predefined Lync Server administrative roles.Before you deploy Archiving, be sure that the appropriate user rights and permissions are in place, and that any users who you want to assign to a specific RBAC role have been assigned to that role.</span></span> <span data-ttu-id="f93f3-107">Per informazioni dettagliate sui diritti utente, le autorizzazioni e i ruoli per la distribuzione del supporto per l'archiviazione, vedere [Deployment Checklist for archiving in Lync Server 2013](lync-server-2013-deployment-checklist-for-archiving.md), disponibile nella documentazione relativa alla pianificazione e nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f93f3-107">For details about the user rights, permissions, and roles for deploying support for Archiving, see [Deployment checklist for Archiving in Lync Server 2013](lync-server-2013-deployment-checklist-for-archiving.md), which is available in the Planning documentation and the Deployment documentation.</span></span> <span data-ttu-id="f93f3-108">Per informazioni dettagliate su RBAC, vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f93f3-108">For details about RBAC, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

