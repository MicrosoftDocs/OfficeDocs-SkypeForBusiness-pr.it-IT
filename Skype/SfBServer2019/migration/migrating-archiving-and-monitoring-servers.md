---
title: Migrazione di server di archiviazione e Monitoring Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front end. Tuttavia, se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752668"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="7f49b-104">Migrazione di server di archiviazione e Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="7f49b-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="7f49b-105">Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente legacy, è possibile distribuire questi server nell'ambiente Skype for Business Server 2019 dopo aver eseguito la migrazione dei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="7f49b-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="7f49b-106">Tuttavia, se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Skype for Business Server 2019 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="7f49b-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="7f49b-107">Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f49b-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="7f49b-108">I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f49b-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="7f49b-109">I dati di cui è stato eseguito il backup prima della rimozione dell'ambiente legacy saranno la cronologia delle attività nell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="7f49b-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="7f49b-110">La versione legacy del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front end legacy.</span><span class="sxs-lookup"><span data-stu-id="7f49b-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="7f49b-111">In Skype for Business Server 2019, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f49b-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="7f49b-112">Durante il periodo di coesistenza tra le distribuzioni legacy e Skype for Business Server 2019, la versione legacy del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool legacy.</span><span class="sxs-lookup"><span data-stu-id="7f49b-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="7f49b-113">Archiviazione e monitoraggio in Skype for Business Server 2019 raccogliere dati per gli utenti ospitati nei pool Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f49b-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f49b-114">Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Skype for Business Server 2019, la versione legacy del server di archiviazione continua a raccogliere dati per gli utenti ospitati in pool legacy e l'archiviazione in Skype for Business Server 2019 raccoglie i dati per gli utenti ospitati nei pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f49b-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="7f49b-115">Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme all'archiviazione e al monitoraggio in Skype for Business Server 2019, consultare il fornitore su quando e come integrare la soluzione di terze parti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f49b-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

