---
title: Espansione delle impostazioni dell'archivio SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Per modificare le proprietà di un SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: 83bf11af40e8c51693b2b1768f1d71c9bc2f37f9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609373"
---
# <a name="sql-store-settings-expander"></a>Espansione delle impostazioni dell'archivio SQL
 
Per modificare le proprietà di un SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo **Modifica proprietà** per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra **di** dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modifica delle proprietà di un SQL Server database

Per modificare l'istanza SQL Server utilizzata da qualsiasi database diverso dall'archivio di gestione centrale, eseguire la procedura seguente in Generatore di topologie:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Per modificare un'istanza di SQL Server

1. Selezionare il database corretto nel nodo **Archivi SQL** e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** eseguire una di queste operazioni:
    
   - Per utilizzare l'istanza SQL Server predefinita, selezionare **Istanza predefinita** e quindi fare clic su **OK.**
    
   - Per utilizzare un'istanza di database denominata, selezionare **Istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**. È necessario immettere solo il nome dell'istanza ,ad esempio ArchivingInstance, e non l'SQL Server percorso completo.
    
Quando si utilizza  la finestra di dialogo Modifica proprietà, Generatore di topologie non verificherà che l'istanza di database immessa sia valida. Ad esempio, se si digita inavvertitamenteArchivingInstanec come nome dell'istanza e quindi si fa clic su **OK,** Generatore di topologie accetterà tale istanza non valida. Prima di pubblicare questa topologia, è necessario correggere questo errore: se non è possibile trovare un'istanza di SQL Server, Generatore di topologie non creerà tale istanza automaticamente.
  

