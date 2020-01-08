---
title: Modello di conferenza utente di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Modello di conferenza utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Una parte fondamentale del modello di conferenza utente di Lync Server è la dimensione della riunione. Dopo aver raccolto i dati dai più punti dati, come descritto nella sezione precedente, sono stati determinati i seguenti elementi:

  - La maggior parte delle riunioni è in realtà una piccola riunione di collaborazione con una media di quattro o sei partecipanti

  - Circa il 80% delle riunioni ha meno di 20 partecipanti.

  - 99,98% delle riunioni hanno meno di 100 partecipanti.

Oltre alle dimensioni della riunione, il modello per gli utenti dei servizi di conferenza tiene conto anche di diversi fattori, ad esempio:

  - **Riunioni simultanee**   quante volte si prevede che gli utenti si trovino in riunioni contemporaneamente?

  - **Media mix**   quali tipi di elementi multimediali sono disponibili e che dovrebbero essere usati dagli utenti nelle riunioni?

  - **I tipi**   utente sono utenti interni, utenti remoti, utenti federati o utenti anonimi?

  - **Rampa di riunione**   per quanto tempo è necessario per tutti gli utenti di una riunione partecipare a una riunione?

Per informazioni dettagliate sul modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

Per determinare il numero di riunioni e utenti da usare per il test, abbiamo eseguito le operazioni seguenti:

  - Il numero totale di utenti di un'organizzazione, ad esempio gli utenti di 80.000, lo ha moltiplicato per la percentuale di concorrenza della riunione (ad esempio, 5% di tutti gli utenti) per determinare il numero totale di utenti che dovrebbero essere presenti in riunioni contemporaneamente (in questo esempio , 4000 utenti).

  - Diviso il numero totale di utenti in base al numero di Lync Server 2013, server front-end nella distribuzione (ad esempio, 8 Server) per determinare il numero stimato di partecipanti alla riunione per server front-end (in questo esempio, 500 utenti per server front-end).

  - Diviso il numero di utenti per server front-end per la dimensione media della riunione (ad esempio 4 utenti) per determinare il numero medio stimato di riunioni per server front-end (in questo esempio, le riunioni di 125 per server front-end).

  - Per ottenere il caricamento per mezzo di ogni server front-end, abbiamo valutato la combinazione di elementi multimediali. Ad esempio, supponendo che il 75% delle riunioni richieda più di un semplice supporto audio e che il 50% di queste riunioni richieda la condivisione delle applicazioni, una media di 47 riunioni e 188 utenti si connettono simultaneamente a ogni server front-end per la condivisione delle applicazioni.

  - È stata testata una varietà di dimensioni delle riunioni (in base al modello utente di un massimo di 250 utenti in un pool condiviso) per garantire la scalabilità del server.

</div>

<span> </span>

</div>

</div>

</div>

