---
title: 'Lync Server 2013: Panoramica del server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Panoramica del server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Un amministratore è un server che esegue Lync Server 2013 che autentica le richieste degli utenti, ma non ospita gli account utente. Puoi facoltativamente distribuire un Director nei due scenari seguenti:

  - Se si Abilita l'accesso da parte di utenti esterni distribuendo Edge Server, è anche necessario distribuire un Director. In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni. Quando un amministratore viene usato per autenticare utenti esterni, allevia i server del pool Front-end dall'overhead dell'esecuzione dell'autenticazione di questi utenti. Consente inoltre di isolare i pool di front-end interni da traffico illecito, ad esempio attacchi Denial of Service. Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.

  - Se si distribuiscono più pool Front-end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario tutte le richieste vanno prima di tutto al Director, che li instrada al pool Front end corretto.

</div>

<span> </span>

</div>

</div>

</div>

