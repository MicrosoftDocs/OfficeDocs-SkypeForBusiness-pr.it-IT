---
title: Espansione delle impostazioni dell'archivio SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza del database di SQL Server. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805516"
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
  

