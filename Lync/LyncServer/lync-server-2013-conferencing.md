---
title: 'Lync Server 2013: Servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f368a375a73eddc78b858c0d85a1bc21a1bd04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-11_

Con le conferenze unificate in Lync Server 2013, gli utenti possono collaborare, condividere informazioni e coordinare i loro sforzi in tempo reale. Tutti gli utenti possono usare l'intera gamma di collaborazioni spontanee, riunioni pianificate e strumenti per riunioni. Le funzionalità di conferenza vocale e video possono essere usate da qualsiasi posizione con una connessione Internet e gli utenti non possono partecipare a conferenze audio tramite la chiamata con un telefono PSTN (Public Switched Telephone Network).

Gli strumenti di riunione integrati in Outlook consentono agli organizzatori di pianificare una riunione o iniziare una conferenza estemporanea con un solo clic e renderlo altrettanto facile per i partecipanti partecipare. Un client Web estende le funzionalità di conferenza avanzate ai partecipanti che non hanno eseguito la versione desktop di Lync.

<div>

## <a name="audio-and-video-conferencing"></a>Conferenze audio e video

Lync Server offre un'esperienza utente familiare per gli utenti dei servizi di Bridge audio tradizionali, inclusi i servizi di accesso esterno PSTN con i comandi di controllo delle chiamate a tocco tonale. Allo stesso tempo, incorpora potenti funzionalità di pianificazione, partecipazione e gestione disponibili solo con una piattaforma di comunicazioni unificata integrata.

Con un solo clic, gli utenti possono pianificare una riunione da Outlook. I dettagli, ad esempio l'ora della riunione, la posizione e i partecipanti, seguono il modello familiare di Outlook. Inoltre, le informazioni specifiche per le conferenze telefoniche, ad esempio il numero di accesso esterno, gli ID riunione e i promemoria PIN (Personal Identification Number), vengono popolati automaticamente.

Per assicurarti che solo le persone autorizzate partecipino a una chiamata, Lync Server offre più livelli di autenticazione per i partecipanti. Gli utenti che partecipano tramite Lync sono già autenticati da servizi di dominio Active Directory e non devono immettere un PIN, un codice di passaggio o un ID riunione.

Lync semplifica l'esperienza degli utenti di videoconferenza incorporando video nel client unificato, in modo che la programmazione di una riunione con video o l'escalation del video sia spontanea e semplice.

Lync Server semplifica l'aggiunta di video a una chiamata telefonica standard con un solo clic. Quando sono presenti più partecipanti a una videochiamata o a una conferenza, ogni utente può visualizzare il video da un massimo di cinque utenti contemporaneamente o un relatore può scegliere una sola origine video per essere visualizzata esclusivamente da tutti.

Video ad alta definizione (risoluzione 1270 x 720; proporzioni 16:9) e video VGA (risoluzione 640 x 480; proporzioni 4:3) sono supportati per le chiamate peer-to-peer tra gli utenti che eseguono Lync in computer di fascia alta. La risoluzione visualizzata da ogni partecipante in una singola conversazione può essere diversa, a seconda delle funzionalità video del rispettivo hardware di ogni utente.

Gli amministratori IT possono impostare criteri per limitare o disabilitare il video ad alta definizione o VGA nei client, a seconda della funzionalità del computer, della larghezza di banda della rete e della presenza di una fotocamera in grado di fornire la risoluzione necessaria. Questi criteri vengono applicati tramite il provisioning in banda.

</div>

<div>

## <a name="web-conferencing"></a>Conferenza Web

Lync Server integra funzionalità di condivisione dei servizi di conferenza, ad esempio desktop, applicazioni, allegati, lavagne, sondaggi e PowerPoint, in Lync semplificato. In combinazione con le conferenze audio o video, il risultato è una sessione altamente immersiva e collaborativa semplice da semplificare.

Per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 impiega Office Web Apps per gestire le presentazioni di PowerPoint. Gli utenti possono condividere un'immagine o copiare e incollare testo usando una lavagna nella riunione Lync. I relatori possono eseguire sondaggi nella riunione Lync per sollecitare il feedback dei partecipanti.

La condivisione desktop consente ai relatori di trasmettere in tempo reale qualsiasi elemento visivo, applicazioni, pagine Web, documenti, software o parte dei propri desktop ai partecipanti remoti, direttamente da Lync. I membri del gruppo di destinatari possono seguire i movimenti del mouse e l'input da tastiera. I relatori possono scegliere di condividere l'intero schermo o solo una parte. Condividendo i loro desktop, i relatori possono interagire con i loro destinatari in demo di prodotti o software interattivi da qualsiasi posizione.

La condivisione delle applicazioni consente ai relatori di condividere il controllo del software sui propri desktop senza perdere di vista il feedback dei partecipanti o le domande di testo. I relatori possono anche delegare il controllo dell'applicazione ai partecipanti alla riunione.

</div>

<div>

## <a name="dial-in-conferencing"></a>Servizi di conferenza telefonica con accesso esterno

Per gli utenti che non usano un computer personale, sono disponibili diversi metodi per partecipare a una conferenza telefonica Lync Server. Un utente PSTN può chiamare un numero di accesso, accedere al Bridge della riunione e quindi immettere l'ID riunione. Per riunioni più sicure, l'utente può anche essere obbligato a immettere il proprio PIN per l'autenticazione in Active Directory. Lync Server supporta anche i dispositivi Lync Phone Edition, che sono dispositivi IP autonomi forniti da Microsoft partner.

</div>

</div>

<span> </span>

</div>

</div>

</div>

