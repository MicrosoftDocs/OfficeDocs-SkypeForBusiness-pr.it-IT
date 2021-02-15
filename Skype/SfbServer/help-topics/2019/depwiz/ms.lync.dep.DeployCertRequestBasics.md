---
title: Richiesta di certificato (Basic)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina Impostazioni nome e sicurezza sono disponibili una casella di testo per definire un nome descrittivo, un elenco a discesa per la lunghezza in bit della coppia di chiavi privata e pubblica e una casella di controllo che consente di contrassegnare la chiave privata del certificato come esportabile.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830416"
---
# <a name="certificate-request-basic"></a>Richiesta di certificato (Basic)
 
Nella  pagina Impostazioni nome e sicurezza è disponibile una casella di testo per definire un nome descrittivo, un elenco a discesa per la lunghezza in **bit** della coppia di chiavi privata e pubblica e una casella di controllo che consente di contrassegnare la chiave privata del certificato come esportabile. 
  
Il nome descrittivo di un certificato rappresenta un nome facilmente riconoscibile che consente alla persona che visualizza il certificato di identificarlo più facilmente.
  
La lunghezza in bit della coppia chiave privata e chiave pubblica può essere impostata su 1024, 2048 o 4096.
  
Se si seleziona la casella **di** controllo Contrassegna la chiave privata del certificato come esportabile, il certificato e la chiave privata possono essere esportati e spostati in un altro computer o server. Questa operazione è necessaria solo quando si crea un pool di server perimetrali per il servizio mras (Media Relay Authentication Service).
  
> [!CAUTION]
> Per mantenere la sicurezza del certificato e della coppia di chiavi, è necessario selezionare l'opzione Contrassegna la chiave privata del certificato come esportabile solo se è assolutamente necessario. 
  

