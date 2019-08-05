---
title: Aggiungere l'FQDN del pool di applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:'
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195503"
---
# <a name="add-trusted-application-pool-fqdn"></a>Aggiungere l'FQDN del pool di applicazioni attendibili
 
Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:
  
Un nome di dominio completo del server o del pool di server che ospitano le applicazioni attendibili.
  
Selezionare **più pool di computer** se si sta distribuendo un pool di server per le applicazioni attendibili da bilanciamento del carico e disponibilità elevata oppure selezionare **Single computer pool** se non è necessario il bilanciamento del carico o l'elevata disponibilità.
  
> [!IMPORTANT]
> Un singolo server delle applicazioni attendibili non può essere convertito in un pool di server in un secondo momento. Se si ritiene che potrebbe essere necessario un pool in futuro, è possibile distribuire un pool di più server contenente un singolo computer e aggiungere i server quando necessario. 
  
Per informazioni dettagliate sui pool di applicazioni attendibili, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

