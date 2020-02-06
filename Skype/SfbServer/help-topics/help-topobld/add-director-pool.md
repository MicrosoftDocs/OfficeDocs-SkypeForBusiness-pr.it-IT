---
title: Aggiungere pool di Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Per definire il nome di dominio completo del pool di Director, selezionare un pool di computer multipli costituito da due o più direttori in un pool con bilanciamento del carico o da un singolo pool di computer. Devi anche digitare il nome di dominio completo (FQDN) che verrà usato per la connessione al pool di Director o l'FQDN del singolo amministratore. Per un pool di computer Director, questa sarebbe la voce Domain Name System (DNS) per l'IP virtuale di un dispositivo di bilanciamento del carico hardware o della voce DNS condivisa per il bilanciamento del carico DNS.
ms.openlocfilehash: 1a419c6a27118cbdf7ffe841a39b9b60e6e84577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821188"
---
# <a name="add-director-pool"></a>Aggiungere pool di Director
 
Per **definire il nome di dominio completo del pool di Director**, selezionare un **pool di computer multipli** costituito da due o più direttori in un pool con bilanciamento del carico o da un **singolo pool di computer**. Devi anche digitare il nome di dominio completo (FQDN) che verrà usato per la connessione al pool di Director o l'FQDN del singolo amministratore. Per un pool di computer Director, questa sarebbe la voce Domain Name System (DNS) per l'IP virtuale di un dispositivo di bilanciamento del carico hardware o della voce DNS condivisa per il bilanciamento del carico DNS.
  
> [!TIP]
> Se si prevede di implementare un pool di Director in futuro, selezionare **più pool di computer**. Anche se un pool è definito come due o più computer con bilanciamento del carico, è possibile creare un singolo pool di computer e creare un nome di dominio completo del pool per il singolo computer. Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di Director tramite la distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool ai relativi equilibri di bilanciamento del carico per il pool, per il bilanciamento del carico DNS (Domain Name System) o per i dispositivi di bilanciamento del carico hardware. In molti casi è necessario disporre di entrambi i sistemi di bilanciamento del carico. Assicurarsi di aggiungere il nuovo server membro a entrambi. 
  

