---
title: Aggiungere nome di dominio completo (FQDN) del pool di applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:'
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787736"
---
# <a name="add-trusted-application-pool-fqdn"></a>Aggiungere nome di dominio completo (FQDN) del pool di applicazioni attendibili
 
Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:
  
Un nome di dominio completo del server o del pool di server che ospitano le applicazioni attendibili.
  
Selezionare **più pool di computer** se si sta distribuendo un pool di server per le applicazioni attendibili da bilanciamento del carico e disponibilità elevata oppure selezionare **Single computer pool** se non è necessario il bilanciamento del carico o l'elevata disponibilità.
  
> [!IMPORTANT]
> Un singolo server delle applicazioni attendibili non può essere convertito in un pool di server in un secondo momento. Se si ritiene che potrebbe essere necessario un pool in futuro, è possibile distribuire un pool di più server contenente un singolo computer e aggiungere i server quando necessario. 
  
Per informazioni dettagliate sui pool di applicazioni attendibili, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

