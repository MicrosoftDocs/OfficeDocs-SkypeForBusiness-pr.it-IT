---
title: Rimuovere i server di archiviazione e monitoraggio legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se la distribuzione legacy contiene un server di archiviazione o un server di monitoraggio, dopo la migrazione a Skype for Business Server 2019, questi server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da qualsiasi pool legacy rimanente. È possibile rimuovere il server di archiviazione o il server di monitoraggio in qualsiasi sequenza. Il requisito fondamentale è che tutti gli utenti siano stati rimossi da qualsiasi pool legacy rimanente.
ms.openlocfilehash: 06d6287438e4b470017b00601b1e2ab472bea9b6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244450"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Rimuovere i server di archiviazione e monitoraggio legacy

Se la distribuzione legacy contiene un server di archiviazione o un server di monitoraggio, dopo la migrazione a Skype for Business Server 2019, questi server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da eventuali pool legacy rimanenti. È possibile rimuovere il server di archiviazione o il server di monitoraggio in qualsiasi sequenza. Il requisito fondamentale è che tutti gli utenti siano stati rimossi da qualsiasi pool legacy rimanente.
  
È possibile trasferire utenti in Skype for Business Server 2019 seguendo le procedure descritte nella [fase 4: trasferire gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).
  
Dopo aver confermato che tutti gli utenti sono stati rimossi da tutti i pool rimanenti, decommision il server e Rimuovi ruoli. Un esempio datato, ma pertinente è "disinstallazione di Microsoft Lync Server e rimozione dei ruoli del server", a [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)cui è possibile scaricare.
  

