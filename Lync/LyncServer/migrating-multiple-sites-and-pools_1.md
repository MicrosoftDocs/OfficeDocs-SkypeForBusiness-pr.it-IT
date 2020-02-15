---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97bd53e884d4b66b8197ef2672d6ffdca39d4cea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

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

