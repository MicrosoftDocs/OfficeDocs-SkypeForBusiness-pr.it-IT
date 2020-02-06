---
title: Verificare impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet Get-CsManagementStoreReplicationStatus di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer collegato al dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore. msi).
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812754"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="8273a-103">Verificare impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="8273a-103">Verify configuration settings</span></span>

<span data-ttu-id="8273a-104">È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Skype for business server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer collegato al dominio in cui è installato Skype for business server 2019 Core Components (OCSCore. msi).</span><span class="sxs-lookup"><span data-stu-id="8273a-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="8273a-105">I risultati iniziali possono indicare lo stato "false" invece di "true" per la replica.</span><span class="sxs-lookup"><span data-stu-id="8273a-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="8273a-106">In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e consentire il completamento della replica prima di eseguire nuovamente **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="8273a-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

