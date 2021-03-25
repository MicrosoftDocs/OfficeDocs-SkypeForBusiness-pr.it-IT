---
title: Aggiungere un archivio SQL Server di monitoraggio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Monitoring Server richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di monitoraggio. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per il monitoraggio oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita). o un'istanza denominata specificata dall'utente.
ms.openlocfilehash: 5c1ef4c7b2474a094492aa7905c044a5da145ff5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119725"
---
# <a name="add-monitoring-server-sql-server-store"></a>Aggiungere un archivio SQL Server di monitoraggio

Monitoring Server richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di monitoraggio. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per il monitoraggio oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita). o un'istanza denominata specificata dall'utente.

Per informazioni dettagliate SQL Server supporto, vedere [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sul database di monitoraggio, inclusa la collocazione del database di monitoraggio, vedere [Supported Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) nella documentazione relativa al supporto, Planning for[Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) nella documentazione relativa alla pianificazione e SQL Server Data and Log File Placement nella documentazione relativa alla [distribuzione.](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti utente appropriati, sarà possibile creare il database di monitoraggio durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, persino come parte della procedura di installazione. > Per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo SQL Server sysadmin, è necessario richiedere di essere aggiunti al gruppo fino alla distribuzione dei file di database. Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sui diritti utente e sulle autorizzazioni necessari per eseguire queste procedure, [vedere Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) nella documentazione relativa alla distribuzione.