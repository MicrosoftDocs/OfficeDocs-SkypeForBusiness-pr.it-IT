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
description: È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet Get-CsManagementStoreReplicationStatus di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer aggiunto a un dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore.msi).
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335746"
---
# <a name="verify-configuration-settings"></a>Verificare le impostazioni di configurazione

È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer aggiunto al dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore.msi). 
  
I risultati iniziali possono indicare lo stato "False" anziché "True" per la replica. In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e attendere il completamento della replica prima di eseguire di nuovo **Get-CsManagementStoreReplicationStatus**. 
  

