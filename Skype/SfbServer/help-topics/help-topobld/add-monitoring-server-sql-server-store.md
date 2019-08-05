---
title: Aggiungere il server di monitoraggio di SQL Server Store
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Per archiviare i dati di monitoraggio, server di monitoraggio richiede un'edizione di 64 bit supportata del software di database di SQL Server. È possibile selezionare un database SQL Server definito in precedenza da usare per il monitoraggio oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server, oltre all'istanza di SQL Server che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: c6ccf465f5ed34fd6491305d9e9fa6d8309b43e9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187148"
---
# <a name="add-monitoring-server-sql-server-store"></a>Aggiungere il server di monitoraggio di SQL Server Store

Per archiviare i dati di monitoraggio, server di monitoraggio richiede un'edizione di 64 bit supportata del software di database di SQL Server. È possibile selezionare un database SQL Server definito in precedenza da usare per il monitoraggio oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiederà il database di SQL Server, oltre all'istanza di SQL Server che si vuole usare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

Per informazioni dettagliate sul supporto di SQL Server, vedere [software di database e supporto](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) di clustering nella documentazione relativa alla supportabilità. Per informazioni dettagliate sul database di monitoraggio, inclusa la collocazione del database di monitoraggio, vedere [percorso del server supportato](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa alla supportabilità,[pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) nella documentazione di pianificazione e [dati di SQL Server e registrare la posizione dei file](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.

> [!NOTE]
> Se l'account usato per pubblicare la topologia include i diritti utente e le autorizzazioni appropriati, è possibile creare il database di monitoraggio quando si pubblica la topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione. > per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire queste procedure, vedere [autorizzazioni di distribuzione per SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.


