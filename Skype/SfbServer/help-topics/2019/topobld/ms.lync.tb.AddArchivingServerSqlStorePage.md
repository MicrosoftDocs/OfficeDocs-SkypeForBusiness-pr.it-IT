---
title: Aggiungere l'archivio SQL Server per il server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: ff6cec0d083e4597dec7ae61df08b16ff8feab7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100212"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="ea6ed-104">Aggiungere archivio SQL Server per il server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ea6ed-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="ea6ed-105">Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="ea6ed-106">È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).</span><span class="sxs-lookup"><span data-stu-id="ea6ed-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="ea6ed-p103">Se l'account utilizzato per pubblicare la topologia dispone dei diritti utente e delle autorizzazioni appropriate, sarà possibile creare un il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in seguito, come parte della procedura di installazione o in altro modo.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="ea6ed-109">Per installare e distribuire i database nel server basato su SQL Server per l'archiviazione, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="ea6ed-110">Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere di essere aggiunti al gruppo fino alla distribuzione dei file di database.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="ea6ed-111">Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="ea6ed-112">Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea6ed-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>