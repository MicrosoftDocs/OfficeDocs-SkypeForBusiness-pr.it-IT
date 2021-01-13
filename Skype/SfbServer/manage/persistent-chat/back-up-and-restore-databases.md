---
title: Eseguire il backup e il ripristino dei database di chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Riepilogo: informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826376"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Eseguire il backup e il ripristino dei database di chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente richiede il software di database di SQL Server per archiviare i dati delle chat room, ad esempio la cronologia e il contenuto, la configurazione, il provisioning degli utenti e altri metadati rilevanti. Inoltre, se l'organizzazione dispone di regole che richiedono l'archiviazione di attività di chat persistente e il servizio di conformità facoltativo è abilitato, il software di database di SQL Server viene utilizzato per archiviare i dati di conformità, inclusi il contenuto e gli eventi relativi alle chat, ad esempio l'aggiunta e la mancata esecuzione di sale. Il contenuto della chat room è archiviato nel database di Persistent Chat (MGC). I dati di conformità sono archiviati nel database di conformità (mgccomp). Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup. 
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

## <a name="back-up-the-databases"></a>Eseguire il backup dei database

Sono disponibili due modi per eseguire il backup dei dati di Persistent Chat. 
  
- Backup di SQL Server
    
- Il cmdlet **Export-CsPersistentChatData** , che esporta i dati della chat persistente come file
    
I dati creati utilizzando il backup di SQL Server richiedono significativamente più spazio su disco, possibilmente 20 volte di più, rispetto a quello creato dal cmdlet **Export-CsPersistentChatData** , ma il backup di SQL Server è probabilmente una procedura con cui si ha familiarità.
  
Se si desidera utilizzare le procedure di backup di SQL Server, vedere la documentazione SQL per ulteriori informazioni. 
  
Se si desidera utilizzare il cmdlet **Export-CsPersistentChatData** , è possibile specificare il comando come indicato di seguito:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Ad esempio, il comando seguente esporta i dati della chat persistente dal database di Persistent Chat che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip. Poiché il parametro level non è stato specificato, il comando eseguirà un'esportazione completa delle informazioni di Persistent Chat:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Ripristinare i database

Il modo in cui si ripristinano i dati della chat persistente dipende dal metodo utilizzato per eseguire il backup. Se sono state utilizzate le procedure di backup di SQL Server, è necessario utilizzare le procedure di ripristino di SQL Server. Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
