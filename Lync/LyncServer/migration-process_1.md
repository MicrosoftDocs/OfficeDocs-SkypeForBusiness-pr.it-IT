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
ms.openlocfilehash: 1cc0620b2de14c56a6886a70cd7b977046828786
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo di migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

La procedura di migrazione consigliata e supportata per Lync Server 2013 è la procedura di migrazione affiancata. In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e vengono inoltre fornite informazioni sulla coesistenza.

<div>

## <a name="side-by-side-migration"></a>Migrazione side-by-side

In quasi ogni migrazione è consigliabile utilizzare il percorso di migrazione side-by-side. In una migrazione affiancata, è necessario distribuire un nuovo server con Lync Server 2013 accanto a un server corrispondente che esegue Office Communications Server 2007 R2 e quindi trasferire le operazioni nel nuovo server. Se è necessario eseguire il rollback a Office Communications Server 2007 R2, è solo necessario spostare di nuovo le operazioni nei server originali. Tenere presente che in questa situazione tutte le nuove riunioni pianificate con client aggiornati non funzioneranno e sarà necessario eseguire anche il downgrade dei client.

</div>

<div>

## <a name="coexistence-testing"></a>Testing della coesistenza

Dopo aver distribuito Lync Server 2013 in parallelo con Office Communications Server 2007 R2, la topologia rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Office Communications Server 2007 R2. In questo stato è importante testare e verificare che i servizi siano avviati, che sia possibile amministrare ogni sito e che i client siano in grado di comunicare con gli utenti correnti e legacy. Prima di eseguire la migrazione di tutti gli utenti, è molto importante identificare lo stato di ogni distribuzione e assicurarsi che ogni distribuzione sia corretta e funzionante. In genere, la fase di test di coesistenza esiste durante il testing pilota di Lync Server 2013. Gli utenti legacy vengono spostati in Lync Server 2013 per un determinato periodo di tempo per garantire che la compatibilità delle applicazioni e le caratteristiche e le funzionalità funzionino correttamente. Dopo il testing pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool legacy e le applicazioni di Office Communications Server 2007 R2 vengono ritirati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

