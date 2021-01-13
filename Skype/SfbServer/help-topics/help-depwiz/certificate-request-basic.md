---
title: Richiesta di certificato (Basic)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La pagina Impostazioni nome e sicurezza fornisce una casella di testo per definire un nome descrittivo, un elenco a discesa per la lunghezza in bit della coppia di chiavi private e pubbliche e una casella di controllo che consente di contrassegnare la chiave privata del certificato come esportabile.
ms.openlocfilehash: f0d0339a483056276d400654f897b898b002cf03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805346"
---
# <a name="certificate-request-basic"></a>Richiesta di certificato (Basic)
 
La pagina **Impostazioni nome e sicurezza** fornisce una casella di testo per definire un **nome descrittivo**, un elenco a discesa per la **lunghezza in bit** della coppia di chiavi private e pubbliche e una casella di controllo che consente di **contrassegnare la chiave privata del certificato come esportabile**.
  
Il nome descrittivo di un certificato rappresenta un nome facilmente riconoscibile che consente alla persona che visualizza il certificato di identificarlo più facilmente.
  
La lunghezza in bit della coppia chiave privata e chiave pubblica può essere impostata su 1024, 2048 o 4096.
  
Selezionando la casella di controllo **Contrassegna come esportabile la chiave privata del certificato** , il certificato e la chiave privata devono essere esportati e spostati in un altro computer o server. L'unica volta che è necessario è quando si crea un pool di server perimetrali per il servizio di autenticazione di MRAS (Media Relay Authentication Service).
  
> [!CAUTION]
> Per garantire la sicurezza del certificato e della coppia di chiavi, è consigliabile selezionare l'opzione Contrassegna come esportabile la chiave privata del certificato solo se è assolutamente necessario. 
  

