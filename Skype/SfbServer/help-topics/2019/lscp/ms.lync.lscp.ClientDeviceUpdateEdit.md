---
title: Modifica della configurazione del Registro dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile aggiungere una configurazione del log del dispositivo alla pagina Modifica impostazioni log che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
ms.openlocfilehash: 6c448b886b14397f65d7ebeb5a52b90a38c7b320
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691541"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="3d558-104">Configurazione dei log del dispositivo: modifica</span><span class="sxs-lookup"><span data-stu-id="3d558-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="3d558-105">È possibile aggiungere una configurazione del log del dispositivo alla pagina **Modifica impostazioni log** che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo in cui un file di log viene mantenuto prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="3d558-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="3d558-106">È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d558-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3d558-p103">L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="3d558-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3d558-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="3d558-109">Tasks you can perform</span></span>

<span data-ttu-id="3d558-110">Nella pagina **Modifica impostazioni log** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d558-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="3d558-111">Aggiungere una configurazione del log dei dispositivi a livello globale o per un determinato sito.</span><span class="sxs-lookup"><span data-stu-id="3d558-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="3d558-112">Modificare le opzioni per una configurazione del log del dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="3d558-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3d558-113">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="3d558-113">UI Reference</span></span>

<span data-ttu-id="3d558-114">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="3d558-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="3d558-115">**Ambito** Identifica l'ambito (globale o sito) della configurazione del log dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3d558-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="3d558-116">**Nome** È possibile aggiungere o modificare il nome della configurazione del log dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3d558-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="3d558-117">**Dimensione massima del file (byte)** Puoi specificare le dimensioni massime che un file di log può diventare prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="3d558-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="3d558-118">Il valore predefinito è 1.024.000 byte (1 MB).</span><span class="sxs-lookup"><span data-stu-id="3d558-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="3d558-119">**Dimensioni massime della cache (byte)** È possibile specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di log prima che la cache sia deselezionata e i dati vengano scritti in un file di log.</span><span class="sxs-lookup"><span data-stu-id="3d558-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="3d558-120">Il valore predefinito è 512.000 byte (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="3d558-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="3d558-121">**Minuti per svuotare la cache (1-60)** È possibile specificare la frequenza con cui le informazioni memorizzate nella cache dei file di log vengono scritte nel file di log effettivo.</span><span class="sxs-lookup"><span data-stu-id="3d558-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="3d558-122">Dopo aver registrato i dati, la cache viene deselezionata.</span><span class="sxs-lookup"><span data-stu-id="3d558-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="3d558-123">Il valore predefinito è cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="3d558-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="3d558-124">**Giorni per conservare i file di log (1-365)** È possibile specificare il numero di giorni in cui i file di log vengono mantenuti prima che vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="3d558-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="3d558-125">Il valore predefinito è 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="3d558-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d558-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d558-126">See also</span></span>

[<span data-ttu-id="3d558-127">Configurazione dei log del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3d558-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
