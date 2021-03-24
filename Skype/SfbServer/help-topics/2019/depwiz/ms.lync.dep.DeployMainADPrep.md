---
title: Preparazione di Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di Skype for Business Server, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti. La Distribuzione guidata di Skype for Business Server guiderà l'utente attraverso i passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory è riuscita, preparare ogni dominio che ospiterà utenti o server.
ms.openlocfilehash: fcc77ed8dab3a6e3e643c2022dc45623e855dfde
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097362"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="cdc52-105">Preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="cdc52-105">Prepare Active Directory</span></span>

<span data-ttu-id="cdc52-106">Per iniziare l'installazione di Skype for Business Server, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti.</span><span class="sxs-lookup"><span data-stu-id="cdc52-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="cdc52-107">La Distribuzione guidata di Skype for Business Server guiderà l'utente attraverso i passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="cdc52-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="cdc52-108">Dopo aver confermato che la replica di Active Directory è riuscita, preparare ogni dominio che ospiterà utenti o server.</span><span class="sxs-lookup"><span data-stu-id="cdc52-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdc52-p103">Per preparare correttamente lo schema, è necessario essere connessi come membri del gruppo Enterprise Admins e del gruppo Schema Admins. Per preparare la foresta, è necessario essere connessi come membri del gruppo Enterprise Admins o come amministratori nella radice della foresta. Per preparare il dominio, è necessario essere connessi come membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="cdc52-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="cdc52-112">Per informazioni dettagliate sulle topologie di Active Directory supportate, vedere [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="cdc52-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="cdc52-113">Per informazioni dettagliate sulla preparazione di Active Directory, vedere [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdc52-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>