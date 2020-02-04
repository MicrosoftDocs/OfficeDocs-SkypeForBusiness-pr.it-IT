---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53021b37baca7a859c79a6c47bfbf3d587a3466d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processo di migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

La procedura di migrazione consigliata e supportata per Lync Server 2013 è la migrazione affiancata. Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.

<div>

## <a name="side-by-side-migration"></a>Migrazione affiancata

In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato. In una migrazione affiancata si distribuisce un nuovo server con Lync Server 2013 accanto a un server corrispondente che sta eseguendo Lync Server 2010 e quindi trasferisce le operazioni nel nuovo server. Se è necessario eseguire il rollback a Lync Server 2010, è sufficiente spostare di nuovo le operazioni nei server originali. Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.

</div>

<div>

## <a name="coexistence-testing"></a>Test di coesistenza

Dopo aver distribuito Lync Server 2013 in parallelo a Lync Server 2010, la distribuzione rappresenta uno stato di verifica della coesistenza di Lync Server 2013 e Lync Server 2010. In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy. Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente. In genere, la fase di test di coesistenza esiste durante il test pilota di Lync Server 2013. Gli utenti legacy vengono spostati in Lync Server 2013 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente. Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Lync Server 2013 e i pool e le applicazioni legacy di Lync Server 2010 vengono ritirati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

