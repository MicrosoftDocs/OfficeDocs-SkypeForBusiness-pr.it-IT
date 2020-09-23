---
title: Aggiungere l'archivio per Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Archiviazione richiede un'edizione a 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216717"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="81a7c-104">Aggiungere l'archivio per Front End Server</span><span class="sxs-lookup"><span data-stu-id="81a7c-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="81a7c-105">Archiviazione richiede un'edizione a 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="81a7c-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="81a7c-106">È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).</span><span class="sxs-lookup"><span data-stu-id="81a7c-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="81a7c-p103">Se l'account usato per pubblicare la topologia ha le autorizzazioni e i diritti utente corretti, sarà possibile creare il database di monitoraggio durante la pubblicazione della topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="81a7c-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="81a7c-109">Per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="81a7c-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="81a7c-110">Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiederne l'aggiunta al gruppo fino alla distribuzione dei file di database.</span><span class="sxs-lookup"><span data-stu-id="81a7c-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="81a7c-111">Se non è possibile rendere membro del gruppo sysadmin, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database.</span><span class="sxs-lookup"><span data-stu-id="81a7c-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="81a7c-112">Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="81a7c-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


