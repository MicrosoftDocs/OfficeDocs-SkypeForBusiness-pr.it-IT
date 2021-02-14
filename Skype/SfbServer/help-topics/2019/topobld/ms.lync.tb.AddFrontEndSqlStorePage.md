---
title: Aggiungere archivio di Front End SQL Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database. Di conseguenza, tutte le opzioni vengono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811636"
---
# <a name="add-front-end-sql-server-store"></a>Aggiungere archivio di Front End SQL Server

Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database. Di conseguenza, tutte le opzioni vengono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.

Il pool Front End di una distribuzione di server Enterprise Edition richiede un'edizione a 64 bit supportata del software di database SQL Server per il database back-end. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per il database back-end oppure definire un nuovo database SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database SQL Server ( che può essere l'istanza predefinita oppure un'istanza denominata specificata dall'utente. È inoltre possibile scegliere di abilitare il mirroring nell SQL Server store e specificare un controllo del mirroring per il failover automatico.

Per informazioni dettagliate SQL Server supporto, vedere [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla configurazione SQL Server per il database back-end, vedere [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) nella documentazione relativa alla distribuzione.

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti utente appropriati, è possibile creare il database back-end (rtc) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, persino come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per una distribuzione Enterprise Edition, è necessario essere membri del gruppo SQL Server sysadmins per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sui diritti utente e sulle autorizzazioni necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


