---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-26_

Lync Server 2013 supporta distribuzioni multisito e multipool. Il processo di migrazione di più pool da Office Communications Server 2007 R2 a Lync Server 2013 richiede le considerazioni seguenti:

1.  Dopo aver distribuito un pool di piloti di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.

2.  Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.

3.  Dopo la transizione delle route federate da Office Communications Server 2007 R2 Edge Servers ai server pilota Lync Server 2013 Edge, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.

4.  Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Office Communications Server 2007 R2 sia vuoto.

5.  Dopo aver verificato che il pool di Office Communications Server 2007 R2 è vuoto, è possibile disattivare il pool.
    
    Per informazioni dettagliate su come disattivare il pool e i server legacy di Office Communications Server 2007 R2, vedere la [fase 10: rimuovere la Commissione dal sito legacy](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

