---
title: Aggiungere nome di dominio completo (FQDN) del pool di applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:'
ms.openlocfilehash: bb473aaab771038c0556234d865edcb19eca23f8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697961"
---
# <a name="add-trusted-application-pool-fqdn"></a>Aggiungere nome di dominio completo (FQDN) del pool di applicazioni attendibili
 
Per definire un pool di applicazioni attendibili con il nome di dominio completo (FQDN), specificare quanto segue:
  
Un nome di dominio completo del server o del pool di server che ospitano le applicazioni attendibili.
  
Selezionare **più pool di computer** se si sta distribuendo un pool di server per le applicazioni attendibili da bilanciamento del carico e disponibilità elevata oppure selezionare **Single computer pool** se non è necessario il bilanciamento del carico o l'elevata disponibilità.
  
> [!IMPORTANT]
> Un singolo server delle applicazioni attendibili non può essere convertito in un pool di server in un secondo momento. Se si ritiene che potrebbe essere necessario un pool in futuro, è possibile distribuire un pool di più server contenente un singolo computer e aggiungere i server quando necessario. 
  
Per informazioni dettagliate sui pool di applicazioni attendibili, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

