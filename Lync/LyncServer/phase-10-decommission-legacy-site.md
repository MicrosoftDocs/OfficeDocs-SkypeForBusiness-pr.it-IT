---
title: 'Fase 10: rimuovere il sito legacy'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a8a2871659747b68e7a0dec6a945c6f987219a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533763"
---
# <a name="phase-10-decommission-legacy-site"></a>Fase 10: rimuovere il sito legacy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Negli argomenti seguenti vengono fornite indicazioni per la rimozione delle autorizzazioni dei pool e la disattivazione e eliminazione di server e pool da una distribuzione legacy di Office Communications Server 2007 R2. Non tutte le procedure elencate in questa sezione sono obbligatorie. Leggere le informazioni in ognuno di questi argomenti per determinare quale procedura utilizzare per rimuovere la disponibilità.

<div>


> [!WARNING]  
> Se sono state importate le directory conferenze per le conferenze telefoniche con accesso esterno a Lync Server 2013, è importante eseguire la transizione della proprietà della directory conferenze a Lync Server 2013 prima di iniziare a rimuovere le autorizzazioni dei pool. Se si rimuove un pool senza prima trasferire la proprietà delle directory conferenze, la funzionalità di accesso esterno non funzionerà più per tutte le riunioni spostate. È necessario eseguire il passaggio di trasferimento di proprietà una volta per ogni directory conferenze del pool legacy.



</div>

<div>


> [!IMPORTANT]  
> Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima di rimuovere l'ambiente legacy, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Spostare le directory conferenze](move-conference-directories.md)

  - [Aggiornare i record SRV DNS](update-dns-srv-records_1.md)

  - [Rimozione di autorizzazioni di server e pool](decommissioning-servers-and-pools.md)

  - [Rimuovere BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

