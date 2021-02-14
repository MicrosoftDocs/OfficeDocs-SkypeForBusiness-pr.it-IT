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
description: Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che il rendering dei database sia obsoleto o non disponibile.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752158"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Rimuovere database e istanze di SQL Server nel server back-end

Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che il rendering dei database sia obsoleto o non disponibile.
  
Per rimuovere i database o le istanze per il server di archiviazione o il Monitoring Server, è necessario innanzitutto rimuovere il ruolo del server. Analogamente, per rimuovere le istanze o i database per il pool Front End, è necessario innanzitutto rimuovere o riconfigurare il ruolo del server dipendente. Per queste procedure non viene fatta distinzione tra database collocati o istanze separate dei server. La collocazione dei database non incide sulle procedure.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Rimuovere il database di SQL Server per un server di monitoraggio](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Rimuovere il database di SQL Server per un server di archiviazione](remove-the-sql-server-database-for-an-archiving-server.md)
    

