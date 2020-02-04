---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo di migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

La procedura di migrazione consigliata e supportata per Lync Server 2013 è la procedura di migrazione affiancata. Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sulla coesistenza.

<div>

## <a name="side-by-side-migration"></a>Migrazione affiancata

In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato. In una migrazione affiancata si distribuisce un nuovo server con Lync Server 2013 accanto a un server corrispondente che sta eseguendo Office Communications Server 2007 R2 e quindi si trasferiscono le operazioni nel nuovo server. Se è necessario eseguire il rollback a Office Communications Server 2007 R2, è necessario spostare di nuovo solo le operazioni nei server originali. Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.

</div>

<div>

## <a name="coexistence-testing"></a>Test di coesistenza

Dopo aver distribuito Lync Server 2013 in parallelo a Office Communications Server 2007 R2, la topologia rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Office Communications Server 2007 R2. In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy. Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente. In genere, la fase di test di coesistenza esiste durante il test pilota di Lync Server 2013. Gli utenti legacy vengono spostati in Lync Server 2013 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente. Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool e le applicazioni legacy di Office Communications Server 2007 R2 vengono ritirati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

