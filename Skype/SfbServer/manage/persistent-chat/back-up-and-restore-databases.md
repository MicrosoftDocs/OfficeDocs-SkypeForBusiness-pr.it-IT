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
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Riepilogo: informazioni su come eseguire il backup e il ripristino di database del server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: a8c407c35b9d864889c26cbea7296dbed86516fa
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991971"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="1ef5c-103">Backup e ripristino dei database di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="1ef5c-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1ef5c-104">**Riepilogo:** Informazioni su come eseguire il backup e il ripristino di database del server di chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1ef5c-105">Il server di chat persistente richiede il software di database di SQL Server per archiviare i dati delle chat room, ad esempio cronologia e contenuto, configurazione, provisioning degli utenti e altri metadati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="1ef5c-106">Inoltre, se l'organizzazione ha regole che richiedono l'archiviazione di attività della chat persistente e il servizio di conformità facoltativo è abilitato, il software di database di SQL Server viene usato per archiviare i dati di conformità, inclusi il contenuto della chat e gli eventi, ad esempio entrare e uscire dalle sale.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="1ef5c-107">Il contenuto della chat room è archiviato nel database della chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="1ef5c-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="1ef5c-108">I dati di conformità vengono archiviati nel database di conformità (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="1ef5c-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="1ef5c-109">Si tratta di dati business-critical di cui eseguire il backup regolarmente.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ef5c-110">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1ef5c-111">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="1ef5c-112">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="1ef5c-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1ef5c-113">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="1ef5c-114">Eseguire il backup dei database</span><span class="sxs-lookup"><span data-stu-id="1ef5c-114">Back up the databases</span></span>

<span data-ttu-id="1ef5c-115">Esistono due modi per eseguire il backup dei dati della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="1ef5c-116">Backup di SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ef5c-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="1ef5c-117">Cmdlet **Export-CsPersistentChatData** , che esporta i dati della chat persistente come file</span><span class="sxs-lookup"><span data-stu-id="1ef5c-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="1ef5c-118">I dati creati con SQL Server backup richiedono molto più spazio su disco, possibilmente 20 volte di più, rispetto a quelli creati dal cmdlet **Export-CsPersistentChatData** , ma è probabile che SQL Server backup sia una procedura con cui si ha familiarità.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="1ef5c-119">Se si vogliono usare le procedure di backup di SQL Server, vedere la documentazione di SQL per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="1ef5c-120">Se si vuole usare il cmdlet **Export-CsPersistentChatData** , è possibile specificare il comando come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1ef5c-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="1ef5c-121">o</span><span class="sxs-lookup"><span data-stu-id="1ef5c-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="1ef5c-122">Ad esempio, il comando seguente esporta i dati della chat persistente dal database di chat persistente che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="1ef5c-123">Dato che il parametro level non è stato specificato, il comando eseguirà l'esportazione completa delle informazioni sulla chat persistente:</span><span class="sxs-lookup"><span data-stu-id="1ef5c-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="1ef5c-124">Ripristinare i database</span><span class="sxs-lookup"><span data-stu-id="1ef5c-124">Restore the databases</span></span>

<span data-ttu-id="1ef5c-125">Il modo in cui ripristinare i dati della chat persistente dipende dal metodo usato per eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="1ef5c-126">Se sono state usate le procedure di backup di SQL Server, è necessario usare le procedure di ripristino di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ef5c-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="1ef5c-127">Se è stato usato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati della chat persistente, è necessario usare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:</span><span class="sxs-lookup"><span data-stu-id="1ef5c-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="1ef5c-128">o</span><span class="sxs-lookup"><span data-stu-id="1ef5c-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
