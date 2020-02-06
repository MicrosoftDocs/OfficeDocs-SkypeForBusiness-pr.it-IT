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
# <a name="verify-configuration-settings"></a>Verificare impostazioni di configurazione

È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Skype for business server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer collegato al dominio in cui è installato Skype for business server 2019 Core Components (OCSCore. msi). 
  
I risultati iniziali possono indicare lo stato "false" invece di "true" per la replica. In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e consentire il completamento della replica prima di eseguire nuovamente **Get-CsManagementStoreReplicationStatus** . 
  

