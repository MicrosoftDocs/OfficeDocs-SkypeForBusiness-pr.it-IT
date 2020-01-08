---
title: 'Lync Server 2013: pianificazione per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Pianificazione del controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

In Lync Server 2013 il supporto per scenari di controllo delle chiamate remote consente agli utenti di controllare i telefoni PBX (Private Branch Exchange) usando Lync 2013 nei propri computer desktop. Questa sezione descrive le caratteristiche del controllo delle chiamate remote e i requisiti per la distribuzione del controllo delle chiamate remote.

L'integrazione tra un PBX e Lync Server 2013 consente agli utenti abilitati per il controllo delle chiamate remote di usare l'interfaccia utente di Lync 2013 per controllare le chiamate sui telefoni PBX nei modi seguenti:

<div>


> [!NOTE]  
> In definitiva, le funzionalità del PBX che ospita un telefono PBX dell'utente determinano le funzionalità di controllo delle chiamate remote che saranno disponibili per l'utente.



</div>

  - Effettuare una chiamata in uscita

  - Rispondere a una chiamata in arrivo

  - Rispondere a una chiamata in arrivo con un messaggio istantaneo
    
    <div>
    

    > [!NOTE]  
    > Quando il numero di telefono del chiamante può essere associato a un indirizzo di messaggio istantaneo nell'elenco indirizzi globale (GAL) dell'organizzazione, nell'elenco contatti di Lync del destinatario o nell'organizzazione di un partner federato.

    
    </div>

  - Trasferire una chiamata

  - Inoltrare una chiamata in arrivo

  - Posizionare le chiamate in attesa

  - Alternare più chiamate simultanee

  - Rispondere a una seconda chiamata mentre si è già in una chiamata (ovvero chiamata in attesa)

  - Digitare le cifre DTMF (Dual-Tone Multifrequency)

  - Nella finestra di conversazione digitare note in Microsoft Office OneNote programma di acquisizione appunti

Inoltre, quando un utente è abilitato per il controllo delle chiamate remote, Lync 2013 fornisce all'utente le informazioni sulle chiamate seguenti:

  - Identificazione di un chiamante per nome quando il numero di telefono del chiamante è presente nell'elenco dei contatti di un client di messaggistica e collaborazione di Microsoft Office Outlook e Collaboration di un utente abilitato al controllo remoto, un elenco di contatti di Lync o un GAL dell'organizzazione.

  - Passate le chiamate in entrata e in uscita, salvate nella cartella Cronologia conversazioni di Outlook.

  - Notifiche di chiamata perse, che vengono inviate alla cartella posta in arrivo di Outlook dell'utente, ma vengono generate solo se Lync è in funzione quando viene ricevuta la chiamata in arrivo.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Controllo delle chiamate remote e VoIP aziendale

Anche se le funzionalità di controllo delle chiamate remote sono separate dalle caratteristiche di VoIP aziendale e gli utenti non possono essere abilitati per entrambi, Enterprise Voice offre un sottoinsieme di funzionalità disponibili anche per gli utenti abilitati per il controllo delle chiamate remote. Se Enterprise Voice viene distribuita, gli utenti abilitati per il controllo delle chiamate remote possono usare Lync per accedere alle caratteristiche di VoIP aziendale seguenti:

  - Effettuare e ricevere chiamate audio in un altro client Lync

  - Partecipare alla parte audio di una conferenza creata da un utente abilitato per VoIP aziendale

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

