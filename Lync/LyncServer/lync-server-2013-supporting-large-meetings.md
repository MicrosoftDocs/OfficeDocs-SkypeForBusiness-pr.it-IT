---
title: 'Lync Server 2013: supportare riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Supporto di riunioni di grandi dimensioni tramite Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Le riunioni di grandi dimensioni non seguono il modello di test descritto nella sezione precedente perché presentano le caratteristiche seguenti:

  - Il formato della riunione è una presentazione uno-a-molti.

  - Uno o più utenti sono relatori e tutti gli altri membri partecipano solo come partecipanti.

  - La condivisione delle presentazioni di PowerPoint è l'attività di collaborazione dati principale.

  - L'audio è obbligatorio e può essere usato anche il video.

  - Una persona dedicata, in genere l'organizzatore della riunione o un assistente dell'organizzatore configura bene la riunione in anticipo.

  - Il personale dedicato (non i relatori) esegue la riunione, inclusa la connessione a una riunione online, verificando che l'audio, il video e la condivisione delle diapositive funzionino, gestiscono i ruoli di lobby e utenti, riattivano e riattivano i partecipanti, le domande e la gestione delle registrazioni, come appropriato.

Il supporto di riunioni di grandi dimensioni fino a 1000 utenti richiede la risoluzione dei problemi relativi al modello hardware condiviso e al modello senza prenotazione.

Per avere sufficienti risorse di memoria e CPU per riunioni fino a 1000 utenti, i server front-end ospitanti non devono ospitare altri carichi di lavoro istantanei e di presenza o di Enterprise Voice. Non deve inoltre ospitare altre riunioni, indipendentemente dalle dimensioni delle altre riunioni. Ciò significa che le riunioni di hosting di un massimo di 1000 utenti richiedono la configurazione di un pool di Lync Server separato dedicato all'hosting di riunioni di grandi dimensioni fino a 1000 utenti.

Un pool di Lync Server dedicato all'hosting di riunioni di grandi dimensioni dovrebbe ospitare una sola riunione di un massimo di 1000 utenti contemporaneamente, in modo che gli orari delle riunioni debbano essere prenotati in anticipo tramite un processo di pianificazione fuori banda per garantire il supporto dedicato del servizio front end ERS. Per supportare più di una riunione di grandi dimensioni contemporaneamente, è consigliabile configurare più pool di riunioni di grandi dimensioni dedicati.

È consigliabile che una persona dedicata esegua e controlli la parte online di una riunione di grandi dimensioni. Questa persona può essere l'organizzatore, il delegato dell'organizzatore o del relatore oppure un membro del team di supporto di grandi riunioni dedicato, a seconda delle preferenze dell'organizzazione.

Nelle sezioni seguenti viene descritto come implementare un pool dedicato per riunioni di grandi dimensioni, incluse le procedure consigliate per l'uso di Lync Server 2013 per supportare scenari di grandi riunioni.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione del supporto per riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gestione di riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

