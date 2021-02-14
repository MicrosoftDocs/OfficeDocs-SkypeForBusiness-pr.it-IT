---
title: Rimuovere server di archiviazione e di monitoraggio legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se la distribuzione legacy conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Skype for Business Server 2019, questi server possono essere rimossi dall'ambiente legacy purché tutti gli utenti siano stati rimossi dai pool legacy rimanenti. È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza. Il requisito fondamentale è che tutti gli utenti siano stati rimossi dai pool legacy rimanenti.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752168"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Rimuovere server di archiviazione e di monitoraggio legacy

Se la distribuzione legacy conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Skype for Business Server 2019, questi server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi dai pool legacy rimanenti. È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza. Il requisito fondamentale è che tutti gli utenti siano stati rimossi dai pool legacy rimanenti.
  
È possibile spostare gli utenti in Skype for Business Server 2019 seguendo le procedure descritte nella fase [4: spostare](phase-4-move-test-users-to-the-pilot-pool.md)gli utenti di test nel pool pilota.
  
Dopo aver confermato che tutti gli utenti sono stati rimossi dai pool rimanenti, separare il server e rimuovere i ruoli. Un esempio datato, ma pertinente, è "Disinstallazione di Microsoft Lync Server e rimozione dei ruoli del server", che può essere scaricato all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

