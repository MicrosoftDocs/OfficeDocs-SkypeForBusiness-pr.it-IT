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
description: Per modificare le proprietà di un database SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Non è inoltre possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805516"
---
# <a name="sql-store-settings-expander"></a>Espansione delle impostazioni dell'archivio SQL
 
Per modificare le proprietà di un database SQL Server database, è necessario modificare l'istanza SQL Server database. Non è possibile usare la finestra di dialogo **Modifica proprietà** per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Non è inoltre possibile utilizzare la finestra **di** dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modifica delle proprietà di un SQL Server database

Per modificare l'istanza di SQL Server utilizzata da qualsiasi database diverso dall'archivio di gestione centrale, eseguire la procedura seguente in Generatore di topologie:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Per modificare un'istanza di SQL Server

1. Selezionare il database corretto nel nodo **Archivi SQL** e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** eseguire una di queste operazioni:
    
   - Per utilizzare l'istanza SQL Server predefinita, selezionare **Istanza predefinita** e quindi fare clic su **OK.**
    
   - Per utilizzare un'istanza di database denominata, selezionare **Istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**. È necessario immettere solo il nome dell'istanza(ad esempio, ArchivingInstance) e non l'intero SQL Server percorso.
    
Quando si utilizza  la finestra di dialogo Modifica proprietà, Generatore di topologie non verifica che l'istanza di database immessa sia valida. Se ad esempio si digita inavvertitamenteArchivingInstanec come nome dell'istanza e quindi si fa clic su **OK,** Generatore di topologie accetterà tale istanza non valida. Prima di pubblicare questa topologia, è necessario correggere questo errore: se non è possibile trovare un'istanza di SQL Server, generatore di topologie non creerà tale istanza automaticamente.
  

