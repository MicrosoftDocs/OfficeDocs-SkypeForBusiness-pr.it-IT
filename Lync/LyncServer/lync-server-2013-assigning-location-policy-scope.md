---
title: "Lync Server 2013: assegnazione dell'ambito dei criteri percorso"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69218c3f5399b62fc67fe0d538a98f1bdadd3cf4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Assegnazione dell'ambito dei criteri percorso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

Come per gli altri criteri di Lync Server, i criteri di percorso possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri percorso a livello di utente si comporta in modo diverso rispetto ad altri criteri di Lync Server. Non solo i criteri percorso per utente devono essere applicati agli oggetti endpoint (come gli utenti e gli oggetti contatto telefonici di area comune), che possono essere applicati anche ai siti di rete di Lync Server. I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale). Tutti i client connessi alle subnet in un sito di rete raccolgono automaticamente il criterio percorso assegnato al sito di rete. Nei casi in cui un criterio percorso a livello di utente sia assegnato a un utente e a un sito di rete, il criterio percorso basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.

A ogni sito di rete è assegnato un criterio percorso e ogni criterio avrà diversi utilizzi PSTN, URI di notifica e valori URI di conferenza assegnati.

<div>


> [!NOTE]  
> Il motivo di questo comportamento di ambito dei criteri speciali è tale che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito di u ser è assegnato a.



</div>

</div>

<span> </span>

</div>

</div>

</div>

