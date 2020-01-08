---
title: "Lync Server 2013: assegnazione dell'ambito dei criteri di posizione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c44bef383690856d873d64ab6218b0f14219e73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Come per altri criteri di Lync Server, i criteri di posizione possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri di posizione a livello di utente si comporta in modo leggermente diverso rispetto a quello di altri criteri di Lync Server. Non solo i criteri di posizione per utente possono essere applicati agli oggetti endpoint, ad esempio gli utenti e gli oggetti dei contatti telefonici di area comune, ma possono essere applicati anche ai siti di rete di Lync Server. I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale). Tutti i client connessi alle subnet in un sito di rete prelevano automaticamente i criteri di posizione assegnati al sito di rete. Nei casi in cui un criterio di posizione a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio di posizione basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.

A ogni sito di rete è assegnato un criterio di posizione e ogni criterio avrà diversi usi PSTN, URI di notifica e valori degli URI di conferenza assegnati.

<div>


> [!NOTE]  
> Il motivo di questo comportamento speciale per l'ambito dei criteri è che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito che si usa viene assegnato a ser.



</div>

</div>

<span> </span>

</div>

</div>

</div>

