---
title: Expander delle impostazioni di SQL Store
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza di database di SQL Server. Non è possibile usare la finestra di dialogo Modifica proprietà per eseguire attività come lo spostamento del database del server di archiviazione da un computer a un altro. Inoltre, non è possibile usare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'Central Management store.
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195430"
---
# <a name="sql-store-settings-expander"></a>Expander delle impostazioni di SQL Store
 
Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza di database di SQL Server. Non è possibile usare la finestra di dialogo **modifica proprietà** per eseguire attività come lo spostamento del database del server di archiviazione da un computer a un altro. Inoltre, non è possibile usare la finestra di dialogo **modifica proprietà** per modificare l'istanza di SQL Server che ospita l'Central Management store.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modifica delle proprietà di un database di SQL Server

Per modificare l'istanza di SQL Server utilizzata da qualsiasi database diverso da Central Management store, completare la procedura seguente in Generatore di topologie:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Per modificare un'istanza di SQL Server

1. Selezionare il database appropriato nel nodo **Archivi SQL** e quindi fare clic su **modifica proprietà**.
    
2. Nella finestra di dialogo **modifica proprietà** eseguire una delle operazioni seguenti:
    
   - Per usare l'istanza predefinita di SQL Server, selezionare **istanza predefinita** e quindi fare clic su **OK**.
    
   - Per usare un'istanza di database denominata, selezionare **istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**. È necessario immettere solo il nome dell'istanza, ad esempio ArchivingInstance, e non l'intero percorso di SQL Server.
    
Quando si lavora nella finestra di dialogo **modifica proprietà** , generatore di topologia non verificherà che l'istanza di database immessa sia un'istanza valida. Ad esempio, se typeArchivingInstanec inavvertitamente come nome dell'istanza e quindi fai clic su **OK**, generatore di topologie accetterà l'istanza non valida. Prima di poter pubblicare la topologia, è necessario correggere l'errore: se non è possibile trovare un'istanza di SQL Server, il generatore di topologia non creerà l'istanza desiderata.
  

