---
title: Processo di migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a31a127ef3a37ed366117247dd68c192d19e691
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo di migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

La procedura di migrazione consigliata e supportata per Lync Server 2013 è la migrazione affiancata. In questo argomento vengono illustrati i motivi per cui utilizzare questo tipo di migrazione e fornite informazioni sul test di coesistenza.

<div>

## <a name="side-by-side-migration"></a>Migrazione affiancata

In quasi ogni migrazione è consigliabile utilizzare il percorso di migrazione side-by-side. In una migrazione affiancata, è necessario distribuire un nuovo server con Lync Server 2013 accanto a un server corrispondente che esegue Lync Server 2010 e quindi trasferire le operazioni nel nuovo server. Se è necessario eseguire il rollback a Lync Server 2010, è solo necessario spostare di nuovo le operazioni nei server originali. Tenere presente che in questa situazione tutte le nuove riunioni pianificate con client aggiornati non funzioneranno e sarà necessario eseguire anche il downgrade dei client.

</div>

<div>

## <a name="coexistence-testing"></a>Testing della coesistenza

Dopo aver distribuito Lync Server 2013 in parallelo con Lync Server 2010, la distribuzione rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Lync Server 2010. In questo stato è importante testare e verificare che i servizi siano avviati, che sia possibile amministrare ogni sito e che i client siano in grado di comunicare con gli utenti correnti e legacy. Prima di eseguire la migrazione di tutti gli utenti, è estremamente importante conoscere lo stato di ciascuna distribuzione e verificare che ogni distribuzione sia operativa e funzioni correttamente. In genere, la fase di test di coesistenza esiste durante il testing pilota di Lync Server 2013. Gli utenti legacy vengono spostati in Lync Server 2013 per un determinato periodo di tempo per garantire che la compatibilità delle applicazioni e le caratteristiche e le funzionalità funzionino correttamente. Dopo il testing pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool legacy e le applicazioni di Lync Server 2010 vengono ritirati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

