---
title: Aggiungere l'archivio SQL Server per il server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 471001fbd003211c1f4d47e36c7ad434277ff383f3a262a5a10376d3b6dee617
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315862"
---
# <a name="add-archiving-server-sql-server-store"></a>Aggiungere archivio SQL Server per il server di archiviazione

Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone dei diritti utente e delle autorizzazioni appropriate, sarà possibile creare un il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in seguito, come parte della procedura di installazione o in altro modo.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per l'archiviazione, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile essere membri del gruppo sysadmins, è consigliabile fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) nella documentazione relativa alla distribuzione.