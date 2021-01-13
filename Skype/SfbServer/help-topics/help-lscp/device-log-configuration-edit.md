---
title: Modifica della configurazione del Registro dispositivi
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Nella pagina di modifica delle impostazioni del log è possibile aggiungere una configurazione del log del dispositivo che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo per cui un file di log viene conservato prima di essere eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
ms.openlocfilehash: 694729b74209715bd87bed0c3bd59d80f31fff59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807316"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="b23f0-104">Configurazione dei log del dispositivo: modifica</span><span class="sxs-lookup"><span data-stu-id="b23f0-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="b23f0-105">Nella pagina di \*\*\*\* modifica delle impostazioni del log è possibile aggiungere una configurazione del log del dispositivo che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo per cui un file di log viene conservato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="b23f0-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="b23f0-106">È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b23f0-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b23f0-p103">L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="b23f0-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="b23f0-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="b23f0-109">Tasks you can perform</span></span>

<span data-ttu-id="b23f0-110">Nella pagina di \*\*\*\* modifica delle impostazioni del log è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b23f0-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="b23f0-111">Aggiungere una configurazione del log del dispositivo a livello globale o per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="b23f0-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="b23f0-112">Modificare le opzioni per una configurazione del log del dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="b23f0-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="b23f0-113">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="b23f0-113">UI Reference</span></span>

<span data-ttu-id="b23f0-114">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="b23f0-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="b23f0-115">**Ambito** Identifica l'ambito (globale o sito) della configurazione del registro dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b23f0-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="b23f0-116">**Nome** È possibile aggiungere o modificare il nome della configurazione del registro dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b23f0-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="b23f0-117">**Dimensioni massime file (byte)** È possibile specificare le dimensioni massime che un file di registro può diventare prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="b23f0-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="b23f0-118">Il valore predefinito è 1.024.000 byte (1 MB).</span><span class="sxs-lookup"><span data-stu-id="b23f0-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="b23f0-119">**Dimensioni massime della cache (byte)** È possibile specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di registro prima che la cache debba essere cancellata e che i dati vengano scritti in un file di registro.</span><span class="sxs-lookup"><span data-stu-id="b23f0-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="b23f0-120">Il valore predefinito è 512.000 byte (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="b23f0-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="b23f0-121">**Minuti per svuotare la cache (1-60)** È possibile specificare la frequenza con cui le informazioni archiviate nella cache dei file di registro vengono scritte nel file di registro effettivo.</span><span class="sxs-lookup"><span data-stu-id="b23f0-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="b23f0-122">Dopo la registrazione dei dati, la cache viene svuotata.</span><span class="sxs-lookup"><span data-stu-id="b23f0-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="b23f0-123">Il valore predefinito è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="b23f0-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="b23f0-124">**Giorni per mantenere i file di registro (1-365)** È possibile specificare il numero di giorni in cui i file di registro vengono mantenuti prima che vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="b23f0-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="b23f0-125">Il valore predefinito è 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="b23f0-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b23f0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b23f0-126">See also</span></span>

[<span data-ttu-id="b23f0-127">Configurazione dei log del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b23f0-127">Device Log Configuration</span></span>](device-log-configuration.md)
