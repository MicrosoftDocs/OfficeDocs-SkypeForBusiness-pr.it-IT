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
description: Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 5200562ce8db04b741bfba7f62fbe42a2c8f47df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803686"
---
# <a name="add-archiving-server-sql-server-store"></a>Aggiungere archivio SQL Server per il server di archiviazione

Il server di archiviazione richiede un'edizione a 64 bit supportata del software SQL Server database per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per l'archiviazione o definire un nuovo database SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone dei diritti utente e delle autorizzazioni appropriate, sarà possibile creare un il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in seguito, come parte della procedura di installazione o in altro modo.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per l'archiviazione, è necessario essere membri del gruppo SQL Server sysadmins per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.


