---
title: 'Fase 10: sito legacy decommission'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>Fase 10: sito legacy decommission

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Gli argomenti seguenti includono indicazioni per lo smantellamento dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy di Office Communications Server 2007 R2. Non tutte le procedure elencate in questa sezione sono obbligatorie. Leggere le informazioni in ognuno di questi argomenti per determinare la procedura di disattivazione da usare.

<div>


> [!WARNING]  
> Se sono state importate le directory conferenza per le conferenze telefoniche con accesso esterno a Lync Server 2013, è importante eseguire la transizione della proprietà della directory conferenza a Lync Server 2013 prima di iniziare la disattivazione dei pool. Se si rimuove la Commissione da un pool senza la prima transizione della proprietà della directory conferenza, la funzionalità di accesso esterno per tutte le riunioni migrate non funzionerà più. È necessario eseguire il passaggio per la proprietà transizione una sola volta per ogni directory di conferenza nel pool legacy.



</div>

<div>


> [!IMPORTANT]  
> Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima della disattivazione dell'ambiente legacy, vedere<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Trasferire le directory conferenza](move-conference-directories.md)

  - [Aggiornare i record SRV DNS](update-dns-srv-records_1.md)

  - [Disattivazione di server e pool](decommissioning-servers-and-pools.md)

  - [Rimuovere BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

