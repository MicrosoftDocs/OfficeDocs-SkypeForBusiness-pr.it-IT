---
title: Backup e ripristino dei database di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Riepilogo: informazioni su come eseguire il backup e il ripristino di database del server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817342"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Backup e ripristino dei database di Chat persistente
 
**Riepilogo:** Informazioni su come eseguire il backup e il ripristino di database del server di chat persistente in Skype for Business Server 2015.
  
Il server di chat persistente richiede il software di database di SQL Server per archiviare i dati delle chat room, ad esempio cronologia e contenuto, configurazione, provisioning degli utenti e altri metadati rilevanti. Inoltre, se l'organizzazione ha regole che richiedono l'archiviazione di attività della chat persistente e il servizio di conformità facoltativo è abilitato, il software di database di SQL Server viene usato per archiviare i dati di conformità, inclusi il contenuto della chat e gli eventi, ad esempio entrare e uscire dalle sale. Il contenuto della chat room è archiviato nel database della chat persistente (MGC). I dati di conformità vengono archiviati nel database di conformità (mgccomp). Si tratta di dati business-critical di cui eseguire il backup regolarmente. 
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

## <a name="back-up-the-databases"></a>Eseguire il backup dei database

Esistono due modi per eseguire il backup dei dati della chat persistente. 
  
- Backup di SQL Server
    
- Cmdlet **Export-CsPersistentChatData** , che esporta i dati della chat persistente come file
    
I dati creati con SQL Server backup richiedono molto più spazio su disco, possibilmente 20 volte di più, rispetto a quelli creati dal cmdlet **Export-CsPersistentChatData** , ma è probabile che SQL Server backup sia una procedura con cui si ha familiarità.
  
Se si vogliono usare le procedure di backup di SQL Server, vedere la documentazione di SQL per altre informazioni. 
  
Se si vuole usare il cmdlet **Export-CsPersistentChatData** , è possibile specificare il comando come indicato di seguito:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Ad esempio, il comando seguente esporta i dati della chat persistente dal database di chat persistente che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip. Dato che il parametro level non è stato specificato, il comando eseguirà l'esportazione completa delle informazioni sulla chat persistente:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Ripristinare i database

Il modo in cui ripristinare i dati della chat persistente dipende dal metodo usato per eseguire il backup. Se sono state usate le procedure di backup di SQL Server, è necessario usare le procedure di ripristino di SQL Server. Se è stato usato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati della chat persistente, è necessario usare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
