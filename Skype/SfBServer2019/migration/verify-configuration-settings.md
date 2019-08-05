---
title: Verificare le impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet Get-CsManagementStoreReplicationStatus di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer collegato al dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore. msi).
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195848"
---
# <a name="verify-configuration-settings"></a>Verificare le impostazioni di configurazione

È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Skype for Business Server 2019 nel computer interno in cui si trova l'archivio di gestione centrale oppure in qualsiasi computer collegato a un dominio in cui è installato Skype for Business Server 2019 Core Components (OcsCore. msi). 
  
I risultati iniziali possono indicare lo stato "false" invece di "true" per la replica. In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e consentire il completamento della replica prima di eseguire nuovamente **Get-CsManagementStoreReplicationStatus** . 
  

