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
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="75cb3-103">Eseguire il backup e il ripristino dei database di chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="75cb3-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75cb3-104">**Riepilogo:** Informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75cb3-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75cb3-105">Il server Chat persistente richiede il software di database di SQL Server per archiviare i dati delle chat room, ad esempio la cronologia e il contenuto, la configurazione, il provisioning degli utenti e altri metadati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="75cb3-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="75cb3-106">Inoltre, se l'organizzazione dispone di regole che richiedono l'archiviazione di attività di chat persistente e il servizio di conformità facoltativo è abilitato, il software di database di SQL Server viene utilizzato per archiviare i dati di conformità, inclusi il contenuto e gli eventi relativi alle chat, ad esempio l'aggiunta e la mancata esecuzione di sale.</span><span class="sxs-lookup"><span data-stu-id="75cb3-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="75cb3-107">Il contenuto della chat room è archiviato nel database di Persistent Chat (MGC).</span><span class="sxs-lookup"><span data-stu-id="75cb3-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="75cb3-108">I dati di conformità sono archiviati nel database di conformità (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="75cb3-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="75cb3-109">Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup.</span><span class="sxs-lookup"><span data-stu-id="75cb3-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75cb3-110">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="75cb3-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="75cb3-111">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="75cb3-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="75cb3-112">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="75cb3-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="75cb3-113">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75cb3-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="75cb3-114">Eseguire il backup dei database</span><span class="sxs-lookup"><span data-stu-id="75cb3-114">Back up the databases</span></span>

<span data-ttu-id="75cb3-115">Sono disponibili due modi per eseguire il backup dei dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="75cb3-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="75cb3-116">Backup di SQL Server</span><span class="sxs-lookup"><span data-stu-id="75cb3-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="75cb3-117">Il cmdlet **Export-CsPersistentChatData** , che esporta i dati della chat persistente come file</span><span class="sxs-lookup"><span data-stu-id="75cb3-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="75cb3-118">I dati creati utilizzando il backup di SQL Server richiedono significativamente più spazio su disco, possibilmente 20 volte di più, rispetto a quello creato dal cmdlet **Export-CsPersistentChatData** , ma il backup di SQL Server è probabilmente una procedura con cui si ha familiarità.</span><span class="sxs-lookup"><span data-stu-id="75cb3-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="75cb3-119">Se si desidera utilizzare le procedure di backup di SQL Server, vedere la documentazione SQL per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="75cb3-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="75cb3-120">Se si desidera utilizzare il cmdlet **Export-CsPersistentChatData** , è possibile specificare il comando come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="75cb3-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="75cb3-121">o</span><span class="sxs-lookup"><span data-stu-id="75cb3-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="75cb3-122">Ad esempio, il comando seguente esporta i dati della chat persistente dal database di Persistent Chat che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="75cb3-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="75cb3-123">Poiché il parametro level non è stato specificato, il comando eseguirà un'esportazione completa delle informazioni di Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="75cb3-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="75cb3-124">Ripristinare i database</span><span class="sxs-lookup"><span data-stu-id="75cb3-124">Restore the databases</span></span>

<span data-ttu-id="75cb3-125">Il modo in cui si ripristinano i dati della chat persistente dipende dal metodo utilizzato per eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="75cb3-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="75cb3-126">Se sono state utilizzate le procedure di backup di SQL Server, è necessario utilizzare le procedure di ripristino di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75cb3-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="75cb3-127">Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:</span><span class="sxs-lookup"><span data-stu-id="75cb3-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="75cb3-128">o</span><span class="sxs-lookup"><span data-stu-id="75cb3-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
