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
description: Per iniziare l'installazione di Skype for Business Server, è necessario preparare lo schema dei servizi di dominio Active Directory, la foresta e i domini che ospiteranno i server e gli utenti. La distribuzione guidata di Skype for Business Server vi guiderà nei passaggi necessari per preparare Active Directory, iniziando dallo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory ha esito positivo, è necessario preparare ogni dominio che ospiterà gli utenti o i server.
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825051"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="33c75-105">Preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="33c75-105">Prepare Active Directory</span></span>

<span data-ttu-id="33c75-106">Per iniziare l'installazione di Skype for Business Server, è necessario preparare lo schema dei servizi di dominio Active Directory, la foresta e i domini che ospiteranno i server e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="33c75-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="33c75-107">La distribuzione guidata di Skype for Business Server vi guiderà nei passaggi necessari per preparare Active Directory, iniziando dallo schema e quindi nella preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="33c75-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="33c75-108">Dopo aver confermato che la replica di Active Directory ha esito positivo, è necessario preparare ogni dominio che ospiterà gli utenti o i server.</span><span class="sxs-lookup"><span data-stu-id="33c75-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33c75-p103">Per preparare correttamente lo schema, è necessario essere connessi come membri del gruppo Enterprise Admins e del gruppo Schema Admins. Per preparare la foresta, è necessario essere connessi come membri del gruppo Enterprise Admins o come amministratori nella radice della foresta. Per preparare il dominio, è necessario essere connessi come membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="33c75-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="33c75-112">Per informazioni dettagliate sulle topologie di Active Directory supportate, vedere [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="33c75-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="33c75-113">Per informazioni dettagliate sulla preparazione di Active Directory, vedere [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="33c75-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


