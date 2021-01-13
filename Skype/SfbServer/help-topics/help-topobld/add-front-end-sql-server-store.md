---
title: Aggiungere archivio di Front End SQL Server
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
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Una distribuzione di server Standard Edition installa automaticamente il software di database SQL Server Express e il database di SQL Server necessari. Pertanto, tutte le opzioni sono precompilate e non è possibile apportare modifiche alla configurazione predefinita.
ms.openlocfilehash: 939f12fa02951074e487066337c8bb76af59143a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824076"
---
# <a name="add-front-end-sql-server-store"></a>Aggiungere archivio di Front End SQL Server

Una distribuzione di server Standard Edition installa automaticamente il software di database SQL Server Express e il database di SQL Server necessari. Pertanto, tutte le opzioni sono precompilate e non è possibile apportare modifiche alla configurazione predefinita.

Il pool Front End di una distribuzione del server Enterprise Edition richiede un'edizione a 64 bit supportata del software di database di SQL Server per il database back-end. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per il database back-end oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata). È inoltre possibile scegliere di abilitare il mirroring nell'archivio SQL Server e specificare un controllo del mirroring per il failover automatico.

Per informazioni dettagliate sul supporto di SQL Server, vedere [database software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sull'impostazione di SQL Server per il database back-end, vedere [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) nella documentazione relativa alla distribuzione.

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone dei diritti e delle autorizzazioni utente appropriate, è possibile creare il database back-end (RTC) quando si pubblica la topologia. È anche possibile creare il database in un secondo momento, persino come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per una distribuzione di Enterprise Edition, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è un membro del gruppo sysadmins di SQL Server, è necessario richiederne l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile rendere membro del gruppo sysadmin, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


