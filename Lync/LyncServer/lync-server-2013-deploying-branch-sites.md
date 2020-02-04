---
title: 'Lync Server 2013: Distribuzione di siti di succursale'
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
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Distribuzione di siti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Gli utenti del sito della filiale ottengono la maggior parte delle funzionalità di Lync Server 2013 dal server nel sito centrale a cui è associato il sito della filiale. Ogni sito di succursale è associato esattamente a un sito centrale. Per eseguire chiamate da e verso la rete PSTN (Public Switched Telephone Network), un sito di succursale potrebbe contenere una delle opzioni seguenti:

  - Un gateway PSTN e possibilmente un server di meditazione

  - Trunk SIP

  - Infrastruttura vocale esistente con un PBX (Private Branch Exchange)

  - Un Survivable Branch Appliance

  - Un Survivable Branch Server

I siti di succursale con un Survivable Branch Appliance o un Survivable Branch Server sono più resistenti in tempi di errori di rete a livello di area geografica o di siti centrali diversi da quelli della filiale senza una di queste soluzioni. Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate PSTN se la rete che connette il sito della filiale al sito centrale non è più presente. Un altro modo per ottenere la resilienza del sito della filiale consiste nell'usare un gateway PSTN o un trunk SIP con una distribuzione su vasta scala di Lync Server presso il sito della filiale.

Per informazioni dettagliate sulla distribuzione del sito della filiale appropriata per l'organizzazione, inclusi i prerequisiti e altre considerazioni sulla pianificazione, vedere [pianificazione della connettività PSTN in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [pianificazione della resilienza vocale del sito filiale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Implementazione della connettività PSTN in un sito di succursale in Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

