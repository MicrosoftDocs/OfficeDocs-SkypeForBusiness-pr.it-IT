---
title: Migrazione di più siti e pool
description: Migrazione di più siti e pool.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543252"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Lync Server 2013 supporta distribuzioni multisito e multi-pool. Il processo di migrazione di più pool da Lync Server 2010 a Lync Server 2013 richiede le considerazioni seguenti:

1.  Dopo aver distribuito un pool pilota di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti. Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che i criteri di conferenza dell'utente siano stati spostati in Lync Server 2013.

2.  Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.

3.  Dopo la transizione delle route federate dai server perimetrali di Lync Server 2010 ai server perimetrali di Lync Server 2013 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.

4.  Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Lync Server 2010 sia vuoto.

5.  Dopo aver verificato che il pool di Lync Server 2010 sia vuoto, è possibile disattivare il pool.
    
    Per informazioni dettagliate su come disattivare i server e il pool legacy di Lync Server 2010, vedere [Phase 8: decommission legacy pools](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

