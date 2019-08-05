---
title: Aggiungere l'archiviazione di SQL Server Store
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Il server di archiviazione richiede una versione di 64 bit supportata del software di database di SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione o la definizione di un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server e l'istanza di SQL Server che che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 9d9d5af7e769a22c7742029d786826e3d2b3c998
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195558"
---
# <a name="add-archiving-server-sql-server-store"></a>Aggiungere l'archiviazione di SQL Server Store

Il server di archiviazione richiede una versione di 64 bit supportata del software di database di SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione o la definizione di un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server e l'istanza di SQL Server che che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

> [!NOTE]
> Se l'account usato per pubblicare la topologia include i diritti utente e le autorizzazioni appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, come parte della procedura di installazione o in altro modo.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per l'archiviazione, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire le procedure, vedere [autorizzazioni di distribuzione per SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.


