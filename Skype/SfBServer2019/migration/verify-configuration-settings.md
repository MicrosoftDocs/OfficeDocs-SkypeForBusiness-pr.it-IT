---
title: Verificare le impostazioni di configurazione
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
description: È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet Get-CsManagementStoreReplicationStatus di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer aggiunto al dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore.msi).
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752148"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="56d6f-103">Verificare le impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="56d6f-103">Verify configuration settings</span></span>

<span data-ttu-id="56d6f-104">È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Skype for business server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer aggiunto al dominio in cui è installato Skype for business server 2019 Core Components (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="56d6f-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="56d6f-105">I risultati iniziali possono indicare lo stato "False" anziché "True" per la replica.</span><span class="sxs-lookup"><span data-stu-id="56d6f-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="56d6f-106">In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e attendere il completamento della replica prima di eseguire di nuovo **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="56d6f-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

