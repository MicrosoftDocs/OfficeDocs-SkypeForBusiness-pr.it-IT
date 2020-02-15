---
title: 'Lync Server 2013: pianificazione del controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Pianificazione del controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

In Lync Server 2013, il supporto per gli scenari di controllo delle chiamate remote consente agli utenti di controllare i propri telefoni PBX (Private Branch Exchange) utilizzando Lync 2013 nei propri computer desktop. In questa sezione vengono illustrati le funzionalità di controllo delle chiamate remote e i requisiti per distribuire il controllo delle chiamate remote.

L'integrazione tra un sistema PBX e Lync Server 2013 rende possibile per gli utenti abilitati per il controllo delle chiamate remote di utilizzare l'interfaccia utente di Lync 2013 per controllare le chiamate sui rispettivi telefoni PBX nei modi seguenti:

<div>


> [!NOTE]  
> In sintesi, le capacità del PBX che ospita il telefono PBX di un utente determinano le funzionalità di controllo delle chiamate remote che saranno disponibili per tale utente.



</div>

  - Effettuare una chiamata in uscita

  - Rispondere a una chiamata in arrivo

  - Rispondere a una chiamata in arrivo con un messaggio istantaneo
    
    <div>
    

    > [!NOTE]  
    > Quando il numero di telefono del chiamante può essere associato a un indirizzo di messaggistica istantanea nell'elenco indirizzi globale (GAL) dell'organizzazione, nell'elenco contatti di Lync del destinatario della chiamata o nell'organizzazione di un partner federato.

    
    </div>

  - Trasferire una chiamata

  - Inoltrare una chiamata in arrivo

  - Mettere in attesa le chiamate

  - Alternare tra più chiamate simultanee

  - Rispondere a una seconda chiamata quando ne è già attiva un'altra (ovvero, avviso di chiamata)

  - Comporre cifre DTMF (Dual-Tone Multifrequency)

  - Digitare note nel programma per la creazione di appunti Microsoft Office OneNote dalla finestra di conversazione

Inoltre, quando un utente è abilitato per il controllo delle chiamate remote, Lync 2013 fornisce all'utente le informazioni di chiamata seguenti:

  - Identificazione di un chiamante per nome quando il numero di telefono del chiamante è presente nell'elenco dei contatti di un client di messaggistica e collaborazione di Microsoft Office Outlook, un elenco contatti di Lync o un GAL dell'organizzazione.

  - Chiamate in arrivo e in uscita effettuate, salvate nella cartella Cronologia conversazioni in Outlook.

  - Notifiche di chiamata senza risposta, che vengono inviate alla cartella posta in arrivo di Outlook dell'utente, ma vengono generate solo se Lync è in esecuzione quando viene ricevuta la chiamata in arrivo.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Controllo delle chiamate remote e VoIP aziendale

Anche se le funzionalità di controllo delle chiamate remote sono separate dalle caratteristiche di VoIP aziendale e gli utenti non possono essere abilitati per entrambi, VoIP aziendale fornisce un sottoinsieme di caratteristiche che sono disponibili anche per gli utenti abilitati per il controllo delle chiamate remote. Se Enterprise Voice è distribuito, gli utenti abilitati per il controllo delle chiamate remote possono utilizzare Lync per accedere alle seguenti funzionalità di VoIP aziendale:

  - Effettuare e ricevere chiamate audio a un altro client Lync

  - Partecipare alla parte audio di una conferenza creata da un utente abilitato per VoIP aziendale

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

