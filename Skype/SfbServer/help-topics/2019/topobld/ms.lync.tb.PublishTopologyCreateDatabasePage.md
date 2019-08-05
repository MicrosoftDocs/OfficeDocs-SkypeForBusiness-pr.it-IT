---
title: Crea database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Generatore di topologie consente di installare database in un archivio di SQL Server. Quando si installano database tramite Generatore di topologia, l'applicazione legge le informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster di SQL Server specificato. Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie. Se è necessario installare un database specifico in uno specifico computer o se è necessario installare un database collocato, è necessario usare l'interfaccia della riga di comando di Windows PowerShell e il cmdlet Install-CsDatabase.
ms.openlocfilehash: 5736e399771eef30808e62c8a11876d1b6f3d8ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195332"
---
# <a name="create-database"></a>Crea database
 
Generatore di topologie consente di installare database in un archivio di SQL Server. Quando si installano database tramite Generatore di topologia, l'applicazione legge le informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster di SQL Server specificato. Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie. Se è necessario installare un database specifico in uno specifico computer o se è necessario installare un database collocato, è necessario usare l'interfaccia della riga di comando di Windows PowerShell e il cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Creazione di un database

1. Fare clic sul nodo di Skype for Business Server e quindi fare clic su **Installa database**.
    
2. Nella pagina **Crea database** della finestra di dialogo **Installa database** selezionare il nome di dominio completo (FQDN) dell'archivio di SQL Server in cui devono essere creati i nuovi database.
    
3. Fare clic su **Avanzate**. Nella finestra di dialogo **Seleziona percorso file di database** selezionare una delle opzioni seguenti:
    
   - **Determina automaticamente il percorso dei file di database**. Se si seleziona questa opzione, il Generatore di topologie userà un algoritmo predefinito per scegliere il percorso di archiviazione dei registri di database e dei file di dati.
    
   - **Utilizza i valori predefiniti dell'istanza di SQL Server**. Se si seleziona questa opzione, non verrà usato l'algoritmo predefinito per scegliere i percorsi di archiviazione dei file di dati e dei log di database. I file di log e di dati vengono invece archiviati nei percorsi specificati dal percorso predefinito di SQL Server (questi percorsi devono essere configurati in modo avanzato da un amministratore di SQL Server). I file di dati verranno perciò archiviati nel percorso dei file di dati predefinito di SQL Server, mentre i file di log verranno archiviati nel percorso dei file di log predefinito di SQL Server.
    
4. Fare clic su **OK**.
    
5. Nella pagina **Crea database** fare clic su **Avanti**.
    
6. Nella pagina **Creazione del database completata** fare clic su **Fine**.
    

