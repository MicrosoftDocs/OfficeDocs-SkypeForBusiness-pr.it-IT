---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata. Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238084"
---
# <a name="migration-process"></a>Processo di migrazione

La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata. Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.
  
## <a name="side-by-side-migration"></a>Migrazione affiancata

In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato. In una migrazione affiancata si distribuisce un nuovo server con Skype for Business Server 2019 accanto a un server corrispondente che sta eseguendo una versione precedente e quindi trasferisce le operazioni nel nuovo server. Se è necessario eseguire il rollback alla versione precedente, è necessario spostare di nuovo solo le operazioni nei server originali. Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.
  
## <a name="coexistence-testing"></a>Test di coesistenza

Dopo aver implementato Skype for Business Server 2019 in parallelo alla versione precedente, la distribuzione rappresenta uno stato di verifica della coesistenza di Skype for Business Server 2019 e la versione precedente. In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy. Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente. In genere, la fase di test di coesistenza esiste durante il test pilota di Skype for Business Server 2019. Gli utenti legacy vengono spostati in Skype for Business Server 2019 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente. Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Skype for Business Server 2019 e i pool e le applicazioni legacy della versione precedente vengono ritirati.
  
