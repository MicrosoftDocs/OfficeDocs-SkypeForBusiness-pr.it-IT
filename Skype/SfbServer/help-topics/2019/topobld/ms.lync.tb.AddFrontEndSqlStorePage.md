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
description: Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database. Di conseguenza, tutte le opzioni sono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.
ms.openlocfilehash: 6861fd20c8f3e164a4d8d713dfc725bd2f949acd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118675"
---
# <a name="add-front-end-sql-server-store"></a>Aggiungere archivio di Front End SQL Server

Una distribuzione server Standard Edition installa automaticamente il software di database Microsoft SQL Server Express e SQL Server database. Di conseguenza, tutte le opzioni sono prepopolato e non è possibile apportare modifiche alla configurazione predefinita.

Il pool Front End di una distribuzione di server Enterprise Edition richiede un'edizione a 64 bit supportata del software di database SQL Server per il database back-end. È possibile selezionare un database SQL Server definito in precedenza da utilizzare per il database back-end oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui si trova il database di SQL Server e l'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita). o un'istanza denominata specificata dall'utente. È inoltre possibile scegliere di abilitare il mirroring nell SQL Server e specificare un controllo del mirroring per il failover automatico.

Per informazioni dettagliate SQL Server supporto, vedere [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla SQL Server per il database back-end, vedere [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) nella documentazione relativa alla distribuzione.

> [!NOTE]
> Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti utente appropriati, è possibile creare il database back-end (RTC) quando si pubblica la topologia. È anche possibile creare il database in un secondo momento, persino come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per una distribuzione Enterprise Edition, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo SQL Server sysadmins, è necessario richiedere di essere aggiunti al gruppo fino alla distribuzione dei file di database. Se non è possibile essere membri del gruppo sysadmins, è necessario fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sui diritti utente e sulle autorizzazioni necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).