---
title: Opzioni di abbinamento e procedure consigliate per il pool di Lync Server 2013 supportate
description: Lync Server 2013 supporta le opzioni per l'abbinamento dei pool e le procedure consigliate.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d0f8331c0b6998008efff8af70ae3c4b43a9c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560282"
---
# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opzioni di abbinamento del pool supportate e procedure consigliate per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-09_

La distanza tra due data center che devono contenere pool Front End abbinati tra loro può essere illimitata. Si consiglia di utilizzare due data center situati nella stessa area internazionale con collegamenti ad alta velocità. La situazione ottimale prevede che i due data center siano sufficientemente distanti per evitare che un'emergenza interessi entrambi contemporaneamente.

L'implementazione di due data center in aree internazionali diverse è possibile, ma può causare una perdita di dati più elevata a causa della latenza nella replica dei dati.

Quando si pianificano i pool da associare, è necessario tenere presente che sono supportate solo le associazioni seguenti:

  - I pool Enterprise Edition possono essere abbinati solo ad altri pool Enterprise Edition. Analogamente, i pool Standard Edition sono abbinabili solo ad altri pool Standard Edition.

  - I pool fisici possono essere abbinati solo ad altri pool fisici. Analogamente, i pool virtuali sono abbinabili solo ad altri pool virtuali.

  - I pool associati insieme devono eseguire lo stesso sistema operativo.

È possibile abbinare due pool in un modo diverso da quanto consigliato sia nel Generatore di topologie sia durante la convalida della topologia. Il Generatore di topologie, ad esempio, consente di abbinare un pool Enterprise Edition a un pool Standard Edition. Tuttavia, questi tipi di abbinamenti non sono supportati.

Ogni pool di una coppia deve essere in grado di servire tutti gli utenti di entrambi i pool in caso di emergenza.

Se si abbinano pool Enterprise Edition, è anche possibile implementare la disponibilità elevata nei server Back End, ma per coppie di pool Standard Edition sono disponibili solo le misure per il ripristino di emergenza.

</div>

<span> </span>

</div>

</div>

</div>

