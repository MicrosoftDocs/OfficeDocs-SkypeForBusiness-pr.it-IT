---
title: 'Lync Server 2013: distribuzione di siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edacf70cf4a8b899857864c400fa92f78bb0d94b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Distribuzione di siti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Gli utenti del sito di succursale ottengono la maggior parte delle funzionalità di Lync Server 2013 dal server nel sito centrale a cui è associato il sito di succursale. Ogni sito di succursale è associato esattamente a un sito centrale. Per garantire le chiamate alla e dalla rete PSTN (Public Switched Telephone Network), un sito di succursale può includere uno o più elementi seguenti:

  - Un gateway PSTN ed eventualmente un Mediation Server

  - Un trunk SIP

  - Un'infrastruttura vocale esistente con un centralino (PBX)

  - Un Survivable Branch Appliance

  - Survivable Branch Server

I siti di succursale con un Survivable Branch Appliance o un Survivable Branch Server sono più resistenti in periodi di problemi di rete o di siti centrali di aree estese rispetto a quelli di succursale senza una di queste soluzioni. Ad esempio, in un sito in cui è presente un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate PSTN se la rete che connette il sito di succursale al sito centrale è inattivo. Un altro modo per ottenere la resilienza dei siti di succursale consiste nell'utilizzare un gateway PSTN o un trunk SIP con una distribuzione di Lync Server su vasta scala nel sito di succursale.

Per informazioni dettagliate sulla distribuzione dei siti di succursale per l'organizzazione, inclusi i prerequisiti e altre considerazioni relative alla pianificazione, vedere [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [Planning for Branch-site Voice Resilienzy in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Fornitura di connettività PSTN in un sito di succursale in Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

