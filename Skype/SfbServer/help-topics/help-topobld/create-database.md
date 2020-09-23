---
title: Creare un database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Generatore di topologie consente di installare i database in un archivio di SQL Server. Quando si installano i database utilizzando il generatore di topologie, l'applicazione legge informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster di SQL Server specificato. Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie. Se è necessario installare un database specifico in un computer specifico o se è necessario installare un database collocato, è necessario utilizzare l'interfaccia della riga di comando di Windows PowerShell e il cmdlet Install-CsDatabase.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219507"
---
# <a name="create-database"></a>Creazione database
 
Generatore di topologie consente di installare i database in un archivio di SQL Server. Quando si installano i database utilizzando il generatore di topologie, l'applicazione legge informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster di SQL Server specificato. Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie. Se è necessario installare un database specifico in un computer specifico o se è necessario installare un database collocato, è necessario utilizzare l'interfaccia della riga di comando di Windows PowerShell e il cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Creazione di un database

1. Fare clic sul nodo Skype for Business Server 2015 e quindi fare clic su **Installa database**.
    
2. Nella pagina **Crea database** della finestra di dialogo **Installa** database selezionare il nome di dominio completo (FQDN) dell'archivio SQL Server in cui devono essere creati i nuovi database.
    
3. Fare clic su **Avanzate**. Nella finestra di dialogo **Seleziona percorso file di database** selezionare una delle opzioni seguenti:
    
   - **Determina automaticamente il percorso dei file di database**. Se si seleziona questa opzione, il Generatore di topologie userà un algoritmo predefinito per scegliere il percorso di archiviazione dei registri di database e dei file di dati.
    
   - **Utilizza i valori predefiniti dell'istanza di SQL Server**. Se si seleziona questa opzione, non verrà usato l'algoritmo predefinito per scegliere i percorsi di archiviazione dei file di dati e dei log di database. Tali file vengono invece archiviati nei percorsi predefiniti di SQL Server, configurati preventivamente da un amministratore di SQL Server. I file di dati verranno perciò archiviati nel percorso dei file di dati predefinito di SQL Server, mentre i file di log verranno archiviati nel percorso dei file di log predefinito di SQL Server.
    
4. Fare clic su **OK**.
    
5. Nella pagina **Creare database** fare clic su **Avanti**.
    
6. Nella pagina **Creazione del database completata** fare clic su **Fine**.
    

