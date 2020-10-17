---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9de4309f114b712a8ea575f42499922e75f5d8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527343"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-26_

Lync Server 2013 supporta distribuzioni multisito e multi-pool. Il processo di migrazione di più pool da Office Communications Server 2007 R2 a Lync Server 2013 richiede le considerazioni seguenti:

1.  Dopo aver distribuito un pool pilota di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.

2.  Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.

3.  Dopo aver eseguito la transizione dalle route federate dai server perimetrali di Office Communications Server 2007 R2 ai server perimetrali di Lync Server 2013 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.

4.  Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Office Communications Server 2007 R2 sia vuoto.

5.  Dopo aver verificato che il pool di Office Communications Server 2007 R2 è vuoto, sarà possibile disattivare il pool.
    
    Per informazioni dettagliate su come disattivare i server e il pool di Office Communications Server 2007 R2 legacy, vedere [Phase 10: decommission legacy Site](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

