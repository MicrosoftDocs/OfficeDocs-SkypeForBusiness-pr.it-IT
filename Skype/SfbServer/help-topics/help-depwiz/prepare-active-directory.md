---
title: Preparare Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Per iniziare l'installazione di Skype for Business Server 2015, è necessario preparare lo schema di servizi di dominio Active Directory, la foresta e i domini che ospiteranno server e utenti. La distribuzione guidata di Skype for Business Server ti guiderà nei passaggi necessari per preparare Active Directory, a partire dallo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory è riuscita, è necessario preparare ogni dominio che ospiterà utenti o server.
ms.openlocfilehash: a7b908bb1c6194e1b6d9b12a90d250d09815ea5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189722"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="3d103-105">Preparare Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d103-105">Prepare Active Directory</span></span>

<span data-ttu-id="3d103-106">Per iniziare l'installazione di Skype for Business Server 2015, è necessario preparare lo schema di servizi di dominio Active Directory, la foresta e i domini che ospiteranno server e utenti.</span><span class="sxs-lookup"><span data-stu-id="3d103-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="3d103-107">La distribuzione guidata di Skype for Business Server ti guiderà nei passaggi necessari per preparare Active Directory, a partire dallo schema e quindi nella preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="3d103-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="3d103-108">Dopo aver confermato che la replica di Active Directory è riuscita, è necessario preparare ogni dominio che ospiterà utenti o server.</span><span class="sxs-lookup"><span data-stu-id="3d103-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d103-p103">Per preparare correttamente lo schema, è necessario essere connessi come membri del gruppo Enterprise Admins e del gruppo Schema Admins. Per preparare la foresta, è necessario essere connessi come membri del gruppo Enterprise Admins o come amministratori nella radice della foresta. Per preparare il dominio, è necessario essere connessi come membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="3d103-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="3d103-p104">Per informazioni dettagliate sulle topologie Active Directory supportate, vedere [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) nella documentazione relativa al supporto. Per informazioni dettagliate sulla preparazione di Active Directory, vedere [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3d103-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


