---
title: Processo di migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata. In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e fornite informazioni sul test di coesistenza.
ms.openlocfilehash: 4ca0e8d1362c05e87c4ec347115f7e45457c55d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613391"
---
# <a name="migration-process"></a>Processo di migrazione

La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata. In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e fornite informazioni sul test di coesistenza.
  
## <a name="side-by-side-migration"></a>Migrazione affiancata

In quasi ogni migrazione è consigliabile utilizzare il percorso di migrazione side-by-side. In una migrazione affiancata, si distribuisce un nuovo server con Skype for Business Server 2019 insieme a un server corrispondente che esegue una versione precedente e quindi si trasferiscono le operazioni nel nuovo server. Se diventa necessario eseguire il rollback alla versione precedente, è necessario solo spostare le operazioni nei server originali. Tenere presente che in questa situazione tutte le nuove riunioni pianificate con client aggiornati non funzioneranno e sarà necessario eseguire anche il downgrade dei client.
  
## <a name="coexistence-testing"></a>Testing della coesistenza

Dopo aver distribuito Skype for Business Server 2019 in parallelo alla versione precedente, la distribuzione rappresenta uno stato di test di coesistenza di Skype for Business Server 2019 e della versione precedente. In questo stato è importante testare e verificare che i servizi siano avviati, che sia possibile amministrare ogni sito e che i client siano in grado di comunicare con gli utenti correnti e legacy. Prima di eseguire la migrazione di tutti gli utenti, è estremamente importante conoscere lo stato di ciascuna distribuzione e verificare che ogni distribuzione sia operativa e funzioni correttamente. In genere, la fase di test di coesistenza esiste durante i test pilota di Skype for Business Server 2019. Gli utenti legacy vengono spostati a Skype for Business Server 2019 per un periodo di tempo per garantire che la compatibilità delle applicazioni e le funzionalità e le funzionino correttamente. Dopo i test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Skype for Business Server 2019 e i pool legacy e le applicazioni della versione precedente vengono ritirati.
  
