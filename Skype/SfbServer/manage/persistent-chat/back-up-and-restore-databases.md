---
title: Eseguire il backup e il ripristino dei database di Persistent Chat in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Riepilogo: informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.'
---

# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Eseguire il backup e il ripristino dei database di Persistent Chat in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente richiede SQL Server software di database per archiviare i dati delle chat room, ad esempio la cronologia e il contenuto, la configurazione, il provisioning degli utenti e altri metadati pertinenti. Inoltre, se l'organizzazione dispone di normative che richiedono l'archiviazione dell'attività di Persistent Chat e il servizio di conformità facoltativo è abilitato, il software di database SQL Server viene utilizzato per archiviare i dati di conformità, inclusi il contenuto e gli eventi della chat, ad esempio l'aggiunta e l'uscita da sale. Il contenuto delle chat room viene archiviato nel database di Persistent Chat (mgc). I dati di conformità vengono archiviati nel database di conformità (mgccomp). Si tratta di dati business-critical di cui eseguire regolarmente il backup. 
  
> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 

## <a name="back-up-the-databases"></a>Eseguire il backup dei database

Esistono due modi per eseguire il backup dei dati di Persistent Chat. 
  
- SQL Server backup
    
- Il cmdlet **Export-CsPersistentChatData** , che esporta i dati di Persistent Chat come file
    
I dati creati utilizzando il backup di SQL Server richiedono molto più spazio su disco, probabilmente 20 volte superiore a quelli creati dal cmdlet **Export-CsPersistentChatData**, ma è probabile che il backup di SQL Server sia una procedura familiare.
  
Se si desidera utilizzare le SQL Server di backup, vedere la documentazione SQL per ulteriori informazioni. 
  
Se si desidera utilizzare il cmdlet **Export-CsPersistentChatData** , è possibile specificare il comando come segue:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

oppure
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Ad esempio, il comando seguente esporta i dati di Persistent Chat dal database di Persistent Chat che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip. Poiché il parametro Level non è stato specificato, il comando esporterà completamente le informazioni di Persistent Chat:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Ripristinare i database

La modalità di ripristino dei dati di Persistent Chat dipende dal metodo utilizzato per il backup. Se sono stati utilizzati SQL Server di backup, è necessario utilizzare le SQL Server di ripristino. Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

oppure
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
