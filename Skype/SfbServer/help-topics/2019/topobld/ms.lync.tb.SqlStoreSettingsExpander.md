---
title: Espansione delle impostazioni dell'archivio SQL
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un database SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: f77eeb2f397b02231b7d1b004c243f218967c040
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864103"
---
# <a name="sql-store-settings-expander"></a>Espansione delle impostazioni dell'archivio SQL
 
Per modificare le proprietà di un database SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo **Modifica proprietà** per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra **di** dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modifica delle proprietà di un SQL Server database

Per modificare l'istanza SQL Server utilizzata da qualsiasi database diverso dall'archivio di gestione centrale, eseguire la procedura seguente in Generatore di topologie:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Per modificare un'istanza di SQL Server

1. Selezionare il database corretto nel nodo **Archivi SQL** e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** eseguire una di queste operazioni:
    
   - Per utilizzare l'istanza SQL Server predefinita, selezionare **Istanza predefinita** e quindi fare clic su **OK.**
    
   - Per utilizzare un'istanza di database denominata, selezionare **Istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**. È necessario immettere solo il nome dell'istanza(ad esempio ArchivingInstance) e non l'intero SQL Server percorso.
    
Quando si utilizza  la finestra di dialogo Modifica proprietà, Generatore di topologie non verificherà che l'istanza di database immessa sia valida. Ad esempio, se si digita inavvertitamenteArchivingInstanec come nome dell'istanza e quindi si fa clic su **OK,** Generatore di topologie accetterà tale istanza non valida. Prima di pubblicare questa topologia, è necessario correggere questo errore: se non è possibile trovare un'istanza di SQL Server, Generatore di topologie non creerà tale istanza automaticamente.
  

