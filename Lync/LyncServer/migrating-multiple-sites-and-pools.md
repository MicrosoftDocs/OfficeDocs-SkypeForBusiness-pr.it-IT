---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Lync Server 2013 supporta distribuzioni multisito e multipool. Il processo di migrazione di più pool da Lync Server 2010 a Lync Server 2013 richiede le considerazioni seguenti:

1.  Dopo aver distribuito un pool di piloti di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti. Dopo aver spostato un utente nel pool pilota, ad esempio, verificare che i criteri di conferenza dell'utente siano stati spostati in Lync Server 2013.

2.  Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.

3.  Dopo aver eseguito la transizione dalle route federate da Lync Server 2010 Edge Server ai server pilota Lync Server 2013 Edge, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.

4.  Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Lync Server 2010 sia vuoto.

5.  Dopo aver verificato che il pool di Lync Server 2010 sia vuoto, è possibile disattivare il pool.
    
    Per informazioni dettagliate su come disattivare il pool e i server legacy di Lync Server 2010, vedere la [fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

