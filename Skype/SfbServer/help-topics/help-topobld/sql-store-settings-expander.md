---
title: Espansione delle impostazioni dell'archivio SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza del database di SQL Server. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219611"
---
# <a name="sql-store-settings-expander"></a>Espansione delle impostazioni dell'archivio SQL
 
Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza del database di SQL Server. Non è possibile usare la finestra di dialogo **Modifica proprietà** per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo **modifica proprietà** per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modifica delle proprietà di un database di SQL Server

Per modificare l'istanza di SQL Server utilizzata da qualsiasi database diverso dall'archivio di gestione centrale, eseguire la procedura seguente in Generatore di topologie:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Per modificare un'istanza di SQL Server

1. Selezionare il database corretto nel nodo **Archivi SQL** e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** eseguire una di queste operazioni:
    
   - Per utilizzare l'istanza predefinita di SQL Server, selezionare **istanza predefinita** e quindi fare clic su **OK**.
    
   - Per utilizzare un'istanza di database denominata, selezionare **Istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**. È necessario immettere solo il nome dell'istanza (ad esempio, ArchivingInstance) e non l'intero percorso di SQL Server.
    
Quando si utilizza la finestra di dialogo **modifica proprietà** , il generatore di topologie non verificherà che l'istanza di database immessa sia un'istanza valida. Ad esempio, se si è inavvertitamente typeArchivingInstanec come nome dell'istanza e quindi fare clic su **OK**, generatore di topologie accetterà l'istanza non valida. Prima di poter pubblicare la topologia, è necessario correggere l'errore: se non è possibile trovare un'istanza di SQL Server, il generatore di topologie non creerà quell'istanza per l'utente.
  

