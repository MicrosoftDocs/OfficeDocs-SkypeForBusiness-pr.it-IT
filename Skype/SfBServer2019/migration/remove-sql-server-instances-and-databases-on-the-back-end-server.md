---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che i database siano obsoleti o non disponibili.
ms.openlocfilehash: f9e942f1f5516c0bf3437dd3fc9e2dc25b4cc4236e3cffabbf07ff08dde1e404
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306209"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Rimuovere database e istanze di SQL Server nel server back-end

Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che i database siano obsoleti o non disponibili.
  
Per rimuovere i database o le istanze per il server di archiviazione o il Monitoring Server, è necessario innanzitutto rimuovere il ruolo del server. Analogamente, per rimuovere le istanze o i database per il pool Front End, è necessario innanzitutto rimuovere o riconfigurare il ruolo del server dipendente. Per queste procedure non viene fatta distinzione tra database collocati o istanze separate dei server. La collocazione dei database non incide sulle procedure.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Rimuovere il database di SQL Server per un server di monitoraggio](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Rimuovere il database di SQL Server per un server di archiviazione](remove-the-sql-server-database-for-an-archiving-server.md)
    

