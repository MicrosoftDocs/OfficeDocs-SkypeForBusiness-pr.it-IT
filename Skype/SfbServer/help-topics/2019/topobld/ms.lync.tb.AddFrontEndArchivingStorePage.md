---
title: Aggiungere archivio front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: L'archiviazione richiede una versione di 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server, oltre all'istanza di SQL se rver che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).
ms.openlocfilehash: 234d0a2d4ef14aa969b8ef8c7445558e53ca2fee
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794905"
---
# <a name="add-front-end-archiving-store"></a>Aggiungere archivio front-end

L'archiviazione richiede una versione di 64 bit supportata del software di database di Microsoft SQL Server per archiviare i dati di archiviazione. È possibile selezionare un database SQL Server definito in precedenza da usare per l'archiviazione oppure definire un nuovo database di SQL Server specificando un nome di dominio completo (FQDN) del server in cui risiede il database di SQL Server, oltre all'istanza di SQL se rver che si desidera utilizzare per il nuovo database di SQL Server (che può essere l'istanza predefinita o un'istanza denominata specificata).

> [!NOTE]
> Se l'account usato per pubblicare la topologia include i diritti utente e le autorizzazioni appropriati, è possibile creare il database di monitoraggio quando si pubblica la topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione.

> [!NOTE]
> Per installare e distribuire i database nel server basato su SQL Server per il monitoraggio, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è un membro del gruppo sysadmin di SQL Server, è necessario richiedere che venga aggiunto al gruppo fino a quando non vengono distribuiti i file di database. Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per eseguire le procedure, vedere [autorizzazioni di distribuzione per SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) nella documentazione relativa alla distribuzione.


