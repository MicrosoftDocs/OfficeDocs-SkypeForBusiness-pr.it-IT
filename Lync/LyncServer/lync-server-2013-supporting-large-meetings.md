---
title: 'Lync Server 2013: supporto di riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d1ba298ea35c177eb51191c230ea51a50d6c3e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Supporto di riunioni di grandi dimensioni con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Le riunioni di grandi dimensioni non seguono il modello di test descritto nella sezione precedente, poiché hanno le caratteristiche seguenti:

  - La riunione è una presentazione uno a molti.

  - Pochi utenti hanno il ruolo di relatori o il relatore è uno solo e gli altri utenti sono solo partecipanti.

  - La principale attività di collaborazione dati è la condivisione di presentazioni di PowerPoint.

  - L'audio è indispensabile e possono essere usate anche le funzionalità video.

  - Una persona dedicata, di solito l'organizzatore della riunione o un assistente dell'organizzatore, imposta la riunione con buon anticipo.

  - Uno staff dedicato (non i relatori) si occupa di aspetti della riunione quali la connessione alla riunione online, la verifica del funzionamento di audio, video e condivisione delle diapositive, la gestione della sala di attesa e dei ruoli utente, la disattivazione e la riattivazione dell'audio dei partecipanti, la raccolta delle domande e la gestione delle registrazione, come più opportuno.

Per supportare riunioni di grandi dimensioni con un massimo di 1000 utenti, è necessario affrontare i problemi relativi al modello dell'hardware condiviso e al modello senza prenotazione.

Per disporre di risorse di memoria e CPU sufficienti per riunioni fino a 1000 utenti, i front end server host non devono ospitare altri carichi di lavoro per la messaggistica istantanea e la presenza o VoIP aziendale. Inoltre, non devono ospitare altre riunioni, non importa quanto grandi. Questo significa che l'hosting di riunioni fino a 1000 utenti richiede la configurazione di un pool di Lync Server separato dedicato all'hosting di riunioni di grandi dimensioni fino a 1000 utenti.

Un pool di Lync Server dedicato all'hosting di riunioni di grandi dimensioni deve ospitare una sola riunione fino a 1000 utenti contemporaneamente, in modo che i tempi di riunione debbano essere prenotati in anticipo tramite un processo di pianificazione fuori banda per garantire un supporto dedicato dal servizio front end Service. ERS. Per supportare più riunioni di grandi dimensioni contemporaneamente, si consiglia di configurare più pool dedicati.

Si consiglia inoltre di dedicare una persona all'esecuzione e al monitoraggio della parte online delle riunioni di grandi dimensioni. Questa persona può essere l'organizzatore, un delegato dell'organizzatore o del relatore o un membro del team di supporto alle riunioni di grandi dimensioni, a seconda delle preferenze dell'organizzazione.

Nelle sezioni seguenti viene descritto come implementare un pool dedicato per riunioni di grandi dimensioni, incluse le procedure consigliate per l'utilizzo di Lync Server 2013 per il supporto di scenari di riunioni di grandi dimensioni.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione del supporto per le riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gestione di riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

