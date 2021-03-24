---
title: Controllo degli accessi in base al ruolo (RBAC) per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server include Role-Based Access Control (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere Servizi di dominio Active Directory per Skype for Business Server. Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere Changes made by forest preparation in Skype for Business Server nella documentazione relativa alla distribuzione.
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104212"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="ad841-106">Controllo degli accessi in base al ruolo (RBAC) per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad841-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="ad841-107">Skype for Business Server include Role-Based Access Control (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ad841-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="ad841-108">Questi gruppi vengono creati durante la preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="ad841-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="ad841-109">Per informazioni dettagliate sulla preparazione della foresta, vedere [Servizi di dominio Active Directory per Skype for Business Server.](active-directory-domain-services.md)</span><span class="sxs-lookup"><span data-stu-id="ad841-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="ad841-110">Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad841-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="ad841-111">Con RBAC, il privilegio amministrativo viene concesso assegnando gli utenti a ruoli amministrativi predefiniti, inclusi gli 11 ruoli predefiniti che coprono molte attività amministrative comuni.</span><span class="sxs-lookup"><span data-stu-id="ad841-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="ad841-112">Ogni ruolo è associato a un elenco specifico di cmdlet di Skype for Business Server Management Shell che gli utenti in tale ruolo possono eseguire.</span><span class="sxs-lookup"><span data-stu-id="ad841-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="ad841-113">È possibile utilizzare RBAC per seguire il principio del "privilegio minimo", in cui agli utenti vengono fornite solo le capacità amministrative richieste dai loro processi.</span><span class="sxs-lookup"><span data-stu-id="ad841-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="ad841-114">Per ulteriori informazioni sui ruoli RBAC, vedere [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="ad841-114">More details on RBAC roles can be found at [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>