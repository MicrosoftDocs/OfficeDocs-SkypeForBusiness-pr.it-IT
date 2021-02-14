---
title: Eseguire il backup e il ripristino dei database di Chat persistente in Skype for Business Server 2015
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
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="2b4f1-103">Eseguire il backup e il ripristino dei database di Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b4f1-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2b4f1-104">**Riepilogo:** Informazioni su come eseguire il backup e il ripristino dei database del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2b4f1-105">Il server Chat persistente richiede SQL Server software di database per archiviare i dati delle chat room, ad esempio cronologia e contenuto, configurazione, provisioning degli utenti e altri metadati pertinenti.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="2b4f1-106">Inoltre, se l'organizzazione ha normative che richiedono l'archiviazione dell'attività di Persistent Chat e il servizio di conformità facoltativo è abilitato, il software di database SQL Server viene utilizzato per archiviare i dati di conformità, inclusi il contenuto e gli eventi della chat, ad esempio la partecipazione e l'uscita da sale.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="2b4f1-107">Il contenuto delle chat room viene archiviato nel database di Persistent Chat (mgc).</span><span class="sxs-lookup"><span data-stu-id="2b4f1-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="2b4f1-108">I dati di conformità vengono archiviati nel database di conformità (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="2b4f1-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="2b4f1-109">Si tratta di dati critici per l'azienda di cui eseguire regolarmente il backup.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2b4f1-110">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b4f1-111">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="2b4f1-112">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="2b4f1-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2b4f1-113">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="2b4f1-114">Eseguire il backup dei database</span><span class="sxs-lookup"><span data-stu-id="2b4f1-114">Back up the databases</span></span>

<span data-ttu-id="2b4f1-115">Esistono due modi per eseguire il backup dei dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="2b4f1-116">SQL Server Backup</span><span class="sxs-lookup"><span data-stu-id="2b4f1-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="2b4f1-117">Il cmdlet **Export-CsPersistentChatData,** che esporta i dati di Persistent Chat come file</span><span class="sxs-lookup"><span data-stu-id="2b4f1-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="2b4f1-118">I dati creati utilizzando il backup SQL Server richiedono una quantità di spazio su disco notevolmente maggiore, probabilmente 20 volte superiore, rispetto a quelli creati dal cmdlet **Export-CsPersistentChatData,** ma è probabile che il backup di SQL Server sia una procedura familiare.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="2b4f1-119">Se si desidera utilizzare le SQL Server di backup, vedere la documentazione SQL per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="2b4f1-120">Se si desidera utilizzare il cmdlet **Export-CsPersistentChatData,** è possibile specificare il comando come segue:</span><span class="sxs-lookup"><span data-stu-id="2b4f1-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="2b4f1-121">oppure</span><span class="sxs-lookup"><span data-stu-id="2b4f1-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="2b4f1-122">Ad esempio, il comando seguente esporta i dati di Persistent Chat dal database di Persistent Chat che si trova nel server atl-sql-001.contoso.com; i dati esportati verranno archiviati nel file C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="2b4f1-123">Poiché il parametro Level non è stato specificato, il comando esporterà completamente le informazioni di Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="2b4f1-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="2b4f1-124">Ripristinare i database</span><span class="sxs-lookup"><span data-stu-id="2b4f1-124">Restore the databases</span></span>

<span data-ttu-id="2b4f1-125">La modalità di ripristino dei dati di Persistent Chat dipende dal metodo utilizzato per il backup.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="2b4f1-126">Se sono stati utilizzati SQL Server di backup, è necessario utilizzare SQL Server di ripristino.</span><span class="sxs-lookup"><span data-stu-id="2b4f1-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="2b4f1-127">Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati:</span><span class="sxs-lookup"><span data-stu-id="2b4f1-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="2b4f1-128">oppure</span><span class="sxs-lookup"><span data-stu-id="2b4f1-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
