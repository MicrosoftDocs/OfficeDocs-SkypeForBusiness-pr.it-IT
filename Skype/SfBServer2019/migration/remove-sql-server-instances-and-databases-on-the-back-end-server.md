---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in uso, oppure dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente in modo che esegua il rendering dei database obsoleti o non disponibili.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812984"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Rimuovere database e istanze di SQL Server nel server back-end

Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in uso, oppure dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente in modo che esegua il rendering dei database obsoleti o non disponibili.
  
Per rimuovere i database o le istanze per il server di archiviazione o il server di monitoraggio, è necessario prima di tutto rimuovere il ruolo del server. Allo stesso modo, per rimuovere le istanze o i database per il pool Front-End, devi prima rimuovere o riconfigurare il ruolo del server dipendente. Queste procedure non fanno distinzione tra database collocati o istanze separate per i server. Le procedure non sono influenzate dalla collocazione dei database.
  
## <a name="in-this-section"></a>In questa sezione

- [Rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Rimuovere il database di SQL Server per un server di monitoraggio](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Rimuovere il database di SQL Server per un server di archiviazione](remove-the-sql-server-database-for-an-archiving-server.md)
    

