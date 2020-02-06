---
title: Aggiungere un archivio di SQL Server di archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Il server di archiviazione richiede una versione di 64 bit supportata del software di database di SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione o la definizione di un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server e l'istanza di SQL Server che che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: d4fcb526abf0eb1ef961f5790b574a9f30a80b87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821288"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="addf2-104">Aggiungere un archivio di SQL Server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="addf2-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="addf2-105">Il server di archiviazione richiede una versione di 64 bit supportata del software di database di SQL Server per archiviare i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="addf2-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="addf2-106">È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione o la definizione di un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server e l'istanza di SQL Server che che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).</span><span class="sxs-lookup"><span data-stu-id="addf2-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="addf2-107">Se l'account usato per pubblicare la topologia include i diritti utente e le autorizzazioni appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="addf2-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="addf2-108">È anche possibile creare il database in un secondo momento, come parte della procedura di installazione o in altro modo.</span><span class="sxs-lookup"><span data-stu-id="addf2-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="addf2-109">Per installare e distribuire i database nel server basato su SQL Server per l'archiviazione, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="addf2-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="addf2-110">Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database.</span><span class="sxs-lookup"><span data-stu-id="addf2-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="addf2-111">Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database.</span><span class="sxs-lookup"><span data-stu-id="addf2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="addf2-112">Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire le procedure, vedere [autorizzazioni di distribuzione per SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="addf2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


