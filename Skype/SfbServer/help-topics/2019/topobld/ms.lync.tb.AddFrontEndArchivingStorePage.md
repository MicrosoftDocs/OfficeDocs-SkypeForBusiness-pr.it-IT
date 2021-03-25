---
title: Aggiungere l'archivio per Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: L'archiviazione richiede un'edizione a 64 bit supportata del software Microsoft SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui si trova il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita). o un'istanza denominata specificata dall'utente.
ms.openlocfilehash: ae9c90cedc7be4e60689978b28eecce2031a4991
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122667"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="d2bd2-104">Aggiungere archivio front-end</span><span class="sxs-lookup"><span data-stu-id="d2bd2-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="d2bd2-105">L'archiviazione richiede un'edizione a 64 bit supportata del software Microsoft SQL Server database per archiviare i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="d2bd2-106">È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui si trova il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita). o un'istanza denominata specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="d2bd2-p103">Se l'account usato per pubblicare la topologia ha le autorizzazioni e i diritti utente corretti, sarà possibile creare il database di monitoraggio durante la pubblicazione della topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d2bd2-109">Per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d2bd2-110">Se non si è membri del gruppo SQL Server sysadmin, è necessario richiedere di essere aggiunti al gruppo fino alla distribuzione dei file di database.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d2bd2-111">Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d2bd2-112">Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>