---
title: Opzioni di associazione e procedure consigliate per il raggruppamento supportate in Lync Server 2013
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
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opzioni di associazione e procedure consigliate per la combinazione di pool supportate per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-03-09_

Non esiste alcuna restrizione sulla distanza tra due centri dati che includono i pool Front-End associati tra loro. Ti consigliamo di usare due centri dati nella stessa area geografica mondiale, con collegamenti ad alta velocità tra di essi. È preferibile che i due centri dati siano abbastanza separati per evitare che un singolo disastro colpisca contemporaneamente.

È possibile avere due centri dati in tutte le aree del mondo, ma potrebbe causare una perdita di dati più elevata a causa della latenza nella replicazione dei dati.

Quando si pianificano i pool da associare, è necessario ricordare che sono supportate solo le associazioni seguenti:

  - I pool Enterprise Edition possono essere accoppiati solo con altri pool di Enterprise Edition. Allo stesso modo, i pool Standard Edition possono essere abbinati solo agli altri pool di Standard Edition.

  - I pool fisici possono essere accoppiati solo con altri pool fisici. Allo stesso modo, i pool virtuali possono essere abbinati solo ad altri pool virtuali.

  - I pool combinati devono eseguire lo stesso sistema operativo.

Né il generatore di topologie né la convalida della topologia impediscono l'associazione di due pool in modo da non seguire questi suggerimenti. Ad esempio, generatore di topologie consente di associare un pool Enterprise Edition a un pool di Standard Edition. Tuttavia, questi tipi di associazione non sono supportati.

Ogni pool in una coppia deve avere la capacità di servire tutti gli utenti da entrambi i pool in caso di emergenza.

Se si abbinano pool Enterprise Edition, è anche possibile implementare una disponibilità elevata nei server back-end, ma per le coppie di pool standard solo le misure di ripristino di emergenza sono disponibili.

</div>

<span> </span>

</div>

</div>

</div>

