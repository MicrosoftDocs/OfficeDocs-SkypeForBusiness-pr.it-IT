---
title: Aggiungere l'FQDN del pool di applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Per definire un nome di dominio completo (FQDN) per il pool di applicazioni attendibili, specificare quanto segue:'
ms.openlocfilehash: 94cf0f611d754dc614111add734bf231c92c5a81
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217007"
---
# <a name="add-trusted-application-pool-fqdn"></a>Aggiungere l'FQDN del pool di applicazioni attendibili
 
Per definire un nome di dominio completo (FQDN) per il pool di applicazioni attendibili, specificare quanto segue:
  
Un FQDN del server o del pool di server in cui saranno ospitate le applicazioni attendibili.
  
Selezionare **Pool di più computer** se si sta distribuendo un pool di server per le applicazioni attendibili per il bilanciamento del carico e la disponibilità elevata oppure selezionare **Pool computer singolo** se non si necessita del bilanciamento del carico o della disponibilità elevata.
  
> [!IMPORTANT]
> Un singolo server applicazioni attendibili non può essere convertito in un pool di server in un momento successivo. Se si ritiene di poter avere bisogno di un pool in futuro, è possibile distribuire subito un pool di più server contenente un solo computer e quindi aggiungere ulteriori server quando occorre. 
  
Per informazioni dettagliate sui pool di applicazioni attendibili, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

