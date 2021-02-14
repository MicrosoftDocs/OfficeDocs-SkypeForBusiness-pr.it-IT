---
title: Espansione delle impostazioni generali del server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: "In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l'archiviazione facendo clic con il pulsante destro del mouse sul server che esegue l'archiviazione nell'albero della console e scegliendo Azione sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro Azioni e quindi scegliendo Modifica proprietà e modificando una delle opzioni seguenti:"
ms.openlocfilehash: 841343a54ac3681659614a8ab89c02990290d9d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800746"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="8ce1e-103">Espansione delle impostazioni generali del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8ce1e-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="8ce1e-104">In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l'archiviazione facendo clic con il pulsante destro del mouse  sul server che esegue l'archiviazione nell'albero della console e scegliendo Azione sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro Azioni e quindi scegliendo Modifica proprietà e modificando una delle opzioni seguenti: </span><span class="sxs-lookup"><span data-stu-id="8ce1e-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="8ce1e-105">**FQDN**, per modificare il nome di dominio completo (FQDN) del server che si desidera distribuire come server che esegue il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="8ce1e-p101">**Archivio SQL**, per modificare l'istanza di SQL Server da utilizzare per il database SQL Server di archiviazione. Se si modifica il database SQL Server di un server che esegue il server di archiviazione, sarà necessario riavviare il server che esegue il server di archiviazione per assicurarsi che le modifiche vengano applicate.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="8ce1e-p102">**Condivisione file**, per cambiare la cartella da utilizzare per l'archivio file di archiviazione. Se si cambia la condivisione file di un server di archiviazione, sarà necessario riavviare il server di archiviazione perché la modifica abbia effetto. Sarà inoltre necessario spostare i file di conferenza precedenti nella nuova cartella della condivisione file per evitare perdite di tali file archiviati.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8ce1e-111">Per modificare i pool associati a un server che esegue il server di archiviazione, selezionare l'opzione **Modifica proprietà** per il singolo nodo di pool Front End o per il nodo Survivable Branch Appliance attualmente associato al server che esegue il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ce1e-112">Il nodo di archiviazione include un server che esegue il server di archiviazione, se tale server è stato aggiunto in precedenza nella topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-112">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder.</span></span> <span data-ttu-id="8ce1e-113">È possibile modificare le proprietà di qualsiasi server che esegue il server di archiviazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-113">You can edit properties for any server running Archiving in the list.</span></span> <span data-ttu-id="8ce1e-114">Tuttavia, la messaggistica istantanea o le conferenze Web (messaggistica) non possono essere archiviate finché non si configura anche il servizio per il server che esegue l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ce1e-114">However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

