---
title: Aggiungere archivio di Front End SQL Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database. Di conseguenza, tutte le opzioni vengono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811636"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="7fd7c-104">Aggiungere archivio di Front End SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fd7c-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="7fd7c-105">Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="7fd7c-106">Di conseguenza, tutte le opzioni vengono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="7fd7c-107">Il pool Front End di una distribuzione di server Enterprise Edition richiede un'edizione a 64 bit supportata del software di database SQL Server per il database back-end.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="7fd7c-108">È possibile selezionare un database SQL Server definito in precedenza da utilizzare per il database back-end oppure definire un nuovo database SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database SQL Server ( che può essere l'istanza predefinita oppure un'istanza denominata specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="7fd7c-109">È inoltre possibile scegliere di abilitare il mirroring nell SQL Server store e specificare un controllo del mirroring per il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="7fd7c-110">Per informazioni dettagliate SQL Server supporto, vedere [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="7fd7c-111">Per informazioni dettagliate sulla configurazione SQL Server per il database back-end, vedere [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="7fd7c-112">Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti utente appropriati, è possibile creare il database back-end (rtc) durante la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="7fd7c-113">È anche possibile creare il database in un secondo momento, persino come parte della procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="7fd7c-114">Per installare e distribuire i database nel server basato su SQL Server per una distribuzione Enterprise Edition, è necessario essere membri del gruppo SQL Server sysadmins per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7fd7c-115">Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7fd7c-116">Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database.</span><span class="sxs-lookup"><span data-stu-id="7fd7c-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7fd7c-117">Per informazioni dettagliate sui diritti utente e sulle autorizzazioni necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="7fd7c-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


