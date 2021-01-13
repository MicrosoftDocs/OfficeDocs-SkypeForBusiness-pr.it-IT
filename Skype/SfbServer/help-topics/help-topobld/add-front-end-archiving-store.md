---
title: Aggiungere l'archivio per Front End Server
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Archiviazione richiede un'edizione a 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 9e094bacca87e6b70a7caa1db9c43a5c98c0edbd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824216"
---
# <a name="add-front-end-archiving-store"></a>Aggiungere archivio front-end

Archiviazione richiede un'edizione a 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database di SQL Server definito in precedenza da utilizzare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui deve risiedere il database di SQL Server, oltre all'istanza di SQL Server che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

> [!NOTE]
> Se l'account usato per pubblicare la topologia ha le autorizzazioni e i diritti utente corretti, sarà possibile creare il database di monitoraggio durante la pubblicazione della topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmins di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo sysadmin di SQL Server, è necessario richiederne l'aggiunta al gruppo fino alla distribuzione dei file di database. Se non è possibile rendere membro del gruppo sysadmin, è necessario fornire all'amministratore di database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sulle autorizzazioni e sui diritti utente necessari per eseguire le procedure, vedere [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.


