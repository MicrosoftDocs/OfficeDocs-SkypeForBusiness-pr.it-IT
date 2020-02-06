---
title: Aggiungere pool A/V MCU
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Tutti i server front-end Enterprise Edition di un sito centrale che non dispongono di un servizio A/V Conferencing collocato possono usare lo stesso pool di servizi di conferenza A/V autonomo. Per ogni pool di servizi di conferenza A/V, è necessario specificare un nome di dominio completo (FQDN) per il pool e se avrà un solo server A/V Conferencing o più server di conferenza A/V con bilanciamento del carico.
ms.openlocfilehash: b2fd57f0a6c9f39638f62a9bae7c9ed29a73a779
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794835"
---
# <a name="add-av-mcu-pool"></a>Aggiungere pool A/V MCU
 
Tutti i server front-end Enterprise Edition di un sito centrale che non dispongono di un servizio A/V Conferencing collocato possono usare lo stesso pool di servizi di conferenza A/V autonomo. Per ogni pool di servizi di conferenza A/V, è necessario specificare un nome di dominio completo (FQDN) per il pool e se avrà un solo server A/V Conferencing o più server di conferenza A/V con bilanciamento del carico.
  
> [!IMPORTANT]
> Non è possibile convertire un pool a server singolo in un pool a più server. Se in seguito si decide che l'organizzazione ha bisogno di un pool a più server, è necessario eliminare il pool a server singolo e quindi aggiungere il pool a più server. 
  
> [!TIP]
> Se si prevede di implementare un pool di servizi di conferenza a/V in futuro, selezionare **più pool di computer**. Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di un singolo computer e un FQDN del pool per questo computer. Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario di nuovo generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di servizi di conferenza A/V tramite la distribuzione guidata di Skype for Business Server. I pool di servizi a/V Conferencing Server sono univoci in quanto non necessitano di servizi di bilanciamento del carico per creare un pool. I pool di servizi di conferenza A/V si equilibrano internamente e non necessitano di hardware aggiuntivo. 
  

