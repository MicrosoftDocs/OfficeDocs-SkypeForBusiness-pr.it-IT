---
title: Aggiungere il pool MCU A/V
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Tutti i Front End Server Enterprise Edition di un sito centrale che non hanno un servizio per conferenze A/V collocato possono utilizzare lo stesso pool A/V Conferencing autonomo. Per ogni pool di questo tipo, è necessario specificare un nome di dominio completo (FQDN) e il fatto che disponga solo di uno oppure di più A/V Conferencing Server con bilanciamento del carico.
ms.openlocfilehash: 689f91bd27e4b3bbb2bd31149f34438bac59db46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810466"
---
# <a name="add-av-mcu-pool"></a>Aggiungere pool MCU A/V
 
Tutti i Front End Server Enterprise Edition di un sito centrale che non hanno un servizio per conferenze A/V collocato possono utilizzare lo stesso pool A/V Conferencing autonomo. Per ogni pool di questo tipo, è necessario specificare un nome di dominio completo (FQDN) e il fatto che disponga solo di uno oppure di più A/V Conferencing Server con bilanciamento del carico.
  
> [!IMPORTANT]
> Non è possibile convertire un pool di server singolo in un pool di più server. Se successivamente si decide che l'organizzazione necessita di un pool di più server, sarà necessario eliminare il pool di server singolo e quindi aggiungere il pool di più server. 
  
> [!TIP]
> Se si prevede di implementare in futuro un pool A/V Conferencing, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con il carico bilanciato, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione. Quando si è pronti ad aggiungere altri computer al pool in un secondo momento, è necessario di nuovo Generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool A/V Conferencing tramite la Distribuzione guidata di Skype for Business Server. I pool di A/V Conferencing Server sono particolari, in quanto per essere creati non richiedono dispositivi di bilanciamento del carico. I pool A/V Conferencing eseguono il bilanciamento del carico internamente e non hanno bisogno di altro hardware. 
  

