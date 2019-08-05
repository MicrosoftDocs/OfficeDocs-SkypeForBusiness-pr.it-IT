---
title: Aggiungere front-end SQL Server Store
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una distribuzione di server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express richiesto e il database di SQL Server. Tutte le opzioni sono pertanto prepopolate e non è possibile apportare modifiche alla configurazione predefinita.
ms.openlocfilehash: 589870007c2a9dea187038e7a4197b16aad25578
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194979"
---
# <a name="add-front-end-sql-server-store"></a>Aggiungere front-end SQL Server Store

Una distribuzione di server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express richiesto e il database di SQL Server. Tutte le opzioni sono pertanto prepopolate e non è possibile apportare modifiche alla configurazione predefinita.

Il pool Front-End di una distribuzione del server Enterprise Edition richiede una versione di 64 bit supportata del software di database di SQL Server per il database back-end. È possibile selezionare un database SQL Server definito in precedenza da usare per il database back-end oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server e l'istanza di SQL S erver che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata). È anche possibile scegliere di abilitare il mirroring in SQL Server Store e specificare un witness di mirroring per il failover automatico.

Per informazioni dettagliate sul supporto di SQL Server, vedere [software di database e supporto](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) di clustering nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla configurazione di SQL Server per il database back-end, vedere [configurare SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) nella documentazione relativa alla distribuzione.

> [!NOTE]
> Se l'account usato per pubblicare la topologia include i diritti utente e le autorizzazioni appropriati, è possibile creare il database back-end (RTC) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per una distribuzione di Enterprise Edition, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire le procedure, vedere [autorizzazioni di distribuzione per SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


